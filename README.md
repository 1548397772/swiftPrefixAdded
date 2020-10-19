struct PPStruct<Base> {
    var ppIvar: Base
    init(_ ppIvar: Base) {
        self.ppIvar = ppIvar
    }
}

protocol PPProtocol { }

extension PPProtocol{
    var pp: PPStruct<Self> {
        get {PPStruct(self)}
        set {}
    }
    static var pp: PPStruct<Self>.Type{
        get{ PPStruct<Self>.self }
        set{}
    }
}

extension String : PPProtocol{}

extension PPStruct where Base == String{
    var numberOfCharacterisic: Int {
        // do sth
        return 0
    }
}

extension PPStruct where Base == UIButton{
    var clickBtn: UIButton {
        //do sth
        return ppIvar
    }
    
}
