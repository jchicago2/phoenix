import datetime

# Get the current year
current_year = datetime.datetime.now().year

# Function to get all dates for a specified year and weekday
def get_weekdays_for_year(year, weekday):
    dates = []
    # Start from the first day of the year
    d = datetime.datetime(year, 1, 1)
    # Find the first occurrence of the specified weekday
    d += datetime.timedelta(days=(weekday - d.weekday() + 7) % 7)
    while d.year == year:
        dates.append(d.strftime("%A, %Y-%m-%d"))
        d += datetime.timedelta(days=7)
    return dates

# Generate a list of all days of the week for the current year
all_days_of_week = []
weekdays = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"]
for i, day in enumerate(weekdays):
    all_days_of_week.extend(get_weekdays_for_year(current_year, i))

# Print the list of days with dates
for day_with_date in sorted(all_days_of_week):
    print(day_with_date)
