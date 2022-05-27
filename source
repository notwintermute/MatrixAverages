import numpy as np

n = 4  # you can change this
# making the example matrix
# 1 0 1 0
# 0 1 0 1
# 1 0 1 0
# 0 1 0 1
inp = []
for i in range(n):
    inp.append([])
    for j in range(n):
        inp[i].append((1+i+j)%2)
A = np.array(inp)

# making the calculation matrices
# if your matrix isn't changing dimensions then you only need to do this once
# making the dividing matrix
aDiv = 9 * np.ones((n, n))
line1 = 6 * np.ones((1, n))
line1[0, 0] = line1[0, -1] = 4
aDiv[0, :] = aDiv[-1, :] = aDiv[:, 0] = aDiv[:, -1] = line1

# making the mult matrix
line2 = np.zeros((1, n))
line2[0, 0:2] = 1
aMul = line2
line3 = np.zeros((1, n + 1))
line3[0, 0:3] = 1
for i in range(n - 3):
    aMul = np.concatenate((aMul, line3), axis=1)
aMul = np.concatenate((aMul, np.ones((1, 3))), axis=1)
aMul = np.concatenate((aMul, np.zeros((1, n))), axis=1)
aMul[0, -1] = aMul[0, -2] = 1
aMul = aMul.reshape((n, n))

# the calculation itself
sum = np.matmul(aMul, np.matmul(aMul, A).transpose()).transpose()
avg = (sum / aDiv)
print(sum)
print(avg)
