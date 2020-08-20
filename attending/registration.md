---
layout: default_sparse
title: Conference Registration
permalink: /attending/registration/
index: 0
---

Registration for the virtual conference is now open. There are two options for registration: for accepted papers, there is a conference an event enabling registration fee of £85 to cover the server hosting for the videos and interactive content and fixed costs that we have tried to keep as low as possible to allow BMVC to go ahead. We require one of these fees to be paid <strong>per paper</strong> but it also includes a single registration for one of the authors. For additional authors and standard attendees there is a single registration rate of £25 which we have kept low to allow as manner people as possible to attend the interactive parts of the virtual conference.

### Bursaries

We have 20 free bursary places available for students who would otherwise be unable to meet the costs of attending the virtual conference. If you would like to apply for a bursary please fill in the form [here](https://forms.gle/zhmYCWfRPckEFx2e8) which will also ask for proof of your student status. Unfortunately, we cannot accept a bursary registration in place of the per paper event enabling fee.

### Registration

Please register for the virtual conference using the form below. <strong>IMPORTANT:</strong> Please register with the <strong>email address you wish to use to attend the conference</strong> as the registration will be linked to this email address and non-transferrable. For authors paying the per paper event enabling fee, <strong>please ensure you submit the correct paper ID in the eventbrite form</strong> (your paper ID from CMT).


<div class="container-fluid pb-3">
    <div class="card p-1" style="background: #F8F7FA">
        <div class="card-body mx-auto">
          Please register using the options below (scroll for more options):
        </div>
        <div id="eventbrite-widget-container-117309316323"></div>
    </div>
</div>

<script src="https://www.eventbrite.co.uk/static/widgets/eb_widgets.js"></script>

<script type="text/javascript">
    var exampleCallback = function() {
        console.log('Order complete!');
    };

    function getWidth() {
      if (self.innerWidth) {
        return self.innerWidth;
      }

      if (document.documentElement && document.documentElement.clientWidth) {
        return document.documentElement.clientWidth;
      }

      if (document.body) {
        return document.body.clientWidth;
      }
    }

    var height_to_use = 600;

    if (getWidth() < 1000) {
        height_to_use = 650;
    }

    if (getWidth() < 800) {
        height_to_use = 700;
    }

    if (getWidth() < 550) {
        height_to_use = 710;
    }

    window.EBWidgets.createWidget({
        // Required
        widgetType: 'checkout',
        eventId: '117309316323',
        iframeContainerId: 'eventbrite-widget-container-117309316323',

        // Optional
        iframeContainerHeight: height_to_use,  // Widget height in pixels. Defaults to a minimum of 425px if not provided
        onOrderComplete: exampleCallback  // Method called when an order has successfully completed
    });
</script> 
