# Topological Sorting

Given an directed graph, a topological order of the graph nodes is defined as follow: 

* For each directed edge A -&gt; B in graph, A must before B in the order list. 
* The first node in the order can be any node in the graph with no nodes direct to it. 

Find any topological order for the given graph.

## Solution

```java
/**
 * Definition for Directed graph.
 * class DirectedGraphNode {
 *     int label;
 *     ArrayList<DirectedGraphNode> neighbors;
 *     DirectedGraphNode(int x) 
 *      { label = x; neighbors = new ArrayList<DirectedGraphNode>(); }
 * };
 */
public class Solution {
    /**
     * @param graph: A list of Directed graph node
     * @return: Any topological order for the given graph.
     ***/    
    public ArrayList<DirectedGraphNode> topSort(ArrayList<DirectedGraphNode> graph) {
        ArrayList<DirectedGraphNode> res = 
		new ArrayList<DirectedGraphNode>();
        if(graph == null || graph.size() == 0) return res;
        
        Map<DirectedGraphNode, Integer> map = 
		new HashMap<DirectedGraphNode, Integer>();
        for(DirectedGraphNode node : graph){
            map.put(node, 0);
        }
        for(DirectedGraphNode node : graph){
            if(map.get(node) == 0)
        	    findASort(graph, node, map, res);
        }
        return res;
    }
    
    void findASort(ArrayList<DirectedGraphNode> graph, DirectedGraphNode node,    
                 Map<DirectedGraphNode, Integer> map, ArrayList<DirectedGraphNode> res){
        map.put(node, 1);
        for(DirectedGraphNode nb : node.neighbors){
            if(map.get(nb) == 0)
                findASort(graph, nb, map, res);
        }
        res.add(0, node);
    }
}

```

