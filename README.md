# python-psbt

## About

This is a python implementation of BIP 174 - Partially Signed Bitcoin Transaction format as defined 
here: https://github.com/bitcoin/bips/blob/master/bip-0174.mediawiki

Please reference the above wiki for BIP 174 to understand how it works.

This is only an initial version for proof of concept and study. Please do not deploy for mainnet use without significantly reviewing and testing code for yourself.

That being said, I am very eager for feedback and additional testing to get this to a reliable version. Please feel free to ask questions.  

## Support

I have only tested this using python 3.6

## Install

Download psbt.py and bitcoin\_lib.py and place together in desired directory. bitcoin\_lib.py is needed for parsing/serializing of transactions and scripts, as well as some other general functions.

bitcoin\_lib is a library of basic bitcoin functions that was primarily written as part of @jimmysong's Programming Blockchain course and additionally augmented by parts of his pybtcfork claimer. I have made a few additions, mainly just for understanding of more script types. 

## Test Vectors

Optionally, you can also download test\_psbt.py which contains all the test vectors here: https://github.com/bitcoin/bips/blob/master/bip-0174.mediawiki#Test_Vectors

Note that this test vectors are not exhaustive.

## Use 

Instantiate either a Creator, Updater, Signer, Combiner, Input Finalizer or Transaction Extractor 
object depending on the responsibility of the entity.

Different PSBT roles have different requirements and scopes and should stick only to those. Take note of the argument types they expect.

At this time, most functions expect data arguments to be raw bytes. Any PSBT role that has a constructor
that expects a PSBT as an argument, expects it to be in bytes.

You can parse a base64 encoded PSBT and get the base64 representation of one as well.

Index arguments are expected to be ints and at this time getting/adding sighash types is expected 
to be of type int

## Future work

There is still work to do here, a lot of which is TODO tagged in comments. Currently there are a few assumptions made that can be limiting, which I will get to. 

I would like more test vectors added as well. There should be more exhaustive testing of different input types.

I intend to trim down bitcoin\_lib.py quite a bit or perhaps use something different. I chose it for now because I understand it the best. 