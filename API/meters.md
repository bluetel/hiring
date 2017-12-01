Create a service to accept meter reads
======================================

Thanks for showing interest in working with us, the following test is used to gauge where you are technically and is a precursor for an interview here. You will have 7 days to complete the following task and you should work a long side your representative for information should you need it. 

## Intro

Blue energy is an established utility company, they have approached us to create them a microservice that can accept meter reads. The main goal here is to accept, store and present meter readings based on a customers unique identifier.

## The Spec

Your task is to create an api that can accept, validate, store and present meter readings. It will be connected to a legacy service that currently posts this elsewhere. We would like the following routes on this API:

* Accept - the route to accept a meter read should contain the uri `/meter-read`. It should accept a meter reading in JSON format using the schema specified below in the schema section.
* Present - the route to present a meter read should use identifiers for the meter and the customer to personalise what is returned. It should return the reads in a similar json format to the accept method. 

Since we are a tech first company we expect that this service has extensive unit tests to ensure quality and maintanence. You can use any language/framework you want to complete this.

## Schema

    {
        "customerId": "identifier123",
        "serialNumber": "27263927192",
        "mpxn": "14582749",
        "read": [
            {"type": "ANYTIME", "registerId": "387373", "value": "2729"},
            {"type": "NIGHT", "registerId": "387373", "value": "2892"}
        ],
        "readDate": "2017-11-20T16:19:48+00:00"
    }

## Notes/Tips

* You do not have to follow the spec blindly, as long as you can explain the changes you have made.
* You can add to the schema
* Customer id is a unique identifier for a customer, it is globally unique 
* Serial number is the meter serial number is used to identify a meter, this number should be unique, however uniqueness cannot be assured.
* RegisterId is the serial number on the register for that particular register, It can be used to uniquely identify a register, but not an energy supply.
* MPXN this is the meter point number, MPAN for electric, MPRN for gas. This can be used to uniquely identify a supply point.
