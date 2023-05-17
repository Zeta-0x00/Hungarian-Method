# Hungarian Method
 A implementartion of the Kuhn–Munkres algorithm or Munkres assignment algorithm, also known as the Hungarian Method.
 This implementation it's entirely in PyTorch


## Example cases
### Case 1
```haskell
Cost Function 1:
tensor([[ 90.,  75.,  75.,  80.],
        [ 35.,  85.,  55.,  65.],
        [125.,  95.,  90., 105.],
        [ 45., 110.,  95., 115.]])
```
### Case 2
```haskell
Cost Function 2:
tensor([[ 1.,  8., 15., 22.],
        [13., 18., 23., 28.],
        [13., 18., 23., 28.],
        [19., 23., 27., 31.]])
```
### Solution case 1
```rust
First
tensor([[ 90.,  75.,  75.,  80.],
        [ 35.,  85.,  55.,  65.],
        [125.,  95.,  90., 105.],
        [ 45., 110.,  95., 115.]])

Initialized Solution:
tensor([[15.,  0.,  0.,  0.],
        [ 0., 50., 20., 25.],
        [35.,  5.,  0., 10.],
        [ 0., 65., 50., 65.]])

Is optimal? 	False
Rows marked: 	[0]
Cols marked: 	[0, 2]
new iteration 
tensor([[20.,  0.,  5.,  0.],
        [ 0., 45., 20., 20.],
        [35.,  0.,  0.,  5.],
        [ 0., 60., 50., 60.]])

Is optimal? 	False
Rows marked: 	[0, 2]
Cols marked: 	[0]
new iteration 
tensor([[40.,  0.,  5.,  0.],
        [ 0., 25.,  0.,  0.],
        [55.,  0.,  0.,  5.],
        [ 0., 40., 30., 40.]])

Optimal = True
Assesments: 	[tensor(45.), tensor(75.), tensor(90.), tensor(65.)]
Solution:	275.0
```
### Solution case 2
```rust
First
	tensor([[ 1.,  8., 15., 22.],
        [13., 18., 23., 28.],
        [13., 18., 23., 28.],
        [19., 23., 27., 31.]])
Initialized Solution:
	tensor([[0., 3., 6., 9.],
        [0., 1., 2., 3.],
        [0., 1., 2., 3.],
        [0., 0., 0., 0.]])

Is optimal? 	False
Rows marked: 	[3]
Cols marked: 	[0]
new iteration 
tensor([[0., 2., 5., 8.],
        [0., 0., 1., 2.],
        [0., 0., 1., 2.],
        [1., 0., 0., 0.]])

Is optimal? 	False
Rows marked: 	[3]
Cols marked: 	[0, 1]
new iteration 
tensor([[0., 2., 4., 7.],
        [0., 0., 0., 1.],
        [0., 0., 0., 1.],
        [2., 1., 0., 0.]])

Optimal = True
Assesments: 	[tensor(1.), tensor(18.), tensor(23.), tensor(31.)]
Solution:	73.0
```