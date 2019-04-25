---
title: Kayan Nokta Değerlerine Tam Sayılar Atama
ms.date: 11/04/2016
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
ms.openlocfilehash: 8fa013668278fae82bcb2bb9eb1f2aec3cb61581
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312654"
---
# <a name="casting-integers-to-floating-point-values"></a>Kayan Nokta Değerlerine Tam Sayılar Atama

**ANSI 3.2.1.3** bir tamsayı, tam olarak orijinal değeri temsil edemeyen bir kayan noktalı sayı dönüştürüldüğünde kesilme yönü

Bir tamsayı, tam olarak değeri temsil edemeyen bir kayan nokta değerine atandığında, değer en yakın uygun değere yuvarlanır (aşağı veya yukarı).

Örneğin, bir **işaretsiz uzun** (ile 32 bit kesinliği) için bir **float** (mantisi 23 bit sahiptir) 256 en yakın katına sayıyı yuvarlar. **Uzun** değerleri için 4,294,966,913 4,294,967,167 tüm yuvarlanır **float** 4,294,967,040 değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Matematiği](../c-language/floating-point-math.md)
