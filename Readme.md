The following example exports a chart as an image to the XLS document. In this example, the form contains the _Export to File_ and _Export to Stream_ buttons that allow you to save the XLS document with the chart image to a file or a stream. Follow the steps below to implement this scenario:

* [Add](xref:2957) a [Chart Control](xref:DevExpress.XtraCharts.ChartControl) object to the form. Make sure that this Chart Control _Name_ is _chartControl1_ in the Visual Studio _Properties_ window. 

* Create a [Series](xref:DevExpress.XtraCharts.Series) object and pass [ViewType.Bar](xref:DevExpress.XtraCharts.ViewType.Bar) as a constructor parameter  in the _Form1_Load_ event handler. Use the [ChartControl.Series.Add](xref:DevExpress.XtraCharts.SeriesCollection.Add(DevExpress.XtraCharts.Series)) method to add this series to the chart.

* Call the _GetSales_ method and set its result to the [ChartControl.DataSource](xref:DevExpress.XtraCharts.ChartControl.DataSource) property. Specify the [Series.ArgumentDataMember](xref:DevExpress.XtraCharts.SeriesBase.ArgumentDataMember) and [Series.ValueDataMembers](xref:DevExpress.XtraCharts.SeriesBase.ValueDataMembers) properties to populate the chart with data.

* Add two [SimpleButtons](xref:DevExpress.XtraEditors.SimpleButton) to the form. Set the first button [Text](xref:DevExpress.XtraEditors.SimpleButton.Text) property to _Export to File_ and the second one - _Export to Stream_. 

* The Chart Control uses the [DevExpress Printing Library](xref:2079) to export a chart. To use this library, add references to the following assemblies to the project: _DevExpress.XtraPrinting.<:xx.x:>_, _DevExpress.Printing.v<:xx.x:>.Core_.

* Handle the first button's [Click](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.control.click?view=net-5.0) event and use the [ChartControl.IsPrintingAvailable](xref:DevExpress.XtraCharts.ChartControl.IsPrintingAvailable) property to check whether the chart can be exported. Call the [ChartControl.ExportToXls(System.String)](xref:DevExpress.XtraCharts.ChartControl.ExportToXls(System.String)) method to export the chart to a file. Pass the path to this file as a parameter to this method.

* Handle the second button's [Click](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.control.click?view=net-5.0) event and use the [ChartControl.IsPrintingAvailable](xref:DevExpress.XtraCharts.ChartControl.IsPrintingAvailable) property to check whether the chart can be exported. Call the [ChartControl.ExportToXls(System.IO.Stream)](xref:DevExpress.XtraCharts.ChartControl.ExportToXls(System.IO.Stream)) method to export the chart to a stream. This example uses [FileStream](https://docs.microsoft.com/en-us/dotnet/api/system.io.filestream?view=net-5.0), and you can open the file where the stream is saved to check the export result.
