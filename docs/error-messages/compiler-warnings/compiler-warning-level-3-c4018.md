---
title: Derleyici Uyarısı (düzey 3) C4018
ms.date: 11/04/2016
f1_keywords:
- C4018
helpviewer_keywords:
- C4018
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
ms.openlocfilehash: f5708a9f52b6fc8206094454c352710199437f27
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161704"
---
# <a name="compiler-warning-level-3-c4018"></a>Derleyici Uyarısı (düzey 3) C4018

' expression ': imzalı/imzasız uyuşmazlığı

İmzalı ve işaretsiz bir sayının karşılaştırılması, derleyicinin imzalı değeri işaretsiz olarak dönüştürmesine izin vermek için gereklidir.

İmzalı ve imzasız türleri sınarken iki türden birini saçıyorsanız bu uyarı düzeltilebilir.

Aşağıdaki örnek C4018 oluşturur:

```cpp
// C4018.cpp
// compile with: /W3
int main() {
   unsigned int uc = 0;
   int c = 0;
   unsigned int c2 = 0;

   if (uc < c) uc = 0;   // C4018

   // OK
   if (uc == c2) uc = 0;
}
```
