---
title: Bağlayıcı araçları uyarısı LNK4237 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4237
dev_langs:
- C++
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5acccf52d3738985c7a83432342952af03bf78b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302873"
---
# <a name="linker-tools-warning-lnk4237"></a>Bağlayıcı Araçları Uyarısı LNK4237
'Dll dosyasından'; alırken belirtilen /SUBSYSTEM:NATIVE /Subsystem:Console veya /SUBSYSTEM:WINDOWS kullanın.  
  
 [/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) doğrudan windows (Win32) uygulaması derleme birini veya birkaçını kullandığında belirtildi:  
  
-   Kernel32.dll  
  
-   Gdi32.dll  
  
-   User32.dll  
  
-   msvcrt * DLL'leri biri.  
  
 Değil belirterek bu uyarıyı çözümlemek **/SUBSYSTEM:NATIVE**.