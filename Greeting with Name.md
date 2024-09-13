Greeting with Name = 
--Create Variables
--Searches for length up until criteria (in this case ".") and gives the count of characters (this will also include the count with "."
VAR UserNameLength = SEARCH(".",USERPRINCIPALNAME())
--Return the user first name using USERPRICIPALNAME function by leveraging the count of characters and minus 1 to remove the "."
VAR FirstName = LEFT(USERPRINCIPALNAME(),UserNameLength-1)
--Formatting to do the proper upper case of the first letter, isolates the first character to do the upper, and then joins the rest of the name using the MID function
VAR FormattedFirstName = UPPER(LEFT(FirstName,1)) & MID(FirstName,2,UserNameLength-1)
--Return the end result. In this case a text string to create the greeting using our formatted proper name.
RETURN
"Hello " & FormattedFirstName & ", here's what you need to know:"
