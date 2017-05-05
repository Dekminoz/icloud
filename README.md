icloud
======

Access the iCloud API

### usage 

```javascript
var icloud = require('icloud');

var instance = icloud();
instance.login("username", "password", function(err) {
    if (err) return console.log('login failed');
    ### for contacts
    instance.contacts(function(err, results) {
        if (err) return console.log('failed to fetch contacts');
        console.log(results.contacts);
    });
    ### for calendar events
    /*
        params is an nullable object it look like this : 
        { 
            lang:"fr-fr" (default:en-en),
            timezone : "Europe/Paris" (default:America/New_York)
            //use for period range
            startDate : "2017-01-01" (default: 2000-01-01),
            endDate: "2017-03-01" (default: 2100-01-01)
        }
    */
    instance.calendars(params,function(err, results) {
        if (err) return console.log('failed to fetch calendar events');
        console.log(results);
    });
});
```

### services

Contacts is the only service implemented so far. Pull-requests welcome.


### credits

The implementation is heavily inspired by [pycloud](https://github.com/picklepete/pyicloud/)