---
title: Derleyici Uyarısı (düzey 1) C4551
ms.date: 11/04/2016
f1_keywords:
- C4551
helpviewer_keywords:
- C4551
ms.assetid: 458b59bd-e2d7-425f-9ba6-268ff200424f
ms.openlocfilehash: 2f2a47ea318bb0a27495d195c61f410d9cc711fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186159"
---
# <a name="compiler-warning-level-1-c4551"></a>Derleyici Uyarısı (düzey 1) C4551

işlev çağrısında bağımsız değişken listesi eksik

İşlev çağrısı, işlev bir parametre alsa bile işlev adından sonra Open ve Close parantezleri içermelidir.

Aşağıdaki örnek C4551 oluşturur:

```cpp
// C4551.cpp
// compile with: /W1
void function1() {
}

int main() {
   function1;   // C4551
   function1();   // OK
}
```
