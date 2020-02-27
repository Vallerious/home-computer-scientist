# Graph algorithms pseudocode

## DFS (recursive)
1. Initialize static boolean array with the size == number of nodes in graph.
2. Create a method that accepts current node and searched node.
3. Base case 1 - current node == searched node.
4. Base case 2 - alreaddy visited this node.
5. Mark as visited and print/add to collection current node.
6. Iterate children of current node.
7. Execute recursively for each not-visited child.

## BFS (recursive)
1. Initialize static boolean array with the size == number of nodes in graph.
2. Initialize static Queue DS.
3. Create a method that accepts current node and searched node.
4. Base case 1 - current node == searched node.
5. Base case 2 - already visited this node.
6. Mark as visited and print/add to collection current node.
7. Iterate children of current node.
8. Add unvisited children to queue.
9. After above loop execute recursively with element that waited the longest in queue.

## Connected components
1. Initialize static boolean array with the size == number of nodes in graph.
2. Initialize a list of nodes to hold the currently walked graph component.
3. Initialize a list of lists of nodes (the above DS). This holds all components.
4. Modify DFS or BFS to add the current node into list of nodes.
5. Create a method that takes no arguments (graph can be global/static)
6. Iterate with standart for loop over the graph nodes.
7. Only if the currently iterated node is not visited do the following.
  7.1. Call DFS or BFS with the current node. Make searched node something not existing in the graph.
  7.2. Add current component list to all components list.
  7.3. Clear the current list.
  
## Topological sorting (Reversed DFS approach)
1. Initialize static linked list for keeping the order of the items as result.
2. Initialize static set for cycle detection.
3. We will use modified DFS to do the topological sorting.
4. Create method for topological sorting.
5. Start DFS with root element as first parameter.
6. Base case 1 - current node has already been visited (cycle), throw exception.
7. Base case 2 - node visited? return
8. When we 'visit' a node in DFS method add the node to visited nodes set.
9. Call DFS recursively for all children.
10. Remove item from visited nodes.
11. Add current node as first in linked list. (as it is backtracking phase, we go backwards)

## Minimum Spanning Tree (MST) Kruskal
