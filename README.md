# SimpleFileReadingCodeForAlgorithmII
  Here is the sample file: 
  
    13
    13
    0 5
    4 3
    0 1
    9 12
    6 4
    5 4
    0 2
    11 12
    9 10
    0 6
    7 8
    9 11
    5 3

  

     public class ConnectedCompTesting {
	   static int V;//number of vertices
	   static int E;//number of edges

	public static void main(String[] args) {
		// The name of the file to open.
        String fileName = "tinyG.txt";// this is the file 

        // This will reference one line at a time
        String line = null;

        try {
            // FileReader reads text files in the default encoding.
            FileReader fileReader = 
                new FileReader(fileName);

            // Always wrap FileReader in BufferedReader.
            BufferedReader bufferedReader = 
                new BufferedReader(fileReader);

           // while((line = bufferedReader.readLine()) != null) {
             //   System.out.println(line);
            //}  
            for(int i=0;i<2;i++){
            	line=bufferedReader.readLine();
            	if(i==0){
            		V=Integer.parseInt(line);
            	}
            	else{
            		E=Integer.parseInt(line);
            	}
            }
            for(int i=0;i<13;i++){
            	line=bufferedReader.readLine();
            	String[] strs = line.trim().split("\\s+");
            	
            	int[] x=new int[2];
            	for (int j = 0; j < 2; j++) {
            	 x[j] = Integer.parseInt(strs[j]);
            	}
            	System.out.print(x[0] +",");
            	System.out.println(x[1]);

            }
            

            // Always close files.
            bufferedReader.close();         
        }
        catch(FileNotFoundException ex) {
            System.out.println(
                "Unable to open file '" + 
                fileName + "'");                
        }
        catch(IOException ex) {
            System.out.println(
                "Error reading file '" 
                + fileName + "'");                  
            // Or we could just do this: 
            // ex.printStackTrace();
        }
	}
	}
