---
title: Sending System-Exclusive Messages
description: Sending System-Exclusive Messages
ms.assetid: 2bb95e4e-004e-46c8-9c56-25436fcc7f6c
keywords:
- Musical Instrument Digital Interface (MIDI),sending messages
- MIDI (Musical Instrument Digital Interface),sending messages
- playing MIDI files,sending messages
- sending MIDI messages
- Musical Instrument Digital Interface (MIDI),system-exclusive messages
- MIDI (Musical Instrument Digital Interface),system-exclusive messages
- playing MIDI files,system-exclusive messages
- system-exclusive MIDI messages
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Sending System-Exclusive Messages

MIDI system-exclusive messages are the only MIDI messages that will not fit into a single doubleword value. System-exclusive messages can be any length. Windows provides the [**midiOutLongMsg**](https://msdn.microsoft.com/en-us/library/Dd798474(v=VS.85).aspx) function for sending system-exclusive messages to MIDI output devices. To specify MIDI system-exclusive data blocks, use the [**MIDIHDR**](https://msdn.microsoft.com/en-us/library/Dd798449(v=VS.85).aspx) structure.

After you send a system-exclusive data block using **midiOutLongMsg**, you must wait until the device driver is finished with the data block before freeing it. If you are sending multiple data blocks, you must monitor the completion of each data block so you know when to send additional blocks. For information about different techniques for monitoring data-block completion, see [Managing MIDI Data Blocks](managing-midi-data-blocks.md).

> [!Note]  
> Any MIDI status byte other than a system-real-time message will terminate a system-exclusive message. If you are using multiple data blocks to send a single system-exclusive message, do not send any MIDI messages other than system-real-time messages between data blocks.

 

 

 



