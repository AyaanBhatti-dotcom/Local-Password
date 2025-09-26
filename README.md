# Local-Password-Manager
This project demonstrates how to set up a **local password authentication system** on a Linux machine using **GPG** for encryption and **Pass** as a password manager.   It’s a hands-on lab that shows how to securely generate keys, store passwords, and manage them locally — no cloud needed.

<br> 
<br> 
<br> 

## STEP 1: Setting up your key ##

1. The command we will use is 

`gpg –gen-key`

<img width="468" height="22" alt="image" src="https://github.com/user-attachments/assets/c7b6a9b1-2869-4f53-9d48-ea17cedce0ba" />
<br>
<br>
2. It will then ask you for your name. You can provide your name or a pseudo name.
<br>
<img width="468" height="155" alt="image" src="https://github.com/user-attachments/assets/b99e6b8e-bd5e-4806-93b6-7ba4e91987fd" />
<br>
3. It will then ask for an email address. Same situation here. You can either use a real or fake email.
<img width="316" height="151" alt="image" src="https://github.com/user-attachments/assets/566a64cc-8d97-4773-b134-f25742356b3c" />
<br>
4. From here you can type o and enter.
<br>
<img width="468" height="171" alt="image" src="https://github.com/user-attachments/assets/4856b9cf-6df2-40cf-9371-efad779b739d" />
<br>
<br>
5. A window will pop up asking for a passphrase. Please pick a passphrase and remember it.
<img width="468" height="352" alt="image" src="https://github.com/user-attachments/assets/bbcc87a4-85d3-416a-b5ff-4b8d31611f14" />
<br>
NOTE: You may get this warning. For testing purposes we will disregard it for now.
<br>
<img width="384" height="179" alt="image" src="https://github.com/user-attachments/assets/bc837583-829b-4233-87ee-016d81680760" />
<br>
6. A key will now be generated.
Make sure to keep this key safe.
<br>
<img width="468" height="216" alt="image" src="https://github.com/user-attachments/assets/3d78b608-96f5-48e1-9174-20b732452230" />
<br>
## KEY ##  
<br>
<img width="448" height="30" alt="image" src="https://github.com/user-attachments/assets/5a6b0589-895b-4e93-b47e-4264c87ebfbf" />
<br>

### IMPORTANT: If you lose your key, you can use the command: ###

```bash
gpg -K
```
<img width="468" height="237" alt="image" src="https://github.com/user-attachments/assets/3e387864-2447-41d3-9767-c1db1a7f2c60" />



<br>
<br>
<br>

## STEP 2: CHANGING EXPIRATION DATE OF THE KEY ##

<br>
<br>

1. After doing gpg -K, we can see all the keys which we currently have.

<img width="468" height="237" alt="image" src="https://github.com/user-attachments/assets/6d7f24d9-0903-4472-93b4-7cb68cd263f7" />

<br>
You can see that I have two keys which are both for testing purposes. Let's look at the one we just created.
<br>
<br>
<br>
<img width="250" height="40" alt="image" src="https://github.com/user-attachments/assets/f544650b-2f76-414d-bbe3-223fb31cfa5b" />
<br>
The key shows that there is an expiration date which we can change.
<br>
<br>
2. To change the expiration date- use the command:

```bash
gpg --key-edit (replace this with key)
```

<br>
<img width="468" height="210" alt="image" src="https://github.com/user-attachments/assets/0f4acc0d-601d-4215-a0fa-b21bc73a9ce0" />
<br>
3. After this type:

```bash
expire
```
<br>
<img width="468" height="181" alt="image" src="https://github.com/user-attachments/assets/d12745d6-036a-4975-8b00-c6b6970c39ae" />
<br>
<br>
4. For now, we will set it so that it does not expire. It will then ask for the same passphrase that we entered at the beginning.
<br>
<img width="468" height="385" alt="image" src="https://github.com/user-attachments/assets/c5000112-1b46-4a09-9f02-90eb4242bcc7" />
<br>
5. Finally, type:

```bash
save
```
<br>
<img width="118" height="38" alt="image" src="https://github.com/user-attachments/assets/c6405a17-dcbe-42a7-adf3-d794306dafd5" />
<br>
The expiration date is now changed.
<br>
<br>
<br>



## STEP 3: Creating a Password Store and Repository ##

1. After this we will run this command to initialize a new password store.

```bash
pass init (key)
```
<br>
<img width="468" height="56" alt="image" src="https://github.com/user-attachments/assets/23fd1ef9-e8c4-4a9b-8955-3ea41b250d06" />
<br>

2. We will then run pass git init to create a new git repository. This will allow us to save passwords in a formatted way. The command we will use is:

```bash
pass git init
```

<br>
<img width="468" height="189" alt="image" src="https://github.com/user-attachments/assets/e529b486-2ee6-4a20-8a45-542358051450" />
<br>

### Once this repository is created, we can start adding passwords ###


## STEP 4: CREATING AND STORING PASSWORDS ##

1. You can add passwords by using the command:

```bash
pass insert (name of what the password is for)
```
<br>
<img width="468" height="62" alt="image" src="https://github.com/user-attachments/assets/3da9cd11-bfbc-404c-9ae0-c131600145f9" />
<br>
<br>
It will then ask for the password twice. After this, the password will be stored.
<br>
<br>

### NOTE: If we want to view the password, we can use the command: ###

```bash
pass show (name)
```
<br>
<img width="468" height="31" alt="image" src="https://github.com/user-attachments/assets/ec01e4c0-408d-45c7-a8d1-f8658e353072" />
<br>
<br>

2. Passwords can be organized into nested folders, allowing better structure (for example, work/github or personal/email).

```bash
pass insert (folder/name of what the password is for)
```
<br>
<img width="468" height="62" alt="image" src="https://github.com/user-attachments/assets/b971cb13-5394-4fce-bc08-3ea8b6a3740b" />
<br>
To view the password for this, we can use the same command as before with the correct directory:

```bash
pass show (folder/name of what the password is for)
```

<br>
<img width="727" height="56" alt="Screenshot 2025-09-26 at 16 02 07" src="https://github.com/user-attachments/assets/61af8dd8-b332-4fba-a686-96b58d71dafc" />
<br>




















