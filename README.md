class Solution:
    def topoSort(self, V, edges):
        def dfs(node):
            for adjNode in adj[node]:
                if(vis[adjNode]==0):
                    vis[adjNode]=1
                    dfs(adjNode)
            stack.append(node)
            return
        adj=[]
        for _ in range(V):
            adj.append([])
        for u,v in edges:
            adj[u].append(v)
        vis=[0]*V
        stack=[]
        for n in range(0,V):
            if(vis[n]==0):
                vis[n]=1
                dfs(n)
        return stack[::-1]
        
