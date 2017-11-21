---
title: "Bağlayıcı araçları uyarısı LNK4237 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4237
dev_langs: C++
helpviewer_keywords: LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8cc822d4e7432a0a603df9da78b7c4d244719a09
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4237"></a>Bağlayıcı Araçları Uyarısı LNK4237
'Dll dosyasından'; alırken belirtilen /SUBSYSTEM:NATIVE /Subsystem:Console veya /SUBSYSTEM:WINDOWS kullanın.  
  
 [/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) doğrudan windows (Win32) uygulaması derleme birini veya birkaçını kullandığında belirtildi:  
  
-   Kernel32.dll  
  
-   Gdi32.dll  
  
-   User32.dll  
  
-   msvcrt * DLL'leri biri.  
  
 Değil belirterek bu uyarıyı çözümlemek **/SUBSYSTEM:NATIVE**.