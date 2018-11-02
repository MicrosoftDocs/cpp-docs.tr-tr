---
title: Derleyici Hatası C3452
ms.date: 11/04/2016
f1_keywords:
- C3452
helpviewer_keywords:
- C3452
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
ms.openlocfilehash: 165c031f23f3b317300900970b30414da42e7840
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622761"
---
# <a name="compiler-error-c3452"></a>Derleyici Hatası C3452

Liste bağımsız değişken üyesi sabit değil

Bir sabit, derleme zamanında değerlendirilebilen bir değer beklenen bir öznitelik için bağımsız değişken geçirildi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3452 oluşturur.

```
// C3452.cpp
// compile with: /c
int i;
[module( name="mod", type=dll, custom={i} ) ];   // C3452
// try the following line instead
// [module( name="mod", type=dll, custom={"a"} ) ];
```