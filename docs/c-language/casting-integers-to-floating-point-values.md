---
description: 'Hakkında daha fazla bilgi edinin: Floating-Point değerlere tamsayılar atama'
title: Kayan Nokta Değerlerine Tam Sayılar Atama
ms.date: 11/04/2016
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
ms.openlocfilehash: 2a1a3ce5bf7aac98148c70eb62cdb3c377ca54f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214024"
---
# <a name="casting-integers-to-floating-point-values"></a>Kayan Nokta Değerlerine Tam Sayılar Atama

**ANSI 3.2.1.3** Bir integral sayı, özgün değeri tam olarak temsil eden bir kayan noktalı sayıya dönüştürüldüğünde kesilmenin yönü

Bir tamsayı, tam olarak değeri temsil edemeyen bir kayan nokta değerine atandığında, değer en yakın uygun değere yuvarlanır (aşağı veya yukarı).

Örneğin, bir **`unsigned long`** (32 bitlik duyarlık ile) **`float`** (Mantis 23 bit duyarlığa sahiptir), sayıyı 256 ' nin en yakın katına yuvarlar. **`long`** 4.294.966.913 ile 4.294.967.167 arasındaki değerler, **`float`** 4.294.967.040 değerine yuvarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta matematik](../c-language/floating-point-math.md)
