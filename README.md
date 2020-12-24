# ParenthesisCheck
it transfers the received string to the stack by converting it to an array of characters and is controlled by the for loop until it reaches the array size, increasing the value of the variable belonging to that parenthesis type for each parenthesis type. when the control process is complete, it is checked whether the number of opened brackets for each type of parenthesis is equal to the number of closed brackets.
















public class Stack2 {
       private int maxsize;
    private char[] stackArray;
    private int top;
    
     public Stack2(int max){
        maxsize=max;
        stackArray=new char[maxsize];
        top=-1;
        
    }
    public void push(char c){
        stackArray[++top]=c;
        
    }
    public int pop(){
       return stackArray[top--];
     
    }
    public boolean isEmpty(){
        
        return top==-1;
    }
     public void PrintStack(){
        if(top!=-1){
            for (int i = 0; i<=top; i++) {
                System.out.println(stackArray[top-i]);
                
            }
        }
     }
     
public void ParenthesisCheck(String expr){
    char[] chararray=expr.toCharArray();
   Stack2 y=new Stack2(chararray.length);
       for (int i = 0; i <chararray.length; i++) {
           y.push(chararray[i]);
   
        
    }
      
       int a=0;  //  variable that holds the number of brackets from Type '('
       int b=0;  //  variable that holds the number of brackets from Type ')'
       int c=0;  //  variable that holds the number of brackets from Type '['
       int d=0;  //  variable that holds the number of brackets from Type ']'
       int e=0;  //  variable that holds the number of brackets from Type '{'
       int f=0;  //  variable that holds the number of brackets from Type '}'
              
       for (int i = 0; i <chararray.length; i++) {
        if(chararray[i]=='('){
            a++;
            
        }
        else if(chararray[i]=='['){
            c++;
            
        }
         else if(chararray[i]=='{'){
            e++;
            
        }
          else if(chararray[i]==')'){
            b++;
            
        }
         else if(chararray[i]==']'){
            d++;
            
        }
         else if(chararray[i]=='}'){
            f++;
            
        }
        
        
    }
       if(a!=b){
       System.out.println("Type '()' has unclosed brackets ");
           
       }
       else{
       System.out.println("brackets of Type '()' are closed ");
       }
       
       if(c!=d){
       System.out.println("Type '[]' has unclosed brackets " );
       }
       else{
       System.out.println("brackets of Type '[]' are closed");
       }
       if(e!=f){
       System.out.println("Type '{}' has unclosed brackets ");
       }
       else{
            System.out.println("brackets of Type '{}' are closed ");
       }

}
}

