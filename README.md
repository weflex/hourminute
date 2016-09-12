HOUR MINUTE
===========

## Install

        npm install hourminute

Then copy `node_modules/hourminute/lib/index.d.ts` to your typings.


## Usage

- Constructing new HourMinute objects

        const anHourAndAHalf = new HourMinute({hour: 1, minute: 30});
        const twoHours = new HourMinute({hour: 2, minute: 0});

- Getting new HourMinute objects by adding or subtracting

        const threeHoursAndAHalf = anHourAndAHalf.adding(twoHours); // -> 3:30
        const halfAnHour = twoHours.subtracting(anHourAndAHalf);    // -> 0:30
        
- Mutating the original time

        const time = new HourMinute(twoHours);
        time.subtract(anHourAndAHalf);     // now `time` is 0:30
        time.add(twoHours);                // now `time` is 1:00

- Other convenient method for mutating original value

        time.addMinutes(5);                // now `time` is 1:05
        time.addHours(1);                  // now `time` is 2:05
        time.subtractMinutes(5);           // now `time` is 2:00
        time.subtractHours(1)              // now `time` is 1:00

- Exporting values

        time.hour                          // -> 2
        time.asMinutes()                   // -> 120
        time.minute                        // -> 0

- Chaining your mutating calls

        const threeHours = new HourMinute({hour: 1, minute: 0})
            .add(anHourAndAHalf)
            .addMinutes(30);


## Build from source

```bash
npm install && \
npm run typings && \
npm run build
```
