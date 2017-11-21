---
title: "Denetim bayrakları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.flags
dev_langs: C++
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8c6f58e345669cb1898bc2717a7e42ddc8e2539
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="control-flags"></a>Denetim Bayrakları
Microsoft C çalışma zamanı kitaplığı hata ayıklama sürümü aşağıdaki bayraklar denetim yığın ayırma ve raporlama işlemi kullanır. Daha fazla bilgi için bkz: [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).  
  
|Bayrağı|Açıklama|  
|----------|-----------------|  
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Hata ayıklama sürümü dekiler temel heap işlevleri eşlemeleri|  
|[_DEBUG](../c-runtime-library/debug.md)|Çalışma zamanı işlevleri hata ayıklama sürümleri kullanılmasına izin verir|  
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Hata ayıklama yığını Yöneticisi ayırmaları nasıl izler denetler|  
  
 Bu bayrakların veya /D komut satırı seçeneği ile tanımlanan bir `#define` yönergesi. Ne zaman bayrağı ile tanımlanan `#define`, üst bilgi dosyasını dahil etmeden önce deyimi rutin bildirimleri yönergesi görünmesi gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global değişkenler ve standart türler](../c-runtime-library/global-variables-and-standard-types.md)