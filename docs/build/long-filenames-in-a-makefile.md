---
title: "Derleme görevleri dosyasında uzun dosya adları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, long filenames
- long filenames
ms.assetid: 626d56fc-8879-46ba-9c2d-dd386c78cccc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43e34f3c4aba212f373a5c44535533f38f1bf216
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="long-filenames-in-a-makefile"></a>Derleme Görevleri Dosyasında Uzun Dosya Adları
Uzun dosya adları gibi çift tırnak işaretleri içine alın:  
  
```  
all : "VeryLongFileName.exe"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme görevleri dosyası içeriği](../build/contents-of-a-makefile.md)