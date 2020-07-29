---
title: Kayan Nokta Değerlerine Tam Sayılar Atama
ms.date: 11/04/2016
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
ms.openlocfilehash: b3c65beee0cef4eb74d1bad3c03e5a9c11efae27
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227926"
---
# <a name="casting-integers-to-floating-point-values"></a>Kayan Nokta Değerlerine Tam Sayılar Atama

**ANSI 3.2.1.3** Bir integral sayı, özgün değeri tam olarak temsil eden bir kayan noktalı sayıya dönüştürüldüğünde kesilmenin yönü

Bir tamsayı, tam olarak değeri temsil edemeyen bir kayan nokta değerine atandığında, değer en yakın uygun değere yuvarlanır (aşağı veya yukarı).

Örneğin, bir **`unsigned long`** (32 bitlik duyarlık ile) **`float`** (Mantis 23 bit duyarlığa sahiptir), sayıyı 256 ' nin en yakın katına yuvarlar. **`long`** 4.294.966.913 ile 4.294.967.167 arasındaki değerler, **`float`** 4.294.967.040 değerine yuvarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta matematik](../c-language/floating-point-math.md)
