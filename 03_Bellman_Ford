import java.util.*;

public class BellmanFord{
	public static void main(String[] args){
		int N;
		int[][] graph;
		
		Scanner sc = new Scanner(System.in);
		System.out.print("Enter the number of vertices: ");
		N = sc.nextInt();
		graph = new int[N][N];
		System.out.println("Enter the weight matrix of the graph: ");
		for(int i=0; i<N; i++){
			for(int j=0; j<N; j++){
				graph[i][j] = sc.nextInt();
			}
		}
		System.out.print("Enter Source Vertex: ");
		int source = sc.nextInt();
		source--;
		
		int[] dist = new int[N];
		Arrays.fill(dist, Integer.MAX_VALUE);
		dist[source]=0;
		
		for(int i=0; i<N; i++){
			for(int u=0; u<N; u++){
				for(int v=0; v<N; v++){
					if( dist[u]+graph[u][v]<dist[v] && dist[u]!=Integer.MAX_VALUE && graph[u][v]!=0 ){
						dist[v]=dist[u]+graph[u][v];
					}
				}
			}
		}
		
		for(int u=0; u<N; u++){
			for(int v=0; v<N; v++){
				if( dist[u]+graph[u][v]<dist[v] && dist[u]!=Integer.MAX_VALUE && graph[u][v]!=0){
					System.out.println("Negative weight cycle detected");
					return ;
				}
			}
		}
		
		System.out.println("Vertex\tDistance from Source");
		for(int i=0;i<N;i++){
			System.out.println((i+1)+"\t\t"+dist[i]);
		}	
			
	}	
}
