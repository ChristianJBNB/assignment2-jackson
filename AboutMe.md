# Christian Jackson

My name is Christian Jackson, and I am a senior at Northwest Missouri State University. I am studying both computer science and cybersecurity. While taking classes I am also studying for certifications that I hope to use when I get a job in security. I hope that one day I can be a freelance security analysist or work on an incident response team.

[Picture of Me](https://github.com/ChristianJBNB/assignment2-jackson/blob/main/IMG_1494.JPG?raw=true)
---
## Food and Drinks

Here are some of the foods and drinks that I enjoy the most. The table located below this will tell you what the food/drink is, where you can find it, and how much it will cost you.

| Food/Drink       | Location          | Cost of item |
|------------------|-------------------|--------------|
| Z-Man            | KC Joes           | $9.00        |
| Fried Chicken    | Canes             | $8.00        |
| Boulevard Tank 7 | Boulevard Brewery | $4.00        |
| Ice Cream        | Dairy Queen       | $5.00        |
---
>"640K ought to be enough (memory) for anybody." -*Bill Gates*

>"I ain’t gonna be no escape-goat!" -*Karl Malone.*
>
---

>"String Matching Algorithm is also called "String Searching Algorithm." This is a vital class of string algorithm is declared as "this is the method to find a place where one is several strings are found within the larger string." -[Link to Info](https://www.javatpoint.com/daa-string-matching-introduction)

## Example Code for String Matching Algorithm
'''
vector<int> rabin_karp(string const& s, string const& t) {
    const int p = 31; 
    const int m = 1e9 + 9;
    int S = s.size(), T = t.size();

    vector<long long> p_pow(max(S, T)); 
    p_pow[0] = 1; 
    for (int i = 1; i < (int)p_pow.size(); i++) 
        p_pow[i] = (p_pow[i-1] * p) % m;

    vector<long long> h(T + 1, 0); 
    for (int i = 0; i < T; i++)
        h[i+1] = (h[i] + (t[i] - 'a' + 1) * p_pow[i]) % m; 
    long long h_s = 0; 
    for (int i = 0; i < S; i++) 
        h_s = (h_s + (s[i] - 'a' + 1) * p_pow[i]) % m; 

    vector<int> occurences;
    for (int i = 0; i + S - 1 < T; i++) { 
        long long cur_h = (h[i+S] + m - h[i]) % m; 
        if (cur_h == h_s * p_pow[i] % m)
            occurences.push_back(i);
    }
    return occurences;}

'''

[Link to Code](https://cp-algorithms.com/string/rabin-karp.html)