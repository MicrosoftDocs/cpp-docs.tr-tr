---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2429'
title: Derleyici hatası C2429
ms.date: 11/16/2017
f1_keywords:
- C2429
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
ms.openlocfilehash: 3c16a2a430e8050103c3903cf1355de089252ed5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190139"
---
# <a name="compiler-error-c2429"></a>Derleyici hatası C2429

> '*Language Feature*', '*derleyici seçeneği*' derleyici bayrağını gerektirir

Dil özelliği, destek için belirli bir derleyici seçeneği gerektirir.

Hata **C2429: dil özelliği ' iç içe-ad alanı-tanımı ', bir bileşik ad alanı tanımlamayı denerseniz '/std: c++ 17 ' derleyici bayrağını gerektirir** , Visual Studio 2015 güncelleştirme 5 ' den başlayarak bir veya daha fazla kapsam iç içe geçmiş ad alanı içeren bir ad alanı.  (Visual Studio 2017 sürüm 15,3 ' de **/std: c + + en son** anahtarı gereklidir.) C++ 17 ' den önceki c++ ' da bileşik ad alanı tanımlarına izin verilmez. Derleyici, [/std: c++ 17](../../build/reference/std-specify-language-standard-version.md) derleyici seçeneği belirtildiğinde bileşik ad alanı tanımlarını destekler:

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual Studio 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
