**Introduction**
	We know Coach bags are expensive. But there is a website called Coach Outlet, which sells cheap coach bags but just with different designs. However, some of the bags are similar. This project will help you find the cheap bags on Coach Outlet which looks like the ones on Coach website.
	This project will crawl websites of coach.com and www.coachoutlet.com, analyze how similar the bags are 
and return you a ".docx" file contains the information of the products that look similar.
	This project used Python 3, some python library: Requests, Python-Docx, XML, Selenium, and Image Similarity API from DeepAI (https://deepai.org/machine-learning-model/image-similarity). 


**Why Do I Write This Project?**
	At the end of May, my mom tells me that she wants a Coach bag under $20. I highly doubt if that could ever happen. Nevertheless, I still try my best to find such a bag. Luckily, I find a website called Coach Outlet who also sells Coach bags, but a lot cheaper. I mean, they are not as cheap as $20, but they are definitely much cheaper than the ones on the original website. However, my mom is saying that they are not the same. Fortunately, according to my careful observations, on those two websites, some bags are really similar to each other. They are just different from each other in some small details, such as colors or accessories. To find all the similar bags, I decided to write this project.


**Instruction**
To run this project, you need to:
	1. install python 3.6 or higher version on your laptop
	2. install requests library on your laptop (pip install requests)
	3. install python-docx library on your laptop (pip install python-docx)
	4. install XML library on your laptop (pip install xml-python)
	5. install Selenium library on your laptop (pip install selenium)
	6. signup/login on DeepAI (https://deepai.org/)
	7. go to Dashboard, go to billing to insert your credit card information
	8. copy the api-key above the Existing Payment Info
	9. go to coach.py, find the function called main(), go to "analysis data" section, change what after the "api-key" to your own api-key
	10. in the "gather data" section, change the baseurl1 and baseurl2 to the coach outlet and coach website you want to do the crawling. 
	11. check the load more button in both Coach and Coach Outlet to see if the xpath is "//*[@id="cont"]/div[79]/div" and "//*[@id="cont"]/div[73]/div"
	Usually, they are, but sometimes the number inside "div[]" changes, so please change them by yourself.
	12. you need to download Google Chrome, and download the chrome driver that matches the version of your current Google Chrome. I suggest you use an older version of Google Chrome because the older ones are more stable.
	13. In function getData(), change the path of chrome driver to your own chrome driver location
	14. to run, type "python3 Path/To/coach.py" in command lines.
	15. if you want to change the sensitivity of the project, you can change it in function main(). In the "analysis data" section, change "if similarity<15" to the number you want. The smaller the number is, the similar the pictures are. 

**CAUTION**
	This running process might cost money because we need to send requests to Image Similarity API. DeepAI charges $0.5 for each 1000 image comparisons, but they only give you a $5 free trial. So when you are finding the bags that look similar, please use as small datasets as possible. Take myself as an example, my mom wants a handbag, so go to women's bag category first and then search handbags. Then on coach.com, it only shows 66 products, and on coachoutlet.com, it only shows 92 products. So the entire comparison is small in this way.
	If your internet is not "perfect", it might happen that the first "load more" button could not be clicked by the computer. You can click it by yourself.


**Demo**
	The coachresult.docx file is a demo for this project. It runs through "https://www.coachoutlet.com/shop/event-handbags-handbags-shoulder-bags?searchkeyword=Shoulder+Bags&qcat=text_header" and "https://www.coach.com/shop/women-handbags-shoulder-bags," which are the sub-websites that show the results of the women's handbags. And I'm using the similarity <15.
	For each group of products, the first product is the coach bag and the latter ones are the coach outlet bags that are similar to this one.  For each product, it first shows a picture of the product, then the name and price of it, and finally a link to buy it and how similar it is to the original product. At the end of each group of products, there will be a line of "--------------------------The end-------------------------------."


**What I Can Improve**
1. to get more images:
	the current project can only get the images that show up on the search page. However, one product could have multiple colors, those products with other colors could not be gathered by my project. To get the rest of the colors, I also wrote some code in help() function to testify but it's currently not working yet.

2. DeepAI does not offer good comparisons among bags:
	If you check out the demo, you will find that some bags that look very different from the original ones have low scores (which means they are really similar to the original coach bags), but the similar ones have high scores. In this case, I'm thinking that Image Similarity API is actually not that useful for our project. So, I will probably write a Similar Bag AI to analyze how similar coach bags and coach outlet bags are for this project.

3. user interface
	The user interface is terrible in my current project. For the next version, I will allow users to insert everything the users need rather than just change inside my code.


**Difficulties That I Faced**
	It takes a lot of time to let me figure out how to load more products on coach.com because they are using div as a "load more button," directly clicking it does not work. I tried to use the link inside the div to get the information directly, but using that way is hard for me to get the information on the next page. I finally used selenium to simulate the mouse to move to the div and do the clicking, and it currently works. 

**What I Learned**
	It is my first time to crawl a website and use API. And I believe I have a better understanding of HTML structure right now.
