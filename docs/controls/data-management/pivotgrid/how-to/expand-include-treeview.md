---
title: Expand Include fields TreeView
page_title: Expand Include fields TreeView | Kendo UI PivotGrid Widget
description: "Learn how to access the Include fields TreeView widget and expand the root node on window open in a Kendo UI PivotGrid widget."
slug: howto_expand_include_fields_treeview_pivotgrid
---

# Expand Include fields TreeView

The example below demonstrates how to access the **Include fields** TreeView widget and expand the root node on a window `open` event.

###### Example

```html
<div id="example">
    <div id="configurator"></div>
    <div id="pivotgrid"></div>

    <script>
        $(document).ready(function () {
            var pivotgrid = $("#pivotgrid").kendoPivotGrid({
                filterable: true,
                sortable: true,
                columnWidth: 200,
                height: 580,
                dataSource: {
                    type: "xmla",
                    columns: [{ name: "[Date].[Calendar]", expand: true }, { name: "[Product].[Category]" } ],
                    rows: [{ name: "[Geography].[City]" }],
                    measures: ["[Measures].[Reseller Freight Cost]"],
                    transport: {
                        connection: {
                            catalog: "Adventure Works DW 2008R2",
                            cube: "Adventure Works"
                        },
                        read: "//demos.telerik.com/olap/msmdpump.dll"
                    },
                    schema: {
                        type: "xmla"
                    },
                    error: function (e) {
                        alert("error: " + kendo.stringify(e.errors[0]));
                    }
                }
            }).data("kendoPivotGrid");

            $("#configurator").kendoPivotConfigurator({
                dataSource: pivotgrid.dataSource,
                filterable: true,
                sortable: true,
                height: 580
            });

            //wire 'Include fields' open
            $("[data-role=pivotsettingtarget]").each(function(_, setting) {
              var fieldMenu = $(setting).data("kendoPivotSettingTarget").fieldMenu; //get setting FieldMenu

              if (fieldMenu) {
                fieldMenu.includeWindow.bind("open", function() { //wire open event of the 'Include Fields' window
                  var treeView = fieldMenu.treeView;
                  if (treeView) {
                    treeView.one("dataBound", function() {
                      treeView.expand(".k-item:first"); //Expand the root node
                    });
                  }
                });
              }
            });
        });
    </script>
</div>
```

## See Also

Other articles on Kendo UI PivotGrid and how-to examples:

* [JavaScript API Reference](/api/javascript/ui/pivotgrid)
* [How to Access MDX Query]({% slug howto_access_mdx_query_pivotgrid %})
* [How to Add Dimension to Column Axis]({% slug howto_add_dimension_column_axis_pivotgrid %})
* [How to Change Data Source Dynamically]({% slug howto_change_datasource_dynamically_pivotgrid %})
* [How to Drill Down Navigation Always Starting from Root Tuple]({% slug howto_drill_down_navigation_startingfrom_root_tuple_pivotgrid %})
* [How to Expand Multiple Column Dimensions]({% slug howto_expand_multiple_column_dimensions_pivotgrid %})
* [How to Filter by Using the include Operator]({% slug howto_use_include_operator_pivotgrid %})
* [How to Filter Dimensions]({% slug howto_filter_dimensions_pivotgrid %})
* [How to Integrate with Kendo UI Chart]({% slug howto_integratewith_kendoui_chart_pivotgrid %})
* [How to Make the Include fields Window Modal]({% slug howto_make_include_fields_window_modal_pivotgrid %})
* [How to Modify Exported Excel Files]({% slug howto_modify_exported_excel_files_pivotgrid %})
* [How to Modify Measure Tag Captions]({% slug howto_modify_measure_tag_captions_pivotgrid %})
* [How to Reload PivotGrid Configuration Options]({% slug howto_reload_configuration_options_pivotgrid %})
* [How to Render Row Header Caption As Anchor]({% slug howto_render_rowheader_captionas_anchor_pivotgrid %})
* [How to Right-Align Text]({% slug howto_right_align_text_pivotgrid %})
* [How to Show Tooltip with Data Cell Information]({% slug howto_show_tooltip_withdata_cellinformation_pivotgrid %})
* [How to Sort Dimensions]({% slug howto_sort_dimensions_pivotgrid %})
* [How to Translate PivotConfigurator Field Items]({% slug howto_translate_pivotconfigurator_messages_pivotgrid %})
* [How to Translate PivotGrid Messages]({% slug howto_translate_pivotgrid_messages_pivotgrid %})
