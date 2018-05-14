# DemoTiles

**This is demo project to show how integrate 2GIS tiles in Apple Maps**

You should set in your Info.plist file to be able download our tiles.

```
<key>NSAppTransportSecurity</key>
<dict>
<key>NSAllowsArbitraryLoads</key>
<true/>
</dict>

```

You should use `DGSTileOverlay` in your ViewController to render our tiles


```
import MapKit

class ViewController: UIViewController, MKMapViewDelegate {

func viewDidLoad() {
let mapView = MKMapView()
mapView.delegate = self
let tilesOverlay = DGSTileOverlay()
mapView.insert(tilesOverlay, at: 0, level: .aboveLabels)
self.view.addSubview(self.mapView)
}

// MARK: MKMapViewDelegate

public func mapView(_ mapView: MKMapView, rendererFor overlay: MKOverlay) -> MKOverlayRenderer {
return MKTileOverlayRenderer(overlay: overlay)
}

}
```

## Images
### Tiles map example
<img src="https://github.com/2gis/iOS-SDKs-for-tiles/blob/master/Images/Tiles.png?raw=true" width="200">

### Web map example
<img src="https://github.com/2gis/iOS-SDKs-for-tiles/blob/master/Images/Web.png?raw=true" width="200">

