def spiral_word(word):
    val1 = True
    val2 = True
    # use odd and even number to check
    # only compare (length of word -1) times 
    for i in range(len(word)-1):
       
        if i ==0:
            if word[int(i/2)] > word[-(int(i/2)+1)]:
                val2 = False
                
            elif word[int(i/2)] < word[int(-(i/2+1))]:
                val2 = True
                
        else:  # i > 0
            if i % 2 == 0:  # when i is even
                if word[int(i/2)] > word[-(int(i/2)+1)] and val2 is False:
                    val1 = True
                elif word[int(i/2)] < word[-(int(i/2)+1)] and val2 is True:
                    val1 = True
                else:
                    val1 = False
            else:  # when i is odd
                if word[-(int(i/2)+1)] > word[int(i/2)+1] and val2 is False:
                    val1 = True
                elif word[-(int(i/2)+1)] < word[int(i/2)+1] and val2 is True:
                    val1 = True
                else:
                    val1 = False
        if val1 is False:
            val2 = False
    return val1, val2
    
