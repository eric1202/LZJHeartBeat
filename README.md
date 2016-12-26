###How to use

just copy this code 
	 
	
	extension UIView{
    func drawTest() -> () {
        
        
        let layer = CAShapeLayer()
        let bp = UIBezierPath()
        let kwidth = self.frame.size.width
        let kheight = self.frame.size.height
        
        bp.move(to: CGPoint.init(x: 0.01*kwidth, y: 0.5*kheight))
        bp.addLine(to: CGPoint.init(x: 0.3*kwidth, y: 0.5*kheight))
        bp.addLine(to: CGPoint.init(x: 0.33*kwidth, y: 0.47*kheight))
        bp.addLine(to: CGPoint.init(x: 0.38*kwidth, y: 0.54*kheight))
        bp.addLine(to: CGPoint.init(x: 0.44*kwidth, y: 0.5*kheight))
        bp.addLine(to: CGPoint.init(x: 0.50*kwidth, y: 0.30*kheight))
        bp.addLine(to: CGPoint.init(x: 0.56*kwidth, y: 0.57*kheight))
        bp.addLine(to: CGPoint.init(x: 0.61*kwidth, y: 0.5*kheight))
        bp.addLine(to: CGPoint.init(x: 0.7*kwidth, y: 0.5*kheight))
        bp.addLine(to: CGPoint.init(x: 0.75*kwidth, y: 0.48*kheight))
        bp.addLine(to: CGPoint.init(x: 0.80*kwidth, y: 0.5*kheight))
        bp.addLine(to: CGPoint.init(x: 0.99*kwidth, y: 0.5*kheight))
        
        layer.path = bp.cgPath
        layer.fillColor = UIColor.clear.cgColor
        layer.strokeColor = UIColor.red.cgColor
        layer.lineWidth = kwidth/360.0
        self.layer.addSublayer(layer)
        
        let an = CABasicAnimation.init(keyPath: "strokeEnd")
        an.duration = 1
        an.fromValue = 0
        an.toValue = 1
        an.timingFunction = CAMediaTimingFunction.init(name: kCAMediaTimingFunctionEaseInEaseOut)
        an.autoreverses = false
        an.repeatCount = MAXFLOAT
        layer .add(an, forKey: "heartbeat")
        print(layer.lineWidth)
    }

