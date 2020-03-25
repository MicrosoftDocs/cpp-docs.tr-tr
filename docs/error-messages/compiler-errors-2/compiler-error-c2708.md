---
title: Derleyici hatası C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: a1d3379a0da42c5aabd38cffbf6f6a3f340ef3b9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202377"
---
# <a name="compiler-error-c2708"></a>Derleyici hatası C2708

' tanımlayıcı ': gerçek parametrenin bayt uzunluğu önceki çağrıdan veya başvurudan farklı

[__Stdcall](../../cpp/stdcall.md) işlevin önünde bir prototip gelmelidir. Aksi takdirde, derleyici işleve ilk çağrıyı bir prototip olarak yorumlar ve bu hata derleyici eşleşmeyen bir çağrıyla karşılaştığında oluşur.

Bu hatayı onarmak için bir işlev prototipi ekleyin.
