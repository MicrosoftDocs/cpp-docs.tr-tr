---
title: Derleyici Uyarısı (düzey 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: dc4f4c4c1feeba543ce0baa71e1ee5dfd81fdcae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428683"
---
# <a name="compiler-warning-level-1-c4129"></a>Derleyici Uyarısı (düzey 1) C4129

'character': Tanınmayan karakter kaçış sırası

`character` Bir ters eğik çizgiden (\\) bir karakter veya dize sabiti geçerli kaçış dizisi olarak tanınmıyor. Ters eğik çizgi yok sayıldı ve yazdırılmaz. Ters eğik çizgiyi takip eden karakterden yazdırılır.

Tek bir ters eğik çizgi yazdırmak için bir çift ters eğik çizgi belirtin (\\\\).

Bölümünde 2.13.2 C++ standardı, kaçış dizileri açıklar.

Aşağıdaki örnek, C4129 oluşturur:

```
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```