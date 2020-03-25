---
title: Derleyici Uyarısı (düzey 2) C4156
ms.date: 11/04/2016
f1_keywords:
- C4156
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
ms.openlocfilehash: b9add4af0fddf8d68bbba0293530f2bb0ce3800d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162094"
---
# <a name="compiler-warning-level-2-c4156"></a>Derleyici Uyarısı (düzey 2) C4156

' DELETE ' deyiminin dizi biçimi kullanılmadan bir dizi ifadesinin silinmesi; dizi formu değiştirildi

**Delete** 'in dizi olmayan biçimi bir diziyi silemez. Derleyici, **Delete** öğesini dizi formuna çevirdi.

Bu uyarı yalnızca Microsoft uzantıları (/Ze) altında oluşur.

## <a name="example"></a>Örnek

```cpp
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```
