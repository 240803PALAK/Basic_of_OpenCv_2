# Basic_of_OpenCv_2
It include Blurring, Bitwise Operation, Masking.


    import cv2 as cv
    
    img=cv.imread('peacock.jpg')
    cv.imshow('peacock',img)
    
    # Gaussian Blur
    gauss=cv.GaussianBlur(img,(3,3),0)
    cv.imshow('Gaussian Blur',gauss)
    
    # Median Blur
    median=cv.medianBlur(img,3)
    cv.imshow('Median Blur',median)
    
    # Bilateral
    bilateral=cv.bilateralFilter(img,5,15,15)
    cv.imshow('Bilateral',bilateral)
    cv.waitKey(0)
    
    cv.waitKey(0)
    
    
    
    
    
    import cv2 as cv
    import numpy as np
    blank=np.zeros((400,400),dtype='uint8')
    
    rectangle=cv.rectangle(blank.copy(),(30,30),(370,370),255,-1)
    circle=cv.circle(blank.copy(),(200,200),200,255,-1)
    
    cv.imshow('Rectangle',rectangle)
    cv.imshow('Circle',circle)
    
    # Bitwise AND
    bitwise_and=cv.bitwise_and(rectangle,circle)
    cv.imshow('Bitwise And',bitwise_and)
    
    # Bitwise OR
    bitwise_or=cv.bitwise_or(rectangle,circle)
    cv.imshow('Bitwise OR',bitwise_or)
    
    # Bitwise XOR
    bitwise_xor=cv.bitwise_xor(rectangle,circle)
    cv.imshow('Bitwise XOR',bitwise_xor)
    
    # Bitwise not
    bitwise_not=cv.bitwise_not(circle)
    cv.imshow('Bitwise Not',bitwise_not)
    
    cv.waitKey(0)
    
    
    
    
    import cv2 as cv
    import numpy as np
    
    img=cv.imread('peacock.jpg')
    blank=np.zeros(img.shape[:2],dtype='uint8')
    cv.imshow('Blank Image',blank)
    
    mask=cv.circle(blank,(img.shape[1]//2,img.shape[0]//2),300,255,-1)
    cv.imshow('Mask',mask)
    masked=cv.bitwise_and(img,img,mask=mask)
    cv.imshow('Masked Image',masked)
    
    cv.waitKey(0)
