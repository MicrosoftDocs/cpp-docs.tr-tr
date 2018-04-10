---
title: Atama İşleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5bc7f1b0c2df820c3dc9e76b76dfcc72794e1906
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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