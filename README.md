# Anton
A complete automation for Whatsapp Chat. It can reply to the messages to a group or person from your WhatsApp account without your intervention

> ![Whatsapp.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1633964229233/2XtLzrXv9.jpeg)

## Working of some of the major functions

- ### whatsappWebConnection()

`driver = webdriver.Chrome('C:\webdrivers\chromedriver.exe')`

This line is specifying where we’re getting our “driver” from. This driver is a file that contains instructions that let you interact with the browser, specifically Chrome browser in this case.

`driver.get(' web.whatsapp.com ')`

This line of code simply starts a new instance of our browser through our driver. This is where we’ll mess with Whatsapp. Make sure to start your links with “http” (and “https” where available).

`driver.implicitly_wait(15)`

This line tells our driver to wait for 15 seconds.

- ### getLastMessageFromChat()

In the "getLastMessageFromChat" function we are using those identifiers & elements to extract the last message sent/received from the chat. It just takes one parameter as a function argument which is the name of the Person or Group name in case it is the group

- ### sendMessage()
Similarly, in "sendMessage" we again take the Person/Group name & also the message to be sent as the 2 arguments & again with the help of certain identifiers & elements we are placing the text in the message textbox & pressing the send button

`msg_box = driver.find_element_by_xpath('//*[@id="main"]/footer/div[1]/div[2]/div/div[2]')`

In this line, we ask our driver to locate the little text field where we generally type our messages (based on its XPath). Once it finds that field, it will send a text to it.

`msg_box.send_keys(msg)`

`button = driver.find_element_by_class_name('_35EW6').click()`

Once the text is sent to the textbox in the chat, we are ready to hit the send button. This line does that for us, it locates the send button, and clicks on it using the click() method.

- ### startBot()
Now comes the last function which is the "startBot" function. It simply just calls all our utility functions & updates our text file with every new response message that we send.

> Note that we have to keep on calling this function at a particular interval for example every one min. This way every minute our script will pick the last message from the chat, compare it with the message in the text file & if found different, it will call other required functions to get a response which will be sent back.

## Blog
To understand the working of each and every step, you can checkout blog post => https://apoorvtyagi.tech/how-i-automated-my-whatsapp-chats.

## TODO
Add more data to train the Chatterbot
