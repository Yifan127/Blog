### Terms ###

- Payload (reference to [payload](http://softwareengineering.stackexchange.com/questions/158603/what-does-the-term-payload-mean-in-programming))

The term 'payload' is used to distinguish between the 'interesting' information in a chunk of data or similar, and the overhead to support it. It is borrowed from transportation, where it refers to the part of the load that 'pays': for example, a tanker truck may carry 20 tons of oil, but the fully loaded vehicle weighs much more than that - there's the vehicle itself, the driver, fuel, the tank, etc. It costs money to move all these, but the customer only cares about (and pays for) the oil, hence, 'pay-load'.

In programming, the most common usage of the term is in the context of message protocols, to differentiate the protocol overhead from the actual data. Take, for example, a JSON web service response that might look like this (formatted for readability):
	
    {
		"status":"OK",
     	"data":
        {
            "message":"Hello, world!"
     	}
	}

In this example, the string Hello, world! is the payload, the part that the recipient is interested in; the rest, while vital information, is protocol overhead.

Another notable use of the term is in malware. Malicious software usually has two objectives: spreading itself, and performing some kind of modification on the target system (delete files, compromise system security, call home, etc.). The spreading part is the overhead, while the code that does the actual evil-doing is the payload.