# OCR-Parser-for-Receipts

A parser was developed for the OCR output of a receipt format, thus seeking to transform the unstructured data contained in an image, into structured data representative of a sale.

## Used Libraries

- Pillow: for image graphing and boxese visualzation
- Fuzzywuzzy: for string similarity analisys
- Re: for some techniques that help find information easier

## Approaches for Getting Information 

- get_by_regex(boxes, regex, full_match=False)

Method that recieving the boxes of the document, a regular expression and a flag for match type, find all the boxes texts that match the regular expression and the fragment of the text that matched.

- get_by_vertival_position(boxes, index)

Method that return a box based on its vertical position and its text

- get_by_similarity(boxes, search, min_similarity)

Methot that finds every box that has a min_similarity to a given search text, and returns them into a list, sorted by its similarity

- get_by_down_direction(boxes, box, number)

Method that returns the next <number> boxes below a given box, the boxes list should be sorted by vertical position
  
- get_by_right_direction(boxes, box)
  
Method that finds all the boxes that are on the right side of a given box, and returns them into a list sorted by its vertical alignment similarity to a given box
  
## Data Extraction (Main Method)
  
Based on the approaches mentioned before, this method find the main information of the total boxes, and creates a dictionary with the found information
