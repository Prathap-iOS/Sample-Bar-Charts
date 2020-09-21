//
//  ViewController.swift
//  SampleCharts
//
//  Created by Prathap Reddy on 17/09/20.
//

import UIKit
import Charts

class ViewController: UIViewController, ChartViewDelegate {

    @IBOutlet weak var barChart: BarChartView!
    override func viewDidLoad() {
        super.viewDidLoad()
        
        self.barChart.delegate = self
        
        let sales = DataGenerator.data()
        
        var salesEntries = [BarChartDataEntry]()
        
        var salesMonths = [String]()
        
        var i = 0
        
        for sale in sales {
            let saleEntry = BarChartDataEntry(x: Double(i), y: sale.value)
            salesEntries.append(saleEntry)
            
            salesMonths.append(sale.month)
            
            i += 1
        }
        
        let chartDataSet: BarChartDataSet = BarChartDataSet(entries: salesEntries, label: "km")
        let chartData = BarChartData(dataSets: [chartDataSet])
        barChart.data = chartData
        
        //Lable position, Min and Max Values
        barChart.xAxis.labelPosition = .bottom
        barChart.leftAxis.axisMinimum = 0.0
        barChart.leftAxis.axisMaximum = 1000.0
        
        //Proviede colors to Charts
        chartDataSet.colors = [.red, .yellow, .green]
        chartDataSet.colors = ChartColorTemplates.joyful()
        
        //To disable legend at bottom
        barChart.legend.enabled = false
        
        //Pinch and Double tap to Zoom
        barChart.scaleYEnabled = false
        barChart.scaleXEnabled = false
        barChart.pinchZoomEnabled = false
        barChart.doubleTapToZoomEnabled = false
        
        //To chhosing bars by tapping them
        barChart.highlighter = nil
        
        //To Disable right axis and Grid lines
        barChart.rightAxis.enabled = false
        barChart.xAxis.drawGridLinesEnabled = false
    }
}

