---
title: Ön İşlemci işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fca1c097a01f34fb2cc708489338391dfced982f
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465505"
---
# <a name="preprocessor-operators"></a>Ön işlemci İşleçleri
`#define` yönergesi bağlamında, önişlemciye özgü dört işleç kullanılır (her birinin özeti için aşağıdaki listeye bakın). Dize haline getirme, karakter haline getirme ve belirteç yapıştırma işleçleri sonraki üç bölümde ele alınmıştır. Hakkında bilgi için `defined` işleci bkz [#if, #elif, #else ve #endif yönergeleri](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
|İşleç|Eylem|  
|--------------|------------|  
|[Dizeleyen işleç (#)](../preprocessor/stringizing-operator-hash.md)|Karşılık gelen gerçek bağımsız değişkenin çift tırnak içine alınmasına neden olur|  
|[Karakter haline getirme işleci (#@)](../preprocessor/charizing-operator-hash-at.md)|Karşılık gelen bağımsız değişkenin tek tırnak içine alınmasına ve karakter (Microsoft'a Özel) olarak kabul edilmesine neden olur|  
|[Belirteç yapıştıran işleç (#)](../preprocessor/token-pasting-operator-hash-hash.md)|Gerçek bağımsız değişken olarak kullanılan belirteçlerin başka belirteçler oluşturacak şekilde birleştirilmesine olanak verir|  
|[Defined işleci](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Bazı makro yönergelerinde bileşik ifadelerin yazımını basitleştirir|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)   
[Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)   
[C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)