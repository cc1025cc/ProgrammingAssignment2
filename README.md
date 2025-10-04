## This funciton creates a "matrix" object that can cache its inverse
make_cache_matrix <-function(x=matrix()) {
inv <- NULL
## Function to set the matrix
set <- function(y) {
x<<-y 
inv<<-NULL #Reset the inverse when a new matrix is set
#Function to get the matrix
get<- function() x
#Function to set the inverse
setInverse<- function(inverse) inv<<-inverse
## This function is to get the inverse
getInverse<-function()inv
## Return a list of functions
list(set=set, get=get, 
     setInverse=setInverse
     getInverse=getInverse)
}
