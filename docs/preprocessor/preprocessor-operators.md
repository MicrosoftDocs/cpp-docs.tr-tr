---
title: "Ön İşlemci işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c0eaa2a5c689dbe63957e5a0d5dcb8bbd1959949
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="preprocessor-operators"></a>Ön işlemci İşleçleri
`#define` yönergesi bağlamında, önişlemciye özgü dört işleç kullanılır (her birinin özeti için aşağıdaki listeye bakın). Dize haline getirme, karakter haline getirme ve belirteç yapıştırma işleçleri sonraki üç bölümde ele alınmıştır. Hakkında bilgi için **tanımlanan** işleci, bkz: [#if, #elif, #else ve #endif yönergeleri](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
|İşleç|Eylem|  
|--------------|------------|  
|[Dizeleyen işleç (#)](../preprocessor/stringizing-operator-hash.md)|Karşılık gelen gerçek bağımsız değişkenin çift tırnak içine alınmasına neden olur|  
|[Karakterleştirme işleci (#@)](../preprocessor/charizing-operator-hash-at.md)|Karşılık gelen bağımsız değişkenin tek tırnak içine alınmasına ve karakter (Microsoft'a Özel) olarak kabul edilmesine neden olur|  
|[Belirteç yapıştıran işleç (#)](../preprocessor/token-pasting-operator-hash-hash.md)|Gerçek bağımsız değişken olarak kullanılan belirteçlerin başka belirteçler oluşturacak şekilde birleştirilmesine olanak verir|  
|[DEFINED işleci](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Bazı makro yönergelerinde bileşik ifadelerin yazımını basitleştirir|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)   
 [Önceden tanımlı makrolar](../preprocessor/predefined-macros.md)   
 [C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)