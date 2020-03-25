---
title: Derleyici Uyarısı (düzey 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: 1a48fc806f3274a59c99be25ac7a0e7b03a0454b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176227"
---
# <a name="compiler-warning-level-1-c4129"></a>Derleyici Uyarısı (düzey 1) C4129

' character ': Tanınmayan karakter kaçış sırası

Bir karakter veya dize sabitinde ters eğik çizgi (\\) izleyen `character` geçerli bir kaçış sırası olarak tanınmıyor. Ters eğik çizgi yok sayılır ve yazdırılmaz. Ters eğik çizgiden sonraki karakter yazdırılır.

Tek bir ters eğik çizgi yazdırmak için çift ters eğik çizgi (\\\\) belirtin.

C++ Standart, Bölüm 2.13.2 ' de çıkış dizilerini tartışır.

Aşağıdaki örnek C4129 oluşturur:

```cpp
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```
