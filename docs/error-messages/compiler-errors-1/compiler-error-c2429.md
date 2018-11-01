---
title: Derleyici Hatası C2429
ms.date: 11/16/2017
f1_keywords:
- C2429
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
ms.openlocfilehash: 972ec6591132443ef4d1297598d6de7216f59663
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586699"
---
# <a name="compiler-error-c2429"></a>Derleyici Hatası C2429

> '*dil özelliği*'derleyici bayrağını gerektiriyor'*derleyici seçeneği*'

Dil özelliği belirli bir derleyici seçeneği desteği gerektirir.

Hata **C2429: dil özelliği 'iç içe-namespace-definition' derleyici bayrağını gerektiriyor ' / Std: c ++ 17'** tanımlamak çalışırsanız oluşturulan bir *bileşik ad alanı*, bir veya daha fazla bilgi içeren bir ad alanı Visual Studio 2015 güncelleştirme 5'te başlayan kapsam iç içe geçmiş ad alanı adları. (Visual Studio 2017 sürüm 15.3, **/Std: c ++ Son** anahtarı gereklidir.) Bileşik. ad alanı tanımları c++'ta C ++ 17 önce izin verilmez. Bileşik ad tanımları derleyici destekler, [/Std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) derleyici seçeneği belirtilmemişse:

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
