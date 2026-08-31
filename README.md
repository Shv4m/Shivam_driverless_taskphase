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


#4q
def matrix_multiply(A, B):
    rows_A = len(A)
    col_A = len(A[0])
    rows_B = len(B)
    col_B = len(B[0])

if col_A != rows_B:
        print("Error: Multiplication not possible.")
        print("Number of columns in A must equal number of rows in B.")
        return None

result = []
    for i in range(rows_A):
        row = []
        for j in range(col_B):
            row.append(0)
        result.append(row)

for i in range(rows_A):
        for j in range(col_B):
            total = 0
            for k in range(col_A):
                total = total + A[i][k] * B[k][j]
            result[i][j] = total

return result

def input_matrix(name):
    rows = int(input(f"Enter number of rows for {name}: "))
    cols = int(input(f"Enter number of columns for {name}: "))
    matrix = []
    print(f"Enter elements of {name} row by row:")
    for i in range(rows):
        row = list(map(int, input().split()))
        matrix.append(row)
    return matrix


A = input_matrix("Matrix A")
B = input_matrix("Matrix B")

result = matrix_multiply(A, B)

if result is not None:
    print("Resultant Matrix:")
    for row in result:
        print(row)
