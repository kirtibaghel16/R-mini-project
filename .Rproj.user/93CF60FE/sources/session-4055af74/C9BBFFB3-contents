# HR Employee Records Merging
# Merges employees.csv and employee_details.csv on emp_id

library(dplyr)
library(readr)

# Load datasets
employees       <- read_csv("data/employees.csv")
employee_details <- read_csv("data/employee_details.csv")

cat("employees rows:", nrow(employees), "\n")
cat("employee_details rows:", nrow(employee_details), "\n")

# --- Join Types ---

# Inner join: only employees present in BOTH datasets
inner_merged <- inner_join(employees, employee_details, by = "emp_id")

# Left join: all employees, NAs for missing details
left_merged <- left_join(employees, employee_details, by = "emp_id")

# Full join: all records from both datasets
full_merged <- full_join(employees, employee_details, by = "emp_id")

cat("\nInner join rows:", nrow(inner_merged),
    "\nLeft join rows:",  nrow(left_merged),
    "\nFull join rows:",  nrow(full_merged), "\n")

# --- Save outputs ---
write_csv(inner_merged, "output/inner_merged.csv")
write_csv(left_merged,  "output/left_merged.csv")
write_csv(full_merged,  "output/full_merged.csv")

cat("\nFiles saved to output/\n")

# --- Quick summary of full merged dataset ---
print(summary(full_merged[, c("salary", "performance_rating")]))
