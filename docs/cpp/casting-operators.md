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
ms.openlocfilehash: 4d64a25475ad7ac40f63d29798768f8f57866b3c
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941631"
---
# <a name="casting-operators"></a>Atama İşleçleri
C++ diline özgü birkaç atama işleci vardır. Bu işleçler, eski stil C dili atamalarında bulunan belirsizliğin ve tehlikenin bir kısmının giderilmesini amaçlar. Bu işleçler şunlardır:  
  
-   [dynamic_cast](../cpp/dynamic-cast-operator.md) çok biçimli türlerin dönüştürülmesi için kullanılır.  
  
-   [static_cast](../cpp/static-cast-operator.md) dönüştürme olmayan türlerin dönüştürülmesi için kullanılır.  
  
-   [const_cast](../cpp/const-cast-operator.md) kaldırmak için kullanılan **const**, **geçici**, ve **__unaligned** öznitelikleri.  
  
-   [reinterpret_cast](../cpp/reinterpret-cast-operator.md) bitlerin basit reinterpretation için kullanılır.  
  
-   [safe_cast](../windows/safe-cast-cpp-component-extensions.md) doğrulanabilir MSIL oluşturmak için kullanılır.  
  
 Bu işleçler eski stil atamalarla aynı tehlikeleri arz ettiği için son çare olarak `const_cast` ve `reinterpret_cast` kullanın. Bununla birlikte, eski stil atamaları tamamen değiştirmek için gereklidirler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama](../cpp/casting.md)