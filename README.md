# KafkaStream

This Kafka application consumes input records from two topics, namely classroom and students, and produces output records to a third topic.

It outputs (i.e., commit to the output topic) the names of rooms for which the current occupancy exceeds the maximum capacity, along with some additional information that depends on the particular state change. 
- Each time a state change in occupancy or capacity occurs such that the occupancy of a room exceeds its capacity after the state change, the application should output a string key-value pair of the following form:
Room_ID,occupancy_after_state_change
- Each time a state change in occupancy or capacity occurs such that the occupancy of a room was above its capacity before the state change, and is equal to or below its capacity after the state change, the application should output a string key-value pair of the following form:
Room_ID,OK

The implementation tolerate crash failures, and the stream application is able to resume processing and publish messages to the output topic as if the crash failure did not occur.
