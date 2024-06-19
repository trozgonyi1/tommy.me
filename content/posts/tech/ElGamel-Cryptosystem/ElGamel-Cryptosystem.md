---
title: Secure Communication Over Insecure Channels (ElGamel Cryptosystem)
date: 2024-06-19T10:00:25-04:00
summary: "Building the ElGamel cryptosystem in a C server"
url: "/posts/projects/ElGamel-Cryptosystem.md/"
showtoc: true
tags: ["Cryptography", "C", "Sockets"]
draft: false
cover:
    image: /tommy.me/posts/tech/ElGamel-Cryptosystem/pictures/elgamel.png
    alt: "ElGamel"
    caption: ""
---

To prepare for my research position studying lattice based cryptography, I have been reading through the textbook [An Introduction to Mathematical Cryptography](https://link.springer.com/book/10.1007/978-1-4939-1711-2). It begins by reviewing the foundations of early cryptosystems, like the Diffie-Hellmann key exchange, discete log problems and digital signatures. This book has a special focus on the underlying mathematics for each idea it presents, allowing the reading to gain true base level understanding of these ideas. This book is especially valueable as it has the most up to date information on coding theory, elliptic curves and lattice based cryptography.

# My Goals

### `Prepare for research`

I will be researching more efficient ways to create lattice based cryptosystems (LBC), so it only makes sense that I should be an expert on existing lattice based systems. To do so, it is important to set back and understand the foundations of what LBC are built on. This led me to reading about elliptic curves. Elliptic curves are an especially beautiful algebraic structing allowing for trapdoor functions. Essentially, we can take a point on one of these curves and repeatedly add it to itself, modulo some value N. This is an easy task done efficiently on a computer. However, it is extremely difficult to take a point, and figure out how many multiples of an original point it is. This gives us the basis for the cryptosystem.

### `Theory with practice`

Theory is nothing without practice. It's one thing to read about these cryptosystems, but another to actually build them. So, I decided to build the ElGamel cryptosystem. I chose this one because the foundation is quite simple. It uses very basic properties of group theory to create secure communication, very similar to RSA. In fact, both systems were originally based on the discrete log problem. To me it seemed pointless to just create a program to perform the encryption and decryption. I wanted to be able to interact with it. So, I decided to use some of what I learned in *systems programming*. In C, I created a server to accept connections and recieve a public key, use that to encrypt a message, and send it back to be decrypted by the client. This project was made so that I could learn the theory behind this system. I hard coded the message, and left the choice of prime modulus to the user, so it probably shouldn't be used to encrypt anything too sensitive. Now that I have implimented the classical ElGamel cryptosystem, I am creating a new version to use elliptic curves.

---


