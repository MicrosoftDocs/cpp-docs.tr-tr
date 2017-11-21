---
title: "ANSI C uyumluluğu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Ansi
dev_langs: C++
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
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bd98d80c2fcbf3c684aa185b783f164d6b14f0a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ansi-c-compliance"></a>ANSI C Uyumluluğu
Tüm Microsoft özgü tanımlayıcıları çalışma zamanı sisteminde (örneğin, İşlevler, makroları, sabitleri, değişkenler ve tür tanımları) için adlandırma kuralı ANSI uyumludur. Bu belgede, ANSI/ISO C standartlarını takip eden herhangi bir çalışma zamanı işlevini ANSI uyumlu olacak şekilde belirtilir. ANSI uyumlu uygulamalar, yalnızca bu ANSI uyumlu işlevleri kullanmanız gerekir.  
  
 Microsoft'a özgü işlevler ve genel değişkenler adları tek bir alt çizgi ile başlar. Bu adları, yalnızca bir yerel olarak kodunuzun kapsamında kılınabilir. Örneğin, Microsoft çalışma zamanı üstbilgi dosyaları eklediğinizde adlı Microsoft özgü işlevi hala yerel olarak kılabilirsiniz `_open` aynı ada sahip yerel bir değişken bildirme tarafından. Ancak, bu ad genel işlevi veya genel değişkeni için kullanamazsınız.  
  
 Microsoft'a özgü makroları ve bildirim sabitleri adları iki alt çizgi veya bir büyük harf tarafından hemen ardından tek bir başında alt çizgi ile başlar. Bu tanımlayıcı mutlak kapsamıdır. Örneğin, Microsoft özgü tanımlayıcıyı kullanarak **_UPPER** bu nedenle.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uyumluluk](../c-runtime-library/compatibility.md)