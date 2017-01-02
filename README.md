# PowerNapTimerApp
app to practice timer logic,  the delegate pattern, UIAlertController, and UILocalNotifications.


Delegate Pattern 
1. In Model Controller, create TimerDelegate protocol and set this delegate as a weak var delegate optional and call delegate functions in actions 
2. In View Controller, conform to protocol, in viewDidLoad assign the delegate as self 

Alert Controllers - two types, alerts and action sheets that pop up from the bottom. Add text fields to UIAlertControllers that will use a number pad as its keyboard so that users can add however minutes they want at the end of a nap as a "snooze" 
1. In ViewController, initialize UIAlertController, addTextField and give properties to our alertController i.e. placeholder text, keyboardType, initialize different types of actions using UIAlertAction and then add these actions and finally use present(alertController...) to present alert 

UILocalNotifications 
1. In ViewController, create two functions- scheduleLocalNotification and cancelLocalNotification. Add properties .alertBody, .category, .fireDate and schedule notification UIApplication.shared.scheduleLocalNotifiication(localNotifiation) and call this function when the timer is complete in another function in the VC. In cancelLocalNotifications, UIApplication.shared.cancelAllLocalNotification(). 
2. In AppDelegate,register your local notification user settings in didFinishLaunchingWithOptions
Create a local notification when the timer starts that will fire when time is up. 
    {
        let settings = UIUserNotificationSettings(types: [.alert, .badge, .sound], categories: nil)
        UIApplication.shared.registerUserNotificationSettings(settings)
        return true
    }
