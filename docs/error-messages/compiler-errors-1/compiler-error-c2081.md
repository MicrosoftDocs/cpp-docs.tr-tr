---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2081'
title: Derleyici hatası C2081
ms.date: 11/04/2016
f1_keywords:
- C2081
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
ms.openlocfilehash: e6f75d6d478d9523d36a9671457cf2a5618e4f21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151183"
---
# <a name="compiler-error-c2081"></a>Derleyici hatası C2081

' tanımlayıcı ': biçimsel parametre listesindeki ad geçersiz

Tanımlayıcı bir sözdizimi hatasına neden oldu.

Bu hata, biçimsel parametre listesi için eski stil kullanılarak kaynaklanıyor olabilir. Biçimsel parametre listesinde biçimsel parametrelerin türünü belirtmeniz gerekir.

Aşağıdaki örnek C2081 oluşturur:

```c
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

Olası çözüm:

```c
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```
