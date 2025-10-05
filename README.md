## Comment 1: This funciton creates a "matrix" object that can cache its inverse. It innvolves, setting the value of the matrix, getting the value of the matrix, settting the value of the inverse, and getting the value of the inverse. 
make_cache_matrix <-function(x=matrix()) {
inv <- NULL
set <- function(y) {
x << -y 
inv << -NULL 
}
get <- function() x
setInverse <- function(inverse) inv <<- inverse
getInverse <- function() inv

list(set = set, get = get, 
     setInverse = setInverse
     getInverse = getInverse)
}
## Comment 2: This function computes the inverse of the "matrix" created from the function that is listed above. It will primarily check if the inverse has been calculated and if it has, it will get the inverse from the cache and not perform the computation. If the inverse has not been calculated, it will calulate the inverse and set its valuue in the cache through the setinverse function. 
cachesolve <- function(x, ...) {
inv <- x$getinv()
if(!is.null(inv)){
message("getting cached inverse")
return(inv)
}
mat<-x$get()
inv<- solve(mat, ...)  
x$setInverse(inv)
inv
}
