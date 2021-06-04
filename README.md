# LabVIEW Reddit Coding Challenge - June 2021

Submitter: u/itmelo

Challenge URL: https://www.reddit.com/r/LabVIEW/comments/nplfq0/labview_reddit_coding_challenge_june_2021/

In this code challenge, I implemented a way to encode a text message in the Nyx the Owl.bmp. I used a classic stegenography approach in
which I encode the ASCII value of each character into the LSBs of each pixels' R/G/B components. In particular, the my implementation 
modifies a single color component, at most, by 111b (7); the whole pixel may change by up to 127 (1111111b). See VI for details.

# Code

The following VIs are required:
- Test Encode and Decode.vi                    // the main VI to test algorithms and calculate score
- Encode Message.vi                            // my encoding implementation VI
- Decode Message.vi                            // my decoding implementation VI
- calculate rgb with encoded ascii.vi          // a subvi I made to do the LSB-loading
- split u8 into lower middle and upper bits.vi // a subvi I made to do some boolean data manipulation

# Expected results
I copied and pasted the contents of the "Data to Encode.txt" some number of times... maybe 12 times? But the maximum value I can encode 
and match as reported by "Test Encode and Decode.vi" is 1000497 with a score of 0.0289418. In this algorithm, the number of characters I can encode is limited to the number of pixels in the image. These results can be observed in the provided "front panel preview.png" file.

# Improvement ideas
For the sake of the challenge, I think I'm satisfied with what I submitted. But I remembered I have VIs that can compress and decompress a string using .NET gzip (mscorplib 2.0). The algorithm I've used would have to extend the 7-bit to accept 8-bit because the characters would be exepcted to use the 256 values of extended ASCII. As a result, instead of filling the 2/2/3 r/g/b LSBs, fill the 2/3/3 r/g/b LSBs (the full 8-bits!). This would allow, maybe, 30 times more bytes to be stored!  
