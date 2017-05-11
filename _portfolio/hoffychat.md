---
layout: post
title: HoffyChat
thumbnail-path: "img/hoffychat.png"
short-description: HoffyChat is a chat room app to chat with your friends and family online.

---

{:.center}
![]({{ site.baseurl }}/img/hoffychat.png)

## Explanation

HoffyChat is the first app that I built with AngularJS. It uses several various libraries for its simple but effective use. Libraries include: Firebase, AngularFire, Bootstrap, UI-Bootstrap, and one or two other AngularJS plugins.

## Problem

One of the bigger issues that I faced during this project was getting the Modals in UI-Bootstrap to function correctly. I couldn't figure which keywords from UI-Bootstrap would get the New Room Button to pop open the modal for entering a new room. Trying to figure out how get the modal controller to talk to the home controller where the button is, was just as daunting.

Some of the other less noteworthy issues involved getting the first room in the array of rooms to be the default room displayed in the view. Additionally, I had issues trying to get the CSS design layouts to work effectively.

The rest of the problems that I encountered were simply from my inexperience with the AngularJS framework and its libraries.

## Solution

I figured out that in order to get the modal controller to respond to the button on the home controller, I needed to add a service that will get the two controllers talking. Luckily, UI-Bootstrap has a service called $uibModalInstance that fixed that issue for me.

{% highlight javascript %}
function ModalCtrl($uibModalInstance, $scope, Room){

  $scope.createRoom = function(){
    $uibModalInstance.close($scope.addRoom);
  }

  $scope.dismiss = function(){
    $uibModalInstance.dismiss('cancel');
  }
}
{% endhighlight %}

To get the first room in the array of rooms to be the default room selected, I needed to attach a ng-init directive to the view. This directive initially runs any function that is attached to its value, hence ng-init.

{% highlight javascript %}
ng-init="selectRoom(rooms[0].$value)"
{% endhighlight %}

Getting used to the CSS layouts was all that was required for its effective usage.

## Results

After testing the apps layout on several different mediums and browsers, I decided that it would be best to add responsiveness to the site. Adding media queries and responsiveness to the app made mobile browsing so much more pleasant.

## Conclusion

Since this is the first app that I've written in AngularJS, I realize what a powerful tool it is for creating apps that are accessed within a browser. It makes writing apps so much faster and more intuitive. Also, while mobile browsing is becoming ever more popular, websites and apps must have the responsiveness for its variety of display sizes people use to access them.
