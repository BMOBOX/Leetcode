## Notes
1. stack.top() == var (-> Timesout if stack is empty)
2. only key is returned hash.find()
3. hash[c] returns B (A(key) -> B(value))

## Basics

# Stack
push()
pop()
top()
empty()

## Code

'''
class Solution {
    public:
        bool isValid(string s) {
        stack<char> stack;
        unordered_map<char, char> hash = {
            {')', '('},
            {'}', '{'},
            {']', '['}
        };      
        for(auto c : s){
            auto it = hash.find(c);
            if(it == hash.end()){
                stack.push(c);  
            }
            else if(stack.empty() || stack.top() != hash[c]){
                return false;
            }
            else{
                stack.pop();
            }
        }
        return stack.empty();

    }
};
'''
