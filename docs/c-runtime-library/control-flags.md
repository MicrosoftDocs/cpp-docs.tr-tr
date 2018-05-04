---
title: Denetim bayrakları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bfd37a3d76a39748efc0352df829a7b5c57146a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [Global Değişkenler ve Standart Türler](../c-runtime-library/global-variables-and-standard-types.md)