---
title: Atama İşleçleri | Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf4204e55811cd33fa48e2b3a07d3058100729ac
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="casting-operators"></a>Atama İşleçleri
C++ diline özgü birkaç atama işleci vardır. Bu işleçler, eski stil C dili atamalarında bulunan belirsizliğin ve tehlikenin bir kısmının giderilmesini amaçlar. Bu işleçler şunlardır:  
  
-   [dynamic_cast](../cpp/dynamic-cast-operator.md) biçimli türleri dönüştürme için kullanılır.  
  
-   [static_cast](../cpp/static-cast-operator.md) nonpolymorphic türleri dönüştürme için kullanılır.  
  
-   [const_cast](../cpp/const-cast-operator.md) kaldırmak için kullanılan `const`, `volatile`, ve `__unaligned` öznitelikleri.  
  
-   [reinterpret_cast](../cpp/reinterpret-cast-operator.md) BITS basit reinterpretation için kullanılır.  
  
-   [safe_cast](../windows/safe-cast-cpp-component-extensions.md) doğrulanabilen MSIL üretmek için kullanılır.  
  
 Bu işleçler eski stil atamalarla aynı tehlikeleri arz ettiği için son çare olarak `const_cast` ve `reinterpret_cast` kullanın. Bununla birlikte, eski stil atamaları tamamen değiştirmek için gereklidirler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama](../cpp/casting.md)