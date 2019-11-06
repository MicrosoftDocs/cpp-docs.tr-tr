---
title: Derleyici Uyarısı (düzey 1) C4028
ms.date: 11/04/2016
f1_keywords:
- C4028
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
ms.openlocfilehash: 19bfd2659ee9017d3a304dee2d647da091515876
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623845"
---
# <a name="compiler-warning-level-1-c4028"></a>Derleyici Uyarısı (düzey 1) C4028

' number ' biçimsel parametresi bildirimden farklı

Biçimsel parametrenin türü, bildirimde karşılık gelen parametreyle kabul etmez. Özgün bildirimdeki tür kullanılır.

Bu uyarı yalnızca C kaynak kodu için geçerlidir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4028 oluşturur.

```c
// C4028.c
// compile with: /W1 /Za
void f(int , ...);
void f(int i, int j) {}   // C4028

void g(int , int);
void g(int i, int j) {}   // OK

int main() {}
```