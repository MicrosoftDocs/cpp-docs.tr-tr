---
title: ANSI C uyumluluğu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- Ansi
dev_langs:
- C++
helpviewer_keywords:
- underscores, leading
- compatibility [C++], ANSI C
- compliance with ANSI C
- conventions [C++], Microsoft extensions
- underscores
- naming conventions [C++], Microsoft library
- ANSI [C++], C standard
- Microsoft extensions naming conventions
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 452c6803ea05f051727a1417aee49c3a56759141
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ansi-c-compliance"></a>ANSI C Uyumluluğu
Tüm Microsoft özgü tanımlayıcıları çalışma zamanı sisteminde (örneğin, İşlevler, makroları, sabitleri, değişkenler ve tür tanımları) için adlandırma kuralı ANSI uyumludur. Bu belgede, ANSI/ISO C standartlarını takip eden herhangi bir çalışma zamanı işlevini ANSI uyumlu olacak şekilde belirtilir. ANSI uyumlu uygulamalar, yalnızca bu ANSI uyumlu işlevleri kullanmanız gerekir.  
  
 Microsoft'a özgü işlevler ve genel değişkenler adları tek bir alt çizgi ile başlar. Bu adları, yalnızca bir yerel olarak kodunuzun kapsamında kılınabilir. Örneğin, Microsoft çalışma zamanı üstbilgi dosyaları eklediğinizde adlı Microsoft özgü işlevi hala yerel olarak kılabilirsiniz `_open` aynı ada sahip yerel bir değişken bildirme tarafından. Ancak, bu ad genel işlevi veya genel değişkeni için kullanamazsınız.  
  
 Microsoft'a özgü makroları ve bildirim sabitleri adları iki alt çizgi veya bir büyük harf tarafından hemen ardından tek bir başında alt çizgi ile başlar. Bu tanımlayıcı mutlak kapsamıdır. Örneğin, Microsoft özgü tanımlayıcıyı kullanarak **_UPPER** bu nedenle.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uyumluluk](../c-runtime-library/compatibility.md)