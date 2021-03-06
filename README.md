#==============================================================================
# FILE: README
#
# DESCRIPTION:
# Instructions for brain corp code sample
#
#==============================================================================

Install
================
tar -xvzf <package>

Build
===============
make

Run Tests
===============
make check


File Summary
=============
README.md - this file
makefile - make file to build and run tests
test.c - test code that contains code sample function

Problem Statement
====================
From: Teresa Allen <comm_20170204004555_UIR8STMRBYBUGD6I@dropbox.jazz.co>
To: Brooke Wallace <brookbot@yahoo.com>
Sent: Friday, February 3, 2017, 4:45:57 PM PST
Subject: Program Sample for Software Engineer - Firmware at Brain Corporation

Please provide a code example written in C that dispatches messages based upon their type. There are two message types "display" and "motor".  These two message types are mixed into the same packet format and the function that needs to be written needs to distinguish between these two messages and call the appropriate function.  Display messages must be passed to the function called display_message() and motor messages must be passed to a function called update_motor().  Please write function declarations for these functions but empty function bodies are fine.

The packet format uses little-endian data and has the following fields of the specified fields:
packet_id (byte, position 0)
message_type (byte, position 1)
message_length (2 bytes, positions 2 to 3)
message_data (positions 4 to 4+message_length)

message_type values:
0x34: display message
0x80: motor message

message_data for display messages is a ASCII string of length message_length

message_data for motor messages is composed of the following data structure:
forward_back (float32, positions 0 to 3)
left_right (float32, positions 4 to 7)

Example packets for each message are defined below:
uint8_t display_packet[] = {0x1, 0x34, 0x05, 0x0, 0x48, 0x65, 0x6c, 0x6c, 0x6f};

uint8_t motor_packet[] = {0x2, 0x80, 0x08, 0x0, 0x0, 0x0, 0x80, 0x3f, 0x0, 0x0, 0x0, 0xbf};

Please note, we will verify your code by using gcc from a modern version of Ubuntu (14.04+).  Please send back a zip file with your code and any build instructions.


Finally, please discuss how you would change the packet and message structures to make communication more robust.

