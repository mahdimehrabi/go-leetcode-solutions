# leetcode: reverse string Golang

This solution reverses a string in place using a two-pointer approach. We initialize two pointers, l (left) at the start and r (right) at the end of the string. We swap the characters at these pointers and then move the pointers towards each other until they meet in the middle.


### Fullcode 
func reverseString(s []byte)  {
	l := 0
	r := len(s) - 1
	for l < r {
		s[l], s[r] = s[r], s[l]
		l++
		r--
	}
}
