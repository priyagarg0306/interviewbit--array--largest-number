# interviewbit--array--largest-number

**-----> Question:**

Given a list of non negative integers, arrange them such that they form the largest number.

For example:

Given [3, 30, 34, 5, 9],
the largest formed number is 9534330.

Note: The result may be very large, so you need to return a string instead of an integer.


**------> Code:**

bool func(string a,string b){

    string ab=a.append(b);
    string ba=b.append(a);

    if(ab.compare(ba)>0){
        return true;
    }

    return false;
}

string Solution::largestNumber(const vector<int> &v) {
  
    string ans;
    vector<string> s;
    int count=0,n=v.size();

    for(int i=0;i<n;i++){
        if(v[i]==0){
            count++;
        }

        s.push_back(to_string(v[i]));
    }

    if(count==n){
        return "0";
    }

    sort(s.begin(),s.end(),func);

    for(int i=0;i<s.size();i++){
        ans+=s[i];
    }

    return ans;

}
