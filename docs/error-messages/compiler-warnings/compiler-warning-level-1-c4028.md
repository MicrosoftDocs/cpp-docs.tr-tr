---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4028'
title: Derleyici Uyarısı (düzey 1) C4028
ms.date: 11/04/2016
f1_keywords:
- C4028
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
ms.openlocfilehash: ac6f4ba05d7acfa0772429372128d32c27fc909c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241423"
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
