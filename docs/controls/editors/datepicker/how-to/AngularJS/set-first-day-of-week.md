---
title: Set the First Weekday
page_title: Set the First Weekday | Kendo UI DatePicker Widget
description: "Learn how to set the first day of the week on a Kendo UI DatePicker width using AngularJS."
slug: howto_set_first_weekday_datepicker
---

# Set the First Weekday

The example below demonstrates how to set the first day of the week on a Kendo UI DatePicker width using AngularJS.

###### Example

```html
	<div id="example" ng-app="KendoDemos">
      <div ng-controller="MyCtrl">
        <div>
          <h4>Select date:</h4>
          <input kendo-date-picker
                 k-ng-model="dateObject"/>
        </div>
      </div>
    </div>

    <script>
      angular.module("KendoDemos", [ "kendo.directives" ])
      .controller("MyCtrl", function($scope){

      })
      .run(function() {
      	kendo.culture().calendar.firstDay= 3
      })
    </script>
```

## See Also

Other articles on Kendo UI DatePicker:

* [DatePicker JavaScript API Reference](/api/javascript/ui/datepicker)
* [How to Select Ranges between DatePickers]({% slug howto_select_ranges_between_datepicker %})
* [How to Create Date Masking]({% slug howto_create_date_masking_datepicker %})
* [How to Use AngularJS Copy Functionality]({% slug howto_use_angularjs_copy_functionality_datepicker %})
* [How to Integrate DatePicker with DateJS Library]({% slug howto_integrate_withdatejs_library_datepicker %})
* [How to Hide the Deafult Button]({% slug howto_hide_default_button_datepicker %})
* [How to Globally Modify Default Options]({% slug howto_globally_modify_default_options_datepicker %})
* [How to Persist Entered Dates]({% slug howto_persist_entered_dates_datepicker %})
* [How to Make Input Elements Readonly]({% slug howto_make_input_elements_readonly_datepicker %})
* [How to Resize Calendar Based on Input Width]({% slug howto_use_resize_calendar_basedon_input_width_datepicker %})
* [How to Restrict User Input to Min/Max Values]({% slug howto_restrict_user_input_minandmax_values_datepicker %})
* [How to Show Out-of-Range Dates as Disabled]({% slug howto_show_outofrange_dates_disabled_datepicker %})
* [How to Submit Forms on Enter]({% slug howto_submmit_forms_onenter_datepicker %})
