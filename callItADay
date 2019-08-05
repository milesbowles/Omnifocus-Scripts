# Set date/time to beginning of the day (12:00am)
set dayStart to (current date) - (time of (current date))
# Set date/time to end of the day (12:00pm)
set dayEnd to dayStart + (24 * hours)

# Access Omnifocus
tell application "OmniFocus"
	tell front document
		# Get all tasks due today
		set taskList to every flattened task whose due date is greater than dayStart and due date is less than dayEnd
		# Add 24 hours to each tasks due date
		repeat with x from 1 to length of taskList
			set currentTask to item x of taskList
			set newDueDate to (due date of currentTask) + (24 * hours)
			set due date of currentTask to newDueDate
		end repeat
	end tell
end tell
