- two main building blocks of change detection in Angular:
  -- a component view
  -- the associated bindings

 #Automatic change detection with zones
    - As opposed to React, change detection in Angular can be triggered completely automatically as a result of any async event in a browser. 
    This is made possible by using the library called zone.js that introduces a concept of zones. 
    

    - But, `zone.js` also provides an API to run some code in a zone other than the Angular zone. Angular is not notified about async events happening in other zones.
     And no notification means no change detection.

   -The method name to do this is called runOutsideAngular and it’s implemented by the `NgZone` service.

   ** Using NgZone to run some code outside of Angular to avoid triggering change detection is a common optimization technique. **


   *  But it’s also possible to directly inject a parent component into a child component and update the parent state in a lifecycle hook. 

   * in devolopement mode:
     After each change detection cycle, Angular runs a check to ensure the component state is in sync with user interface. 
     This check is performed synchronously and may throw the `ExpressionChangedAfterItWasChecked` error.
