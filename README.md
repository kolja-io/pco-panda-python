# pco-panda-python
pco panda python




treiber installieren 

usb c (thunderbold kabel benutzen)

pco.camware kamara testen 

python installieren (WICHTIG : <3.8)

pip install pco
pip install opencv-python
pip install keyboard 
pip install matplotlib

python manuel : https://www.pco.de/fileadmin/user_upload/pco-manuals/MA_PCOPYTHON.pdf


Beispiel Code:

import time
import cv2 as cv
import sys
import pco
import keyboard
import matplotlib.pyplot as plt
import os
#with pco.Camera() as cam:
cam = pco.Camera()

print('You can now set The Exposure (0.001 - 1e-3s)')

exposure = float(input())

print(exposure)

cam.set_exposure_time(exposure)


while True:  
    directory = r'C:\Users\Kolja\Desktop\Bilder123'
    os.chdir(directory)
    #print('Kamera Nimmt uf')
    cam.record(number_of_images=1, mode='sequence') 
    image, meta = cam.image(image_number=0, roi=None)
    print('Kamera Hat Bild')
    cv.imshow("as louft", image)
    cv.waitKey(1)
    #print('Bild Is DA')
    # if k == ord("s"):
    #     cv.imwrite("hallo.png", image)
    time.sleep(0.01)
    #    except: break  







# with pco.Camera() as cam:

#     directory = r'C:\Users\Kolja\Desktop\Bilder123'
#     os.chdir(directory)


#     cam.record(number_of_images=1, mode='sequence') 
#     image, meta = cam.image(image_number=0, roi=None)

#     cv.imshow("as louft", image)
#     k = cv.waitKey(0)

# if k == ord("s"):
#     cv.imwrite("hallo.png", image)

    

    



    #plt.imshow(image, cmap='gray')
    #plt.show()




    #type(image)
    #numpy.ndarray
    #image.shape(2160, 2560)
    #image, metadata = can.image(roi=(1, 1, 300, 300))
    #image.shape(300, 300)
