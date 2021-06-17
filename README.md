# OSLab10
1)
#!/bin/bash
echo "enter your age: "
read age
if [ $age -ge 18 ]
then
	echo "You may go to the party"
elif [ $age -lt 18 ]
then
	echo "do you have permission? "
	read permission
	if [ $permission = "yes" ]
then
	echo "You may go the party but be back before midnight."
else
	echo "You may not go to the party."
	fi
		
----------------------------------------------------------------------
2)
#!/bin/bash
for i in {1..100}
do
	mkdir user$i
done

----------------------------------------------------------------------
3)
#!/bin/bash
echo "directory: "
read dir
count=0
for file in $(find $dir -type f -name "*.jpg")
do
mv $file $dir/img$((count=count+1)).jpg
done
for file in $(find $dir -type f -name "*.png")
do
mv $file $dir/img$((count=count+1)).png
done

----------------------------------------------------------------------
4)
# !/bin/bash
echo "Enter Choice :"
echo "1. Addition"
echo "2. Subtraction"
echo "3. Multiplication"
echo "4. Division"
read ch

echo "Enter Two numbers : "
read a
read b

case $ch in
1)res=`echo $a + $b | bc`
;;
2)res=`echo $a - $b | bc`
;;
3)res=`echo $a \* $b | bc`
;;
4)res=`echo "scale=2; $a / $b" | bc`
;;
esac
echo "Result : $res"

