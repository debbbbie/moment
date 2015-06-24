## customerize fromNow output
## e.g. 3小时42分钟
```

        from: function(time, withoutSuffix) {
            var d = moment.duration({
                to: this,
                from: time
            }).locale(this.locale());
            var output = d.humanize(!withoutSuffix);
            if((Math.abs(d._data.years) + Math.abs(d._data.months) + Math.abs(d._data.days) == 0 ) &&
                Math.abs(d._data.hours) != 0 ){
                output = d.humanize(false);
                d._milliseconds -= (d._data.hours * 3600000);
                output += d.humanize(!withoutSuffix);
            }
            return output;
        },
```
