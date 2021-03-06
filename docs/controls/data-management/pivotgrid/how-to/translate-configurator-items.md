---
title: Translate PivotConfigurator Messages
page_title: Translate PivotConfigurator Messages | Kendo UI PivotGrid Widget
description: "Learn how to access PivotConfigurator TreeView widget and rename the Measures and KPIs messages in a Kendo UI PivotGrid widget."
slug: howto_translate_pivotconfigurator_messages_pivotgrid
---

# Translate PivotConfigurator Messages

The example below demonstrates how to access PivotConfigurator TreeView widget and rename the **Measures** and **KPIs** messages.

###### Example

```html
<div id="example">
    <div id="configurator"></div>

    <script>
        $(document).ready(function () {
            var ds = new kendo.data.PivotDataSource({
                type: "xmla",
                columns: [{ name: "[Date].[Calendar]", expand: true }, { name: "[Product].[Category]" } ],
                rows: [{ name: "[Geography].[City]" }],
                measures: ["[Measures].[Reseller Freight Cost]"],
                transport: {
                    connection: {
                        catalog: "Adventure Works DW 2008R2",
                        cube: "Adventure Works"
                    },
                    read: "http://demos.telerik.com/olap/msmdpump.dll"
                },
                schema: {
                    type: "xmla"
                },
                error: function (e) {
                    alert("error: " + kendo.stringify(e.errors[0]));
                }
            });

            var configurator = $("#configurator").kendoPivotConfigurator({
                dataSource: ds,
                filterable: true,
                sortable: true,
                height: 580
            }).getKendoPivotConfigurator();

            var source = configurator.treeView.dataSource;

            source.one("change", function() {
              source.get("[Measures]").set("caption", "Translaged Measures");
              source.get("[KPIs]").set("caption", "Translaged KPIs");
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
* [How to Expand the Include fields TreeView]({% slug howto_expand_include_fields_treeview_pivotgrid %})
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
* [How to Translate PivotGrid Messages]({% slug howto_translate_pivotgrid_messages_pivotgrid %})
