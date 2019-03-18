# Understanding Change Detection in Angular

Change Detection means **updating the DOM whenever data is changed**. 

![](../.gitbook/assets/image%20%283%29.png)

#### Manual Change Detection - J-Query, Backbone



![](../.gitbook/assets/image%20%2813%29.png)

### Angular JS - Change detection using $digest

* Watch expression connects DOM to Scope
* Digest Cycle invokes every watch expression and runs update
* Change detection would run multiple times \(up to 10\) until watchers stabilized

![Change detection using angular](../.gitbook/assets/image%20%2811%29.png)

![](../.gitbook/assets/image%20%284%29.png)

### Angular - Change detection using Template Bindings

* Every Component has a change detector
* One pass of change detection, from top to bottom
* Much faster than Angular JS $digest cycles

![](../.gitbook/assets/image.png)

#### What triggers change detection?

* Events \(click, scroll, etc.\)
* XHRs
* Timers
* Basically, any async call
* **ApplicationRef.tick\(\)** triggers change detection in root component

![](../.gitbook/assets/image%20%285%29.png)

Angular uses **Zones** internally to trigger change detection. 

#### What is a Zone? 

A **Zone** is an execution context that persists across async tasks. You can think of it as thread-local storage for JavaScript VMs.



![](../.gitbook/assets/image%20%282%29.png)

Angular provides **two strategies** for Change Detection:

* **Default** - Run Change Detector whenever data changes, hence updating the DOM  
* **onPush** - Angular will only run the change detector  when a new reference for data is created

![](../.gitbook/assets/image%20%281%29.png)

