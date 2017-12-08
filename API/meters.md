Create a service to accept Meter Reads
======================================

Thank-you for showing interest in working with us!

The following test is used to gauge your technical ability and is a precursor to an interview here. You have seven days to complete this task, and you should work with your representative for more information should you need it. 

## Intro

Blue Energy is an established utility company, and they have approached us to create a service for accepting meter reads. The main goal here is to *accept*, *store* and *present* meter readings based on a customer's unique identifier.

## Specification

Your task is to create an API that can *accept*, *validate*, *store* and *present* meter readings. It will connect to a legacy service which currently posts this elsewhere. We would like the following routes on this API:

* Accept - the route to accept a meter read should contain the URI `/meter-read`. It should accept a meter reading in JSON format using the schema specified below in the schema section.
* Present - the route to present a meter read should use identifiers for the meter and the customer to personalise what is returned. It should return the reads in a similar JSON format to the accept method. 

Since we are a tech-first company, and service will be business critical, we expect this service to have extensive unit testing to ensure quality and maintenance. You can use any language or framework you wish to complete this.

## Schema

    {
        "customerId": "identifier123",
        "serialNumber": "27263927192",
        "mpxn": "14582749",
        "read": [
            {"type": "ANYTIME", "registerId": "387373", "value": "2729"},
            {"type": "NIGHT", "registerId": "387373", "value": "2892"}
        ],
        "readDate": "2017-11-20T16:19:48+00:00Z"
    }

## Notes/Tips

* You do not have to follow the spec blindly provided you can explain any modifications.
* You can add to the schema.
* Customer ID is a unique identifier for a customer, it must always be globally unique 
* Serial Number is the meter serial number is used to identify a meter, this number should be unique, however uniqueness cannot be assured.
* Register ID is the serial number on the register for that particular register, It can be used to uniquely identify a register, but not an energy supply.
* MPXN this is the meter point number: MPAN for Electric, MPRN for Gas. This can be used to uniquely identify a supply point.
