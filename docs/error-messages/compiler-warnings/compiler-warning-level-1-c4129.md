---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4129'
title: Derleyici Uyarısı (düzey 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: 27ae487016a5d9a60a95e4715261ec5ba9171db4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155286"
---
# <a name="compiler-warning-level-1-c4129"></a>Derleyici Uyarısı (düzey 1) C4129

' character ': Tanınmayan karakter kaçış sırası

`character` \\ Bir karakter veya dize sabiti içindeki bir ters eğik çizgi () geçerli bir kaçış sırası olarak tanınmıyor. Ters eğik çizgi yok sayılır ve yazdırılmaz. Ters eğik çizgiden sonraki karakter yazdırılır.

Tek bir ters eğik çizgi yazdırmak için çift ters eğik çizgi ( \\ \\ ) belirtin.

C++ standardı, Bölüm 2.13.2 ' de çıkış dizilerini açıklar.

Aşağıdaki örnek C4129 oluşturur:

```cpp
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```
