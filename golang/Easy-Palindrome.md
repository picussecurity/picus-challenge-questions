A palindrome is a word that reads the same backward or forward.

Write a go file that checks if a given word is a palindrome. Character case should be ignored.

For example, isPalindrome("Deleveled") should return true as character case should be ignored, resulting in "deleveled", which is a palindrome since it reads the same backward and forward.

````
func main() {
	fmt.Println(isPalindrome("Deleveled"))
	fmt.Println(isPalindrome("not a palindrome"))
}
````
