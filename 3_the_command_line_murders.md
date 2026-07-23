https://sadservers.com/scenario/command-line-murder

# Description 

This is the Command Line Murders with a small twist as in the solution is different

Enter the name of the murderer in the file /home/admin/mysolution, for example echo "John Smith" > ~/mysolution

Hints are at the base of the /home/admin/clmystery directory. Enjoy the investigation!

# Solutions

// read instructions

grep "CLUE" crimescene  // Filter by CLUE as per instructions >>  Displays 3 clues

grep "Annabel" people | grep "\bF\b"  // Filter and inspect people by suspect Annabel and Females 

sed -n '40p' streets/Hart_Place // extract interview

cat interviews/interview-47246024 // ruled out >> go to second suspect from above

sed -n '179' streets/Buckingham_Place // extract interview

cat interviews/interview-699607     // Clue about car

cat vehicles | tr "\n" " " | sed "s/License/\n/g" | grep "Blue" | grep "Honda" | grep "L337..9" // Filter for Blue Hondas with License Plate starts with L337 and ends with 9 as per interview above

cat Delta_SkyMiles Museum_of_Bash_History Rotary_Club Terminal_City_Library | sort | uniq -c | grep -w "4" | awk '{print $2 "_" $3}' // find list of persons that have all four memberships listed in clue earlier

echo "Joe Germuska" > ~/mysolution // He was only suspect that was above 6ft, Male, Drove Blue Honda with license plate starting with L337 and ended with 9. 

md5sum ~/mysolution
