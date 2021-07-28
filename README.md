# basha-game-of-life

%pylab inline
import numpy as np
import matplotlib.pyplot as plt
Populating the interactive namespace from numpy and matplotlib

start = np.array([[1,0,0,0,0,0],
                  [0,0,0,1,0,0],
                  [0,1,0,1,0,0],
                  [0,0,1,1,0,0],
                  [0,0,0,0,0,0],
                  [0,0,0,0,0,1]])

plt.imshow(start, interpolation='nearest', cmap="gray")
Out[5]:
<matplotlib.image.AxesImage at 0x105aa48d0>


print start[4:8,4:8]  # neighbours of start[5,5]
print start[1:4,1:4]  # neighbours of start[2,2]
#print start[?:?]  # neighbours of start[1,1]
#print start[?:?] # neighbours of start[0,0]
[[0 0]
 [0 0]]
[[0 0 1]
 [1 0 1]
 [0 1 1]]

live_neighbours = np.empty(start.shape)
for index, value in np.ndenumerate(start):
    #Need to add 2, becase the slicing works like 'up to but not including'
    x0 = max(0,(index[0]-1))
    x1 = max(0,(index[0]+2))
    y0 = max(0,(index[1]-1))
    y1 = max(0,(index[1]+2))
    subarray = start[x0:x1, y0:y1]
    live_neighbours[index] = subarray.sum() - value # need to subtract actual value at that cell...

live_neighbours
Out[15]:
array([[ 0.,  1.,  1.,  1.,  1.,  0.],
       [ 2.,  2.,  3.,  1.,  2.,  0.],
       [ 1.,  1.,  5.,  3.,  3.,  0.],
       [ 1.,  2.,  3.,  2.,  2.,  0.],
       [ 0.,  1.,  2.,  2.,  1.,  0.],
       [ 0.,  0.,  0.,  0.,  0.,  0.]])
def get_neighbours(start):
"""
This function gets the number of live neighbours in the binary array start
start : np.ndarray
"""
In [ ]:
def game_of_life(start, n):
    """
    this function runs the game of life for n steps...
    start : np.ndarray (0s and 1s)
    n: int number of steps 
    """
    assert (1>= start.min() >= 0) and (1>= start.max() >= 0), "array must be ones and zeros"
    
    current = np.copy(start)
    
    while n:
        neighbours = get_neighbours(current)
        
        for index, value in np.ndenumerate(current):
            print(index, value)
            # Apply the rules to current
            if ...
            
            else ...
            
        n -= 1 
            
            
    return current
