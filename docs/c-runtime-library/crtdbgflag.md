---
title: _crtDbgFlag | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
dev_langs: C++
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 559dba68c8c171fbc84be17e64c2628b4bbf5011
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crtdbgflag"></a>_crtDbgFlag
**_CrtDbgFlag** bayrağı nasıl bellek ayırmaları öbek hata ayıklama sürümünde izlenen, doğrulandı, bildirilen yazılan ve denetleyen beş bit alanları oluşur. Bit alanları bayrağı kullanılarak ayarlanan [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) işlevi. Bu bayrak ve bit alanları Crtdbg.h bildirilir. Bu bayrak yalnızca kullanılabilir [_DEBUG](../c-runtime-library/debug.md) bayrağı uygulamada tanımlandı.  
  
 Bu bayrak diğer hata ayıklama işlevleri ile birlikte kullanma hakkında daha fazla bilgi için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim bayrakları](../c-runtime-library/control-flags.md)