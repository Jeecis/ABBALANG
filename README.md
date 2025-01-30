# ABBALANG grammar

Written in EBNF and compiled/tested using https://mdkrajnak.github.io/ebnftest/

See the testdata in test_data.txt, and the analog translation of it main.go file. The following examples of ABBALANG have been inspired from golang.

### Single letter variables, 
`Gimme! Gimme! Gimme! someMusic = "a"`
equivalent to
`someMusic := "a"`
### Numbers
`Gimme! Gimme! Gimme! someMusic = 1`
equivalent to
`someMusic := 1`
### Assignment
`Gimme! Gimme! Gimme! bjorn = 12345678
Gimme! Gimme! Gimme! benny = bjorn
`
equivalent to
`bjorn := 1
benny := bjorn
`
### Arithmetic
`benny = 123+234`
equivalent to
`benny = 123 + 234`

### Variables with unlimited length alphanumerics
`Gimme! Gimme! Gimme! benny123 = "bjorn567"`
equivalent to
`benny123 := "bjorn567"`

### Loops 

`Super Trouper(benny>bjorn){
bjorn = bjorn+1
}`
equivalent to
`	for benny > bjorn {
		bjorn = bjorn + 1
	}`

### Conditionals 
`You can(dance==false){
dance = true
}Or you can(sing==false){
sing = true
}Or you can(sing==true){
sing = false
}having the time of your{
life = true
}`
equivalent to
`if dance == false {
		dance = true
	} else if sing == false {
		sing = true
	} else if sing == true {
		sing = false
	} else {
		life = true
	}`

### Switch statement
`Mama mia (y){
here I go again (1){
Gimme! Gimme! Gimme! val = 10
}here I go again (2){
Gimme! Gimme! Gimme! val = 20
}here I go again (3){
Gimme! Gimme! Gimme! val = 30
}My my how can I resist you {
Gimme! Gimme! Gimme! val = 2
}}`
equivalent to
`	var y interface{}
	var val interface{}
	switch y {
	case 1:
		val = 10
	case 2:
		val = 20
	case 3:
		val = 30
	default:
		val = 2
	}`

### Arrays
`Gimme! Gimme! Gimme! val = [1,2,3]`
equivalent to
`val = []int{1, 2, 3}`
### Functions
`Take a chance on yourself(vicotry){
return victory
}`
equivalent to
`func yourself(victory interface{}) interface{} {
	return victory
}`

### Package decleration
`Waterloo ABBALANG`
equivalent to
`package main
`
### Program end
`Thank you for the music!`
no equivalence for golang
