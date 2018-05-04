---
title: _crtDbgFlag | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb0c22e65c33ab8f689026e916f550280bf6a8ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="crtdbgflag"></a>_crtDbgFlag
**_CrtDbgFlag** bayrağı nasıl bellek ayırmaları öbek hata ayıklama sürümünde izlenen, doğrulandı, bildirilen yazılan ve denetleyen beş bit alanları oluşur. Bit alanları bayrağı kullanılarak ayarlanan [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) işlevi. Bu bayrak ve bit alanları Crtdbg.h bildirilir. Bu bayrak yalnızca kullanılabilir [_DEBUG](../c-runtime-library/debug.md) bayrağı uygulamada tanımlandı.  
  
 Bu bayrak diğer hata ayıklama işlevleri ile birlikte kullanma hakkında daha fazla bilgi için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim Bayrakları](../c-runtime-library/control-flags.md)