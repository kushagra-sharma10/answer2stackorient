from math import floor

def roundNumbers(input):
    output = map(lambda x: floor(x), input)
    remain = round(sum(input) - sum(output))
    
    it = sorted(enumerate(input), key=lambda i: i[1] - floor(i[1]))
    for _ in range(remain):
        output[it.pop()[0]] += 1

    return output
