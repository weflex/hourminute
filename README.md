HOUR-MINUTE.js
==============

## Install

```bash
npm install hourminute
```

Then copy `node_modules/hourminute/lib/index.d.ts` to your typings.


## Usage

- Constructing new HourMinute objects

        const anHourAndAHalf = new HourMinute({hour: 1, minute: 30});
        const twoHours = new HourMinute({hour: 2, minute: 0});

- Getting new HourMinute objects by adding or subtracting

        const threeHoursAndAHalf = anHourAndAHalf.adding(twoHours); // -> 3:30
        const halfAnHour = twoHours.subtracting(anHourAndAHalf);    // -> 0:30
        
- Mutating the original time

        twoHours.subtract(anHourAndAHalf); // now `twoHours` is 0:30
        twoHours.add(twoHours);            // now `twoHours` is 1:00

- Other convenient method for mutating original value

        anHourAndAHalf.addMinutes(5)       // now `anHourAndAHalf` is 1:35
        anHourAndAHalf.addHours(1)         // now `anHourAndAHalf` is 2:35
        anHourAndAHalf.subtractMinutes(5)  // now `anHourAndAHalf` is 2:30
        anHourAndAHalf.subtractHours(2)    // now `anHourAndAHalf` is 1:30

- Chaining your mutating calls

        const threeHours = new HourMinute({hour: 1, minute: 0})
            .add(anHourAndAHalf)
            .addMinutes(30);

- Exporting values

        threeHours.hour                    // -> 3
        threeHours.asMinutes()             // -> 180
        threeHours.minute                  // -> 0


## Build from source

```bash
npm install && \
npm run typings && \
npm run build
```
