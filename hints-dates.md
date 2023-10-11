## Parse a date string into a ```date``` object
```python
from datetime import datetime, date

date_string = '2022-12-04'

start = datetime.strptime(date_string, '%Y-%m-%d').date()
```

## Loop dates without an additional package
```python
from datetime import date, timedelta

current = date(2022, 12, 1)
end = date(2022, 12, 31)
delta = timedelta(days=1)

while current <= end:
    print(current)
    current += delta
```

## Loop date with ```dateutil``` package

Install the ```dateutil``` package

```bash
$ pip install python-dateutil
```

Use the package

```python
from datetime import date
from dateutil import rrule

start = date(2022, 12, 1)
end = date(2022, 12, 31)

for day in list(rrule.rrule(freq=rrule.DAILY, dtstart=start, until=end)):
    print(day.date())
```
