---
title: Derleyici Uyarısı (düzey 1) C4028
ms.date: 11/04/2016
f1_keywords:
- C4028
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
ms.openlocfilehash: bfe54fc40b4d6927a1d75f529ec9b619f9b29226
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397373"
---
# <a name="compiler-warning-level-1-c4028"></a>Derleyici Uyarısı (düzey 1) C4028

biçimsel parametre 'number' bildirimden farklı

Biçimsel parametre türü bildirimi karşılık gelen parametre ile kabul değil. Özgün bildiriminde türü kullanılır.

Bu uyarı yalnızca C kaynak kodu için geçerlidir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4028 oluşturur.

```
// C4028.c
// compile with: /W1 /Za
void f(int , ...);
void f(int i, int j) {}   // C4028

void g(int , int);
void g(int i, int j) {}   // OK

int main() {}
```