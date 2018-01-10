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
ms.workload: cplusplus
ms.openlocfilehash: 718058dae02e9dfe9b653abea91993ec6662f5c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4237"></a>Bağlayıcı Araçları Uyarısı LNK4237
'Dll dosyasından'; alırken belirtilen /SUBSYSTEM:NATIVE /Subsystem:Console veya /SUBSYSTEM:WINDOWS kullanın.  
  
 [/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) doğrudan windows (Win32) uygulaması derleme birini veya birkaçını kullandığında belirtildi:  
  
-   Kernel32.dll  
  
-   Gdi32.dll  
  
-   User32.dll  
  
-   msvcrt * DLL'leri biri.  
  
 Değil belirterek bu uyarıyı çözümlemek **/SUBSYSTEM:NATIVE**.