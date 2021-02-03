#merge sort
'''
in merge sort array is divided upto last element and then they are sorted
'''



def mergesort(lst):
    #for sorting we need to check or compare upto last elment so we are dividing   
    if(len(lst))>1:
        #dividing length of array
        mid=len(lst)//2
        left_list=lst[:mid]
        right_list=lst[mid:]

        #recursive function for left_list
        mergesort(left_list)
        #recursive function for right_list
        mergesort(right_list)
        i=0
        j=0
        k=0
        #we use while to compare elment until they are sorted 
        while i<len(left_list) and j<len(right_list):
        #if checks whether left(i) is greater then right if it is greater then in new array which is of k it will be placed
            if left_list[i]<right_list[j]:
                lst[k]=left_list[i]
                i=i+1
                k=k+1
        #else right(j) is subsitted
            else:
                lst[k]=right_list[j]
                j=j+1
                k=k+1
        #to check any element left in the left
        while len(left_list)>i:
            lst[k]=left_list[i]
            i=i+1
            k=k+1
        #to check any element left in the right
        while len(right_list)>j:
            lst[k]=right_list[j]
            j=j+1
            k=k+1


             
                
            
lst=[]
#start 
#take input of array size
n=int(input("enter the array size"))
#taking input of element with for loop one by one
for i in range(0,n):
    ele=int(input("enter the element"))
    # adding element to the array with appened 
    lst.append(ele)
#function is called and it should be called after taking the value
mergesort(lst)
print(lst)



'''
output
enter the array size7
enter the element32
enter the element23
enter the element43
enter the element34
enter the element54
enter the element76
enter the element67
[23, 32, 34, 43, 54, 67, 76]
'''


