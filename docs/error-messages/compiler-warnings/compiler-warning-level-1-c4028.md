---
title: Derleyici Uyarısı (düzey 1) C4028
ms.date: 11/04/2016
f1_keywords:
- C4028
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
ms.openlocfilehash: ed46620605a8d5d60acee2db37c5cfc1348b5f4c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164475"
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
