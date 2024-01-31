import java.util.Stack;
public class Solution {

	public static int countBracketReversals(String input) {
		//Your code goes here
        if(input.length()%2==1){
            return -1;
        }
        Stack<Character> stack=new Stack<Character>();
        
        for(int i=0;i<input.length();i++){
            if(input.charAt(i)=='{'){
                stack.push(input.charAt(i));
            }else{
                if(stack.isEmpty()){
                    stack.push(input.charAt(i));
                }else{
                    if(stack.peek()=='{'){
                        stack.pop();
                    }else{
                        stack.push(input.charAt(i));
                    }
                }         
            }
        }
         int count=0;
        while(stack.isEmpty()!=true){
            char c1=stack.pop();
            char c2=stack.pop();
            if(c1==c2){
                count++;
            }else{
                count=count+2;
            }
        }
        return count;
        
	}
}
