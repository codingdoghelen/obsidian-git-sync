Backlink: [[Spring Framework]]

-

A few words on messaging and brokers in terms of JMS and AMQP.

AMQP is gaining more and more popularity this days. So I guess it's a good opportunity to see how does it match with the good old JMS.

JMS is a standard Java API for communicating with Message Oriented Middleware (MOM).

JMS is a part of the Java J2EE, and it's defined by JSR 914. It's considered to be robust and mature.  
JMS allows two different Java applications to communicate, those applications could be using JMS clients and yet still be able to communicate, yet kept being decoupled.

If you're looking for a JMS messaging broker you'll probably end up with ActiveMQ or HornetQ clients inside your code. Though ActiveMQ is more popular.

So, JMS allows Java components to send and receive messages reliably, with just a few lines of code, yet to be loosely coupled.

One can replace any JMS broker with another with minimal or even non changes in your code.

AMQP (which stands for 'Advanced Message Queuing Protocol') is kind of an open standard application layer protocol for delivering messages that was initially development by O'Hara from JPMorgan.

AMQP can queue and rout messages. It can go P-2-P (One-2-One), publish/subscribe, and some more, in a manner of reliability and secured way.

If you want AMQP you probably go for RabbitMQ, Qpid or StormMQ.

AMQP provides a description on how a message should be constructed. It doesn't provide an API on how the message should be sent.

OK, so we got JMS and we got AMQP that seems to be basically used for the same purpose. Not a smart move, is it?

Well… ==JMS is an API and AMQP is a protocol==.

JMS, back then when it was defined, actually didn't force a protocol between the JMS client and the JMS messaging server.

The JMS client, which implements the JMS API can use whatever protocol to communicate against the JMS server. However the JMS client needs to make sure to be compliant with the JMS API. That's it.

AMQP on other hand is nothing but a protocol between a messaging client and the messaging server. So a JMS client can use AMQP as the protocol to communicate with the messaging server.

Indeed it's already there, for instance, ActiveMQ is offering support for AMQP 1.0.

OK, so now we've a basic understanding on what JMS and AMQP are. Let's start thinking loudly here.

While there are implementations such as ActiveMQ, HornetQ and SonicMQ, that offer some level of cross products interoperability, that is being done thru proprietary protocols, APIs, and client libraries. You can't just replace one broker with anther without go to your code, as it was the case for Java applications. We're deep coupled here to a specified broker that can't easily replaced, if that's possible at all.

AMQP is around a binary wire protocol which was designed for interoperability between different vendors and platforms. As long it's AMQP complaint, changes at the broker level are not needed.

Let's take it one step further and consider the case where a Java client wants to send a message to a Ruby client. Or vice versa. Ruby client can't talk JMS, so we need a message broker that can bridge the two platforms, Java and Ruby. We might want to use STOMP for that via ActiveMQ. That seems to solve the problem, yet poorly. For instance, that'sbecause we're now coupled into a specific vendor solution.

But what if that's a C# client talking NMS API that's trying to connect to a Ruby client which is configured to use STOMP? It won't work. In real life scenario we can much more example using combinations of mixed platforms and requirements- point well taken, I guess.

This is where AMQP is becoming handy. AMQP provides a standard messaging protocol that stands across all platforms. It doesn't matter which AMQP client is used, as long as it's an AMQP complaint, it will hold. Client using AMQP is completely agnostic as to which AMQP client API or AMQP broker is used.

To wrap this up and end this short discussing, AMQP is all around of defining the 'what', and JMS is about defining the 'how'.