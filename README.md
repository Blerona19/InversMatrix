# InversMatrix

package inversmatrix;

import java.util.Arrays;

public class InversMatrix {
    public void calculate() 
    {
        
 double[][] 
        C;
        C = new double[][]
{
        {1,2,3},
        {0,1,4},
        {5,6,4}
    };
        double [][] M=new double[C.length][2*C.length];
        
        for(int i=0;i<C.length;i++) {
          for(int j=0;j<C.length;j++){
              M[i][j]=C[i][j];
          }
          M[i][3+i] =1;
    }
            for(int i=0;i<M.length;i++) {
                double p=M[i][i];
                    for(int j=0;j<M[i].length;j++) {
                        M[i][j]/=p;
                    }
             for(int k=i+1; k<M.length; k++) {
			 p=M[k][i];
			 for (int j=0; j<M[i].length; j++) {
				 M[k][j] -= p*M[i][j];
				 
			 }
		 }
	 }
        for (int i=M.length-1; i>=0; i--) {
		  for(int k=i-1; k>=0; k--) {
			double p=M[k][i];
			 for (int j=0; j<M[i].length; j++) {
				 M[k][j] -= p*M[i][j];
				 
			 }
		 }
	 }
	 
        for(int i=0;i<M.length;i++)  {
            System.out.println(Arrays.toString(M[i]));
        }
        
    } 
    public static void main (String[] args)
        { 
        InversMatrix invers=new InversMatrix();
        invers.calculate();
        }
}
