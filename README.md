# python2
def invertdict(input_dict):
    inverted_dict = {}    
    for key, value in input_dict.items():
        inverted_dict[value] = key        
    return inverted_dict
# Example usage
original_dict = {'a': 1, 'b': 2, 'c': 3}
inverted_dict = invertdict(original_dict)
print(inverted_dict)


def valuesort(input_dict):
    sorted_values = {key: value for key, value in sorted(input_dict.items())}
    return sorted_values
# Example usage
original_dict = {'b': 2, 'a': 1, 'c': 3}
sorted_values = valuesort(original_dict)
print(sorted_values)


def find_n_largest_elements(lst, n):
    sorted_lst = sorted(lst, reverse=True)
    n_largest = sorted_lst[:n]
    return n_largest
# Example usage
input_list = [12, 45, 2, 41, 31, 10, 8, 7, 23, 56]
N = 3
largest_elements = find_n_largest_elements(input_list, N)
print(f"The {N} largest elements are:", largest_elements)



string_maps = {
    "1": "abc",
    "2": "def",
    "3": "ghi",
    "4": "jkl",
    "5": "mno",
    "6": "pqrs",
    "7": "tuv",
    "8": "wxy",
    "9": "z"
}
def generate_combinations(digit_string):
    if len(digit_string) != 2:
        print("Please provide a two-digit string.")
        return []
    first_digit = digit_string[0]
    second_digit = digit_string[1]
    if first_digit not in string_maps or second_digit not in string_maps:
        print("Invalid digits in the string.")
        return []
    first_letters = string_maps[first_digit]
    second_letters = string_maps[second_digit]
    combinations = first_letters + second_letters
    return combinations
# Example usage
for i in range(1,9,1):
    for j in range(1,9,1):
        num1 = i*10
        num2 = j
        result = str(num1+num2)
        combinations = generate_combinations(result)
        print("All possible two-letter combinations:", combinations)


def DoubleList(list):
    new_list = []
    for item in list:
        new_list.append(item*2)
        return new_list
list = [123,456,222,145]
print(DoubleList(list))


def binary_search(lst, t):
    left = 0
    right = len(lst) - 1
    while left <= right:
        mid = (left + right) // 2     
        if lst[mid] == t:
            return mid
        elif lst[mid] < t:
            left = mid + 1
        else:
            right = mid - 1
    return -1
sorted_array = [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
target_element = 12
result = binary_search(sorted_array, target_element)
if result != -1:
    print(f"Element {target_element} found at index {result}")
else:
    print(f"Element {target_element} not found in the array")



def BinarySearch(list, left, right, target):
    if left > right:
        return -1
    mid = (left + right)//2
    if list[mid] == target:
        return mid
    elif list[mid] > target:
        return BinarySearch(list, left, mid - 1, target)
    else:
        return BinarySearch(list, mid + 1, right, target)
list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
result = BinarySearch(list, 0,len(list)-1,9)
if result != -1:
    print(f"Element {target_element} found at index {result}")
else:
    print(f"Element {target_element} not found in the array")


def uniqueValue(lst):
    new_list = []
    obj = {}
    for item in lst:
        if item not in obj:
            obj[item] = 1
        else:
            obj[item] += 1
    for key, value in obj.items():
        if value == 1:
            new_list.append(key) 
    return sorted(new_list)
lst = [1, 1, 2, 4, 5, 3, 5, 5, 7, 9, 10, 11, 21, 12, 2]
print(uniqueValue(lst))



def Nlargest(List,N):
    List = sorted(List,reverse=True)
    return List[:N]
numbers = [15, 2, 34, 45, 12, 67, 23, 9]
print(Nlargest(numbers,3))



def twoDigit(obj):
    strings_arr = []
    for i in range(1,10):
        for j in range(1,10):
            if i != j:
                strings_arr.append(obj[str(i)]+obj[str(j)])
    
    return strings_arr
string_maps = {
"1": "abc",
"2": "def",
"3": "ghi",
"4": "jkl",
"5": "mno",
"6": "pqrs",
"7": "tuv",
"8": "wxy",
"9": "z"
}
List = twoDigit(string_maps)
for item in List:
    print(item)


def isvalid(i, j):
    return 0 <= i < 10 and 0 <= j < 10
def number_Island(data, i, j, visited):
    if not isvalid(i, j) or visited[i][j] or data[i][j] == '0':
        return    
    visited[i][j] = True

    dx = [-1, 1, 0, 0]
    dy = [0, 0, -1, 1]

    for k in range(4):
        new_x, new_y = i + dx[k], j + dy[k]
        number_Island(data, new_x, new_y, visited)
data = [
    "1100000111",
    "1000000111",
    "0000000111",
    "0010001000",
    "0000011100",
    "0000111110",
    "0001111111",
    "1000111110",
    "1100011100",
    "1110001000"
]
visited = [[False for _ in range(10)] for _ in range(10)]
island_count = 0
for i in range(10):
    for j in range(10):
        if data[i][j] == '1' and not visited[i][j]:
            number_Island(data, i, j, visited)
            island_count += 1
print(island_count)


