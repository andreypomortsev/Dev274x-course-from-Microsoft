!curl https://raw.githubusercontent.com/MicrosoftLearning/intropython/master/elements1_20.txt -o elements1_20.txt
print('\n\n')

# the function is getting input from user and collects it to list avoiding duplication and white spaces in input data
def get_names():
    list_of_guesses = []
    print('list any 5 of the first 20 elements in the Period table')
    while len(list_of_guesses) < 5:
        guess = input('Enter the name of an element: ')
        if guess == '':
            print('Empty string is not allowed')
        elif guess.title().strip() in list_of_guesses:
            print(guess,'was already entered')
        else:
            list_of_guesses.append(guess.title().strip())
    return list_of_guesses

# by this variable we assign output from the function in form of a list of user's input
guesses = get_names()

# here we open downloaded earlier file in read mode and assign it to variable
elements20 = open('elements1_20.txt', 'r')
lines = elements20.readline().strip(',\n').split(',')

# here we read the file line by line and turning it into the list "lines"
while elements20.readline():
    lines.append(elements20.readline().strip(',\n'))
    
# this statetment help us to avoid the list index out of range error, 
# of course it can be avoided by Try and Except but we cannot use it here because we have not been taught that :)
    if '' in lines:
        lines.remove('')
        
# we don't need this file anymore, so we close it
elements20.close()

# now we need to know how long 'guesses' list is, due to we need to itirate through it and don't get the out 'of range error'
count = len(guesses)
right_ans = 0

# creating a new list for right answers hat will be found in the list 'lines'
found = []
not_found = []

# iterating user's input through the right answers list
for i in range(count):
    if guesses[i] in lines:
        right_ans += 1
        found.append(guesses[i])
    else:
        not_found.append(guesses[i])

print('\n\n' + str(right_ans * 20) + '% correct','\nFound:',', '.join(found),'\nNot Found:',', '.join(not_found))
