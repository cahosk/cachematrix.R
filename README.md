# cachematrix.R
## Put comments here that give an overall description of what your
## functions do
##create a special "matrix" object that can cache its inverse and compute the inverse
## Write a short comment describing this function
##creates a special "matrix" object that can cache its inverse
makeCacheMatrix <- function(x = matrix()) {
inv <- NULL
set <- function(y){
x <<- y
inv <<- NULL

}

get <- function() x
setInverse <- function(solveMatrix) inv <<- solveMatrix
getInverse <- function() inv
list(set = set, get = get, setInverse = setInverse, getInverse = getInverse)

}


## Write a short comment describing this function
##function computing the inverse of the special matrix returned by the above function
cacheSolve <- function(x, ...) {
        ## Return a matrix that is the inverse of 'x'
}
cacheSolve <- function(x, ...) {
inv <- x$getInverse()
if(!is.null(inv)){
message("getting cached data")
return(inv)
}
data <- x$get()
inv <- solve(data)
x$setInverse(inv)
inv 

}
