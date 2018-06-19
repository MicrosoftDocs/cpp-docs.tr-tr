---
title: İşlev bildirimli depolama sınıfı tanımlayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function specifiers, storage class
- declaring functions, specifiers
- external declarations
- specifiers, function
- external linkage, function declarations
- external linkage, storage-class specifiers
ms.assetid: 801d7df2-efa9-4924-a725-274a5654cfd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f84455dd29023194e64fa4e594419630ef2656e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389669"
---
# <a name="storage-class-specifiers-with-function-declarations"></a>İşlev Bildirimli Depolama Sınıfı Tanımlayıcıları
Kullanabilirsiniz **statik** veya `extern` işlev bildirimleri depolama sınıfı tanımlayıcısı. İşlevlerin her zaman genel kullanım ömürleri vardır.  
  
 **Microsoft özel**  
  
 İç düzeydeki işlev bildirimleri, dış düzeydeki işlev bildirimleri ile aynı anlama sahiptir. Bu, yerel kapsamda bildirilmiş olsa bile bir işlevin, çeviri biriminin geri kalanında, bildirim noktasında görülebilir olması anlamına gelir.  
  
 **SON Microsoft özel**  
  
 İşlevler için görünürlük kuralları, aşağıdaki belirtildiği gibi değişkenlerle ilgili kurallara göre biraz farklıdır:  
  
-   Bir işlev bildirilen olmasını **statik** yalnızca tanımlanmış kaynak dosya içinde görünür. Aynı kaynak dosyasındaki işlevleri çağırabilir **statik** işlevi, ancak diğer kaynak dosyalarda işlevleri erişemiyor, doğrudan adına göre. Başka bir bildirebilir **statik** işlevi bir çakışma olmadan farklı kaynak dosyasında aynı ada sahip.  
  
-   Bildirilen işlevler olarak `extern` program tüm kaynak dosyaları boyunca görülebilir (daha sonra bu tür bir işlevi olarak redeclare sürece **statik**). Herhangi bir işlev `extern` işlevini çağırabilir.  
  
-   Depolama sınıfı belirticisini atlayan işlev bildirimleri varsayılan olarak `extern`'dir.  
  
 **Microsoft özel**  
  
 Microsoft yeniden tanımlama sağlayan bir `extern` tanımlayıcı olarak **statik**.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Depolama Sınıfları](../c-language/c-storage-classes.md)