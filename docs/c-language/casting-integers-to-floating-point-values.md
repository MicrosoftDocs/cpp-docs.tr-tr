---
title: Kayan Nokta Değerlerine Tam Sayılar Atama
ms.date: 11/04/2016
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
ms.openlocfilehash: 8fa013668278fae82bcb2bb9eb1f2aec3cb61581
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152878"
---
# <a name="casting-integers-to-floating-point-values"></a>Kayan Nokta Değerlerine Tam Sayılar Atama

**ANSI 3.2.1.3** bir tamsayı, tam olarak orijinal değeri temsil edemeyen bir kayan noktalı sayı dönüştürüldüğünde kesilme yönü

Bir tamsayı, tam olarak değeri temsil edemeyen bir kayan nokta değerine atandığında, değer en yakın uygun değere yuvarlanır (aşağı veya yukarı).

Örneğin, bir **işaretsiz uzun** (ile 32 bit kesinliği) için bir **float** (mantisi 23 bit sahiptir) 256 en yakın katına sayıyı yuvarlar. **Uzun** değerleri için 4,294,966,913 4,294,967,167 tüm yuvarlanır **float** 4,294,967,040 değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Matematiği](../c-language/floating-point-math.md)
