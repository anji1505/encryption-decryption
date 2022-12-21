# Encryption-Decryption

## How To Encrypt File on Linux

 * If you are a conscientious system administrator, you have probably already wondered how you can make your files secure.

 * Nowadays, as system attacks get more and more frequent, it isn’t probably a bad idea to think about encrypting your files.

 * On Linux, there are multiple of encrypting files, directories or filesystems : namely using the LUKS disk encryption specification  or simple tools such as GnuPG.

## Table of Contents

     1.Encrypt Files using passphase protection

       1.1 Decrypt Encrypted File on Linux

       1.2 Encrypt Directory using gpg

       1.3 Encrypt Directory using zip

     2.Encrypt Files using private key

       2.1Decrypt File using key

     3.Encrypt Files using Nautilus GUI

       3.1Decrypt using GUI Interface


# Encrypt Files using passphase protection

  * In the process of Encryption, I created one new directory by using ``mkdir`` command.

  * In that directory I created three new text files like f1.txt, f2.txt, f3.txt.

  * Once I created directory and files, I created a ``zip`` file for them by using ``sudo zip -r <filename.zip> <filename>`` 

    ![Screenshot_20221221_070840](https://user-images.githubusercontent.com/116748521/208918473-2839fa8b-f0ff-4054-828b-65fb89e2769a.png)

  * Whenever I created `zip` file for them, Than I ran the ``Encryption`` process for that `zip` file by using below command.
   
      ``sudo gpg --batch --output <filename> --passphrase mypassword --symmetric <filename>``
  * When Encrypt done I checked md5sum for that encryption file by using below command.
   
       ``md5sum <filename> <file path> ``
	
	![Screenshot_20221221_071859](https://user-images.githubusercontent.com/116748521/208920601-cf28003e-2eca-4716-9b0c-1a0a5cfb7dc5.png)

  * ``Note``: whenever we created encryption of the file at that time it was not supporting for unzip.
 
## One of the easiest ways of encrypting a file on Linux is to use the “gpg” utility.

   * “gpg” is a simple utility that is part of the OpenPGP initiative that aims at providing easy methods to securely sign documents.  
   * Files can be decrypted using two different methods : a password or a key file. In this section, we are going to focus on setting up a password protection for your encrypted files.

## To encrypt files using a password, use the “gpg” command with the “-c” option specifying that you want to use a symmetric encryption   for your file. After that, specify the name of the file that you want to encrypt.

    ``sudo gpg --batch --output <filename> --passphrase mypassword --symmetric <filename>``

                                     or

      `` gpg -c <file> ``

 * The “gpg” command will create a file with a “.gpg” extension which is the encrypted file that you want to store
 
   ![Screenshot_20221221_064950](https://user-images.githubusercontent.com/116748521/208915073-7f275099-0121-4764-bd64-9e33c77c4dab.png)

 * If you are running a Linux distribution with a graphical environment, you will be prompted with a window in order to specify the passphrase.
   
   ![Screenshot_20221221_065331](https://user-images.githubusercontent.com/116748521/208915478-c0df4097-a5bd-4a9e-8a81-78a1c779cac8.png)

 * ``Note`` : make sure not to forget your passphrase. You won’t be able to recover the passphrase in any means.

 * If you were to inspect the content of the file using a simple ``cat``command, you would not be able to see the content.

    ![Screenshot_20221221_065754](https://user-images.githubusercontent.com/116748521/208916331-a5b23b54-a94d-43cc-a99b-fe141fd1d4e3.png)


 ## Decrypt Encrypted File on Linux:-

  *  In order to decrypt an encrypted file on Linux, you have to use the “gpg” command ``sudo gpg --batch --output <filename> --decrypt <filename>`` with the  for “decrypt” and specify the “.gpg” file that you want to decrypt.

  `` command``:-
   
    ``sudo gpg --batch --output <filename> --decrypt <filename>``
	
 * when I created decrypted to encryption file at that time I get one more zip file  	
   
    ![Screenshot_20221221_073828](https://user-images.githubusercontent.com/116748521/208924594-9f78b2fe-16ac-43cb-b619-a7f1b7f3b521.png)

 * at that time it was asking again ``passphrase``
 
   ![Screenshot_20221221_065331](https://user-images.githubusercontent.com/116748521/208925491-3cadcc37-63da-45c0-9a93-478c5c939c61.png)

 * when I created decryption at that time I got more zip file.
  
  ![Screenshot_20221221_074434](https://user-images.githubusercontent.com/116748521/208925782-a84b8bb2-1be4-427a-8f1b-adf74eae0aac.png)

 * After taht I checked md5sum for that decryption file.

  ![Screenshot_20221221_074729](https://user-images.githubusercontent.com/116748521/208926360-f3fea5f3-9f6c-449b-b53f-107cd50f0d0c.png)
 
 * when I checked md5sum at that time I got same ``string`` 
   
    ``Encrypt string``
    
	   d3376e6401bb97a537271780de1b259e
	
	`` Decrypt string``
	
	   d3376e6401bb97a537271780de1b259e
	   
 * after that I unziped the whatever I got the decryption zip file by using below command.
 
     ``sudo unzip <filename> . ``
     ![Screenshot_20221221_081229](https://user-images.githubusercontent.com/116748521/208931523-5f1b20de-d948-4bd5-b65e-b58c91cfddc3.png)

  * Successfully Encryption and Decryption completed.  
