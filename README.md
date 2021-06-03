# LabVIEW Reddit Coding Challenge - June 2021

Submitter: u/itmelo

Challenge URL: https://www.reddit.com/r/LabVIEW/comments/nplfq0/labview_reddit_coding_challenge_june_2021/

In this code challenge, I implemented a way to encode a text message in the Nyx the Owl.bmp. I used a classic stegenography approach in
which I encode the ASCII value of each character into the LSBs of each pixels' R/G/B components. In particular, the my implementation 
modifies a single color component, at most, by 111b (7); the whole pixel may change by up to 127 (1111111b). See VI for details.

# Code

The following VIs are required:
- Encode Message.vi                            // my encoding implementation VI
- Decode Message.vi                            // my decoding implementation VI
- calculate rgb with encoded ascii.vi          // a subvi I made to do the LSB-loading
- split u8 into lower middle and upper bits.vi // a subvi I made to do some boolean data manipulation

# Expected results
I copied and pasted the contents of the "Data to Encode.txt" some number of times... maybe 12 times? But the maximum value I can encode and match as reported by "Test Encode and Decode.vi" is 1000497.
This can be observed in the provided "front panel preview.png" file.