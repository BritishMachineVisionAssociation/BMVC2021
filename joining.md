---
layout: default_sparse
title: Joining the BMVA
permalink: /joining
---

## Joining the BMVA

You can now join the BMVA via [Eventbrite](https://www.eventbrite.co.uk/e/bmva-membership-2019-tickets-49987702564):

<div class="container-fluid pb-3">
    <!--<button id="eventbrite-widget-trigger" type="button">Buy Tickets</button>-->
    <div class="card p-1"><!-- style="background: #F8F7FA">-->
        <div class="card-body mx-auto">
          Please join using the options below:
        </div>
        <div id="eventbrite-widget-container-49987702564" class="embed-responsive"></div>
    </div>
</div>

If you are joining to attend a technical meeting then please note that the
non-member technical meeting cost includes a year's free membership to the
BMVA and will save you having to fill in a separate form.

To join without using the online form, please obtain an application form from:

| Address | Contact Details |
|:-------|:-------|
| BMVA Membership Secretary,&nbsp;&nbsp;&nbsp; | Tel: 01483 689851 |
| CVSSP, FEPS, | Fax: 01483 686031 |
| University of Surrey, | Email: [membership@bmva.org](mailto:membership@bmva.org) |
| Guildford, |
| Surrey, |
| GU2 7XH |

<br/>

Please send any changes in details to
[membership@bmva.org](mailto:membership@bmva.org) and pay via the
[eventbrite page](https://www.eventbrite.co.uk/e/bmva-membership-2018-tickets-42499208276).


If you have forgotten your membership number, please email
[membership@bmva.org](mailto:membership@bmva.org) and we will endeavour to
re-acquaint you!




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

    var height_to_use = 650;

    if (getWidth() < 1000) {
        height_to_use = 700;
    }

    if (getWidth() < 800) {
        height_to_use = 750;
    }

    if (getWidth() < 550) {
        height_to_use = 750;
    }

    window.EBWidgets.createWidget({
        // Required
        widgetType: 'checkout',
        eventId: '49987702564',

        //modal: true,
        //modalTriggerElementId: "eventbrite-widget-trigger",

        iframeContainerId: 'eventbrite-widget-container-49987702564',
        // Optional
        iframeContainerHeight: height_to_use,  // Widget height in pixels. Defaults to a minimum of 425px if not provided
        iFrameAutoAdapt: 100,
        onOrderComplete: exampleCallback  // Method called when an order has successfully completed
    });
</script>

