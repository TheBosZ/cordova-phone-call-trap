Cordova PhoneCall Trap
=======================

It is a Apache Cordova plugin to simplify handling phone call status and events in Android devices.
I've integrated some Pull Requests, as those of @alkoschuster.
The original project is available here: ichirkin/cordova-phone-call-trap


## Install

    $ cordova plugin add https://github.com/ichirkin/cordova-phone-call-trap.git


## Quick Example

    PhoneCallTrap.onCall(function(state, phone) {
        console.log("CHANGE STATE: " + state);

        switch (state) {
            case "RINGING":
                console.log("Phone is ringing");
                console.log(phone);
                break;
            case "OFFHOOK":
                console.log("Phone is off-hook");
                break;

            case "IDLE":
                console.log("Phone is idle");
                break;
        }
    });
	
## Reject call

    PhoneCallTrap.rejectCall(function() {
        console.log("SUCCESSFULLY REJECTED");
    }, function(error) {
        console.error("THERE WAS AN ERROR REJECTING", error);
    });
	
## Silence call

    PhoneCallTrap.silenceCall(function() {
        console.log("SUCCESSFULLY SILENCED");
    }, function(error) {
        console.error("THERE WAS AN ERROR SILENCING", error);
    });

## Supported platforms

- Android 2.3.3 or higher
- IOS


## References

We have tried PhoneListener but it is only compatible with Phonegap 1.6 and does not work with new Apache Cordova versions. Also, its deployment isn't as easy as an Apache Cordova plugin should be. We are thankful for their work, though.

https://github.com/devgeeks/PhoneListener


## License

Cordova PhoneCall Trap is released under the [MIT License](http://www.opensource.org/licenses/MIT).
