//
//  HorizontalBarChartRenderer.swift
//  Charts
//
//  Copyright 2015 Daniel Cohen Gindi & Philipp Jahoda
//  A port of MPAndroidChart for iOS
//  Licensed under Apache License 2.0
//
//  https://github.com/danielgindi/Charts
//

import Foundation
import CoreGraphics

#if !os(OSX)
    import UIKit
#endif


open class HorizontalGradientBarChartRenderer: HorizontalBarChartRenderer
{
    public var fillColors:[CGColor] = [UIColor.white.withAlphaComponent(0.0).cgColor,
                                       UIColor.white.withAlphaComponent(0.0).cgColor];
    public var locations:[CGFloat] = [0, 1];
    
        open override func drawDataSet(context: CGContext, dataSet: IBarChartDataSet, index: Int)
    {
        super.drawDataSet(context: context, dataSet: dataSet, index: index)

        context.clip();

        let gradient:CGGradient;
        let colorspace:CGColorSpace;
        colorspace = CGColorSpaceCreateDeviceRGB();

        gradient = CGGradient(colorsSpace: colorspace, colors: fillColors as CFArray, locations: locations)!;
        //Vertical Gradient
        let startPoint : CGPoint = CGPoint(x: viewPortHandler.contentLeft, y: 0.0);
        let endPoint : CGPoint = CGPoint(x: viewPortHandler.contentRight, y: 0.0);
        //Horizontal Gradient
        //let startPoint : CGPoint = CGPointMake(0.0, 0.0);
        //let endPoint : CGPoint = CGPointMake(viewPortHandler.contentLeft, 0.0);

        context.drawLinearGradient(gradient,
                                   start: startPoint, end: endPoint, options: CGGradientDrawingOptions.drawsBeforeStartLocation);

        context.restoreGState()
    }
}
