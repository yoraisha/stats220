# **Assignment 1 Part A**

## Meme
![my_meme](https://user-images.githubusercontent.com/100745324/158104180-a26d4212-232d-48eb-8d6f-4e68d3a35c61.png)

## Meme R Code
```r
library(magick)

happy_dog <- image_read("https://cdn.pixabay.com/photo/2016/11/19/15/20/dog-1839808_1280.jpg") %>%
  image_scale(500) 

happy_text <- image_blank(width = 500, height = 500,
                           color = "#FFFFFF") %>%
  image_annotate(text = "getting to make\na meme", font = "Comic Sans", color = "#000000",
                 size = 65, gravity = "center")

sad_dog <- image_read("https://cdn.pixabay.com/photo/2018/09/24/17/29/sad-3700421__340.jpg") %>%
  image_scale(500)

sad_text <- image_blank(width = 500, height = 500,
                            color = "#FFFFFF") %>%
  image_annotate(text = "having to be\ncreative", font = "Comic Sans", color = "#000000",
                 size = 65, gravity = "center") 

top_row <- c(happy_dog, happy_text) %>%
  image_append()

bottom_row <- c(sad_dog, sad_text) %>%
  image_append()

meme <- c(top_row, bottom_row) %>%
  image_append(stack = TRUE) %>%
  image_border("black", "20x20") %>%
  image_scale(350)
  
 image_write(meme, "my_meme.png")
 ```
