# Navigate-to-Specific-TabBarController-tab-from-other-ViewController-Not-ChildTabViewControllers-
This  Guide will help you to naviagte to the specific TabBar ViewController from Other View Controllers on Button Click .


* Assign a Viewcontroller Class to Base TabBarController.
* Initialize a Variable of type String (For Check Purpose)
* Apply Check to Navigate To the Desired Tab BAr View Controller if the String Value Matches 
```swift

import UIKit

class BaseTabBarViewController: UITabBarController {

var isComingFrom = String()

    override func viewDidLoad() {
        super.viewDidLoad()
        
        //Apply Check and Naviagte to Desired tabBar View Controller
        if isComingFrom == "Settings" {
            
            selectedIndex = 1 //enter Desired Index According to your Need (Starts From 0)
            
        }
      }
}
```

* Now Assign  String Value("Settings") to the Variable(isComingFrom) in Your View Controller From where u want to navigate to Specific tabBar ViewController

```swift
import UIKit

class OtherViewController: UITabBarController {

    //MARK: Navigate On Button Press
    @IBAction func buttonMyPreference(_ sender: Any) {
            print("button pressed")
        
        //To access the  Specific tabBar ViewController
        let tabBarController = storyboard?.instantiateViewController(withIdentifier: "GAtHomeTabbarViewController") as! GAtHomeTabbarViewController
        tabBarController.isComingFrom = "Settings" // Assign the Value to Validate in HomeTabBarViewController Class
        self.navigationController?.pushViewController(tabBarController, animated: true)
    }
}
```
* Thats it . Now it will Navigate you on your desired index of TabBarViewController
