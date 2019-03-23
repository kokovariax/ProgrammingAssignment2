
<!-- -->
## Put comments here that give an overall description of what your
## functions do
## These functions written in partial fulfillment of Coursera Data Science: R Programming 
## Week 3 Assignment;March 2019; GitHub user: kokovariax


## This function creates a special "matrix" object that can cache its inverse

   makeCacheMatrix <- function(x = matrix()) { 
       inv <- NULL   
    set <- function(y) {                    
        x <<- y                             
        inv <<- NULL                        
    }
    get <- function() x                   
    setinverse <- function(inverse) inv <<- inverse     
    getinverse <- function() inv                        
    list(set = set, get = get, setinverse = setinverse, getinverse = getinverse) 
}



## This function computes the inverse of the special "matrix" returned by makeCacheMatrix above.
## If the inverse has already been calculated (and the matrix has not changed),
## then cacheSolve will retrieve the inverse from the cache

    cacheSolve <- function(x, ...) {        
    inv <- x$getinverse()
    if(!is.null(inv)) {
        message("getting cached data")
        return(inv)
    }
    data <- x$get()
    inv <- solve(data, ...)
    x$setinverse(inv)
    inv
}


