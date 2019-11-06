---
title: Derleyici Uyarısı (düzey 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: ab3108c60c18276e8e4797c7cfde1b66535dbaaa
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627428"
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