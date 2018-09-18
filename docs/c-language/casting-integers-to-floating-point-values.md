---
title: Kayan nokta değerlerine tam sayılar atama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a81b72a7dfedbc1d6033d53bde63be22943abb08
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055227"
---
# <a name="casting-integers-to-floating-point-values"></a>Kayan Nokta Değerlerine Tam Sayılar Atama

**ANSI 3.2.1.3** bir tamsayı, tam olarak orijinal değeri temsil edemeyen bir kayan noktalı sayı dönüştürüldüğünde kesilme yönü

Bir tamsayı, tam olarak değeri temsil edemeyen bir kayan nokta değerine atandığında, değer en yakın uygun değere yuvarlanır (aşağı veya yukarı).

Örneğin, bir **işaretsiz uzun** (ile 32 bit kesinliği) için bir **float** (mantisi 23 bit sahiptir) 256 en yakın katına sayıyı yuvarlar. **Uzun** değerleri için 4,294,966,913 4,294,967,167 tüm yuvarlanır **float** 4,294,967,040 değeri.

## <a name="see-also"></a>Ayrıca Bkz.

[Kayan Nokta Matematiği](../c-language/floating-point-math.md)