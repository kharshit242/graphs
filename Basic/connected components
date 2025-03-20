import java.util.*;
import java.io.*;
public class pep2 {
    static class Edge{
        int src;
        int dest;
        int wt;
        public Edge(int src,int dest,int wt){
            this.src=src;
            this.dest=dest;
            this.wt=wt;
        }
    }
    public static void main(String args[])throws Exception{
        BufferedReader br=new BufferedReader(new InputStreamReader(System.in));

        int vtces=Integer.parseInt(br.readLine());
        ArrayList<Edge>graph[]=new ArrayList[vtces];
        for(int i=0;i<vtces;i++){
            graph[i]=new ArrayList<>();
        }
        System.out.println("Enter edges");
        int edges=Integer.parseInt(br.readLine());
        System.out.println("Enter graph");
        for(int i=0;i<edges;i++){
            String parts[]=br.readLine().split(" ");
            int v1=Integer.parseInt(parts[0]);
            int v2=Integer.parseInt(parts[1]);
            int wt=Integer.parseInt(parts[2]);
            graph[v1].add(new Edge(v1,v2,wt));
            graph[v2].add(new Edge(v2,v1,wt));
        }

        ArrayList<ArrayList<Integer>>comps=new ArrayList<>();

        boolean vis[]=new boolean[vtces];
        for(int v=0;v<vtces;v++){
            if(vis[v]==false){
                ArrayList<Integer>comp=new ArrayList<>();
                drawTreeAndGenerateComp(graph, v, comp, vis);
                comps.add(comp);
            }
        }
        System.out.println(comps);
    }

    public static void drawTreeAndGenerateComp(ArrayList<Edge>graph[],int src,ArrayList<Integer>comp,boolean vis[]){
        vis[src]=true;
        comp.add(src);
        for(Edge e:graph[src]){
            if(vis[e.dest]==false){
                drawTreeAndGenerateComp(graph,e.dest,comp,vis);
            }
        }
    }
}
