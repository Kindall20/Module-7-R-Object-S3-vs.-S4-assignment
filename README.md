# Module-7-R-Object-S3-vs.-S4-assignment
# Step 1

data("mtcars")
head(mtcars, 6)

# Step 2 

methods("summary")
summary(mtcars)  # Works because mtcars is a data frame

# Step 3
# Assign S3 class to mtcars
class(mtcars) <- "my_car_data"

# Check the class of mtcars after modification
class(mtcars)


# Define an S4 class called 'CarData'
setClass("CarData",
         slots = list(make = "character", mpg = "numeric", cyl = "numeric"))

# Create an S4 object using the new() function
s4_mtcars <- new("CarData", make = "Toyota", mpg = 25, cyl = 4)

# View the S4 object
s4_mtcars


# Question 5: In your GitHub, create two examples of S3 and S4.
# S3 Example
student <- list(name = "John Doe", age = 22, GPA = 3.8)
class(student) <- "student"

# Define a print method for the student class
print.student <- function(x) {
  cat("Student Name:", x$name, "\n")
  cat("Age:", x$age, "\n")
  cat("GPA:", x$GPA, "\n")
}

# Print the student object
print(student)

# S4 Example
setClass("student",
         slots = list(name = "character", age = "numeric", GPA = "numeric"))

# Create a new student object
s4_student <- new("student", name = "Jane Doe", age = 20, GPA = 3.9)

# Display the object
s4_student

