from PIL import Image #pillow
import requests
from StringIO import StringIO
 
charlist = ['@','#','$','%','&','?','*','o','/','{','[','(','|','!','^','~','-','_',':',';',',','.','`',' ']
count = len(charlist)
 
def toText(image):
   image = image.convert('L') #convert to black and white
   result = ''
   for i in range(0,  image.size[1]):# height
      for j in range(0, image.size[0]):# width
         grayscale = image.getpixel((j,i))
         result += charlist[int(grayscale/(255/(count-1)))] #append char to result
      result += '\r\n'
   return result

# if pic source is online  
pic = requests.get('http://img.xiazaizhijia.com/uploads/2015/1130/20151130115139727.jpg')
image = Image.open(StringIO(pic.content))
# if pic source is local, replace pic.content with the local address of the pic
image = image.resize((100,55))# resize to fit the output window

output = open('/Users/apple/Desktop/anime pics//output.txt','w')
output.write(toText(image))
output.close()
