# Shivam_driverless_taskphase
#1q
n =int(input("Enter number of strings : "))

L1st = []
for i in range(n):
    s = input("Enter string: ")
    L1st.append(s)

D={}

for word in L1st:
    word = word.lower()
    for ch in word:
        if ch.isalpha():
            if ch in D:
                D[ch] += 1
            else:
                D[ch] = 1

print(D)
