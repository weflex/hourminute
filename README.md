HOUR MINUTE
===========

## Installation

        npm install hourminute

For TypeScript projects, you have to do a few more things:

        typings install
        mkdir -p typings/global/hourminute
        cp node_modules/hourminute/lib/index.d.ts typings/globals/hourminute/
        echo '/// <reference path="globals/hourminute/index.d.ts" />' >> typings/index.d.ts


## Usage

- Import

        import hourminute from 'hourminute';

- Constructing hourminute objects

        const anHourAndAHalf = hourminute({hour: 1, minute: 30});
        const twoHours = hourminute({hour: 2, minute: 0});

- Getting new HourMinute objects by adding or subtracting

        const threeHoursAndAHalf = anHourAndAHalf.adding(twoHours); // -> 3:30
        const halfAnHour = twoHours.subtracting(anHourAndAHalf);    // -> 0:30
        
- Mutating the original time

        const time = hourminute(twoHours);
        time.subtract(anHourAndAHalf);     // now `time` is 0:30
        time.add(twoHours);                // now `time` is 2:30

- Other convenient method for mutating original value

        time.addMinutes(5);                // now `time` is 2:35
        time.addHours(1);                  // now `time` is 3:35
        time.subtractMinutes(5);           // now `time` is 3:30
        time.subtractHours(1)              // now `time` is 2:30

- Exporting values

        time.hour                          // -> 2
        time.asMinutes()                   // -> 120
        time.minute                        // -> 0

- Chaining your mutating calls

        const threeHours = hourminute({hour: 1, minute: 0})
            .add(anHourAndAHalf)
            .addMinutes(30);

- Convert HourMinute to String

        threeHours.format();               // -> "03:00"


## Build from source

```bash
npm install && \
npm run typings && \
npm run build
```
