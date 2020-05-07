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

**ANSI 3.2.1.3** Bir integral sayı, özgün değeri tam olarak temsil eden bir kayan noktalı sayıya dönüştürüldüğünde kesilmenin yönü

Bir tamsayı, tam olarak değeri temsil edemeyen bir kayan nokta değerine atandığında, değer en yakın uygun değere yuvarlanır (aşağı veya yukarı).

Örneğin, **işaretsiz bir Long** (32 bitlik duyarlık ile) bir **float** (Mantis ' in 23 bittir), sayıyı 256 ' nin en yakın katına yuvarlar. 4.294.966.913 ile 4.294.967.167 arasındaki **uzun** değerler, **float** değeri olan 4.294.967.040 ' e yuvarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Matematiği](../c-language/floating-point-math.md)
