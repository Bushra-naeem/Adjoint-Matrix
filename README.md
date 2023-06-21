# Adjoint-Matrix
def adjointOfMatrix(M):
    matrix_C = []
    for i in range(n):
        matrix = []
        for j in range(n):
            nr_M = []
            for row in range(n):
                for column in range(n):
                     if (row == i or column == j):
                         continue
                     else:
                         nr_M.append(M[row][column])
            a, b, c, d = nr_M
            det = (a*d)-(b*c)
            cofactor = ((-1)**(i+j))*det
            matrix.append(cofactor)
        matrix_C.append(matrix)

    # Let's find the transpose of cofactor matrix
    for i in range(n):
        for j in range(i+1,n):
            matrix_C[i][j],matrix_C[j][i] = matrix_C[j][i],matrix_C[i][j]
    return matrix_C
M = [[3,1,-1],[2,-2,0],[1,2,-1]]
n = len(M)
print(adjointOfMatrix(M))
