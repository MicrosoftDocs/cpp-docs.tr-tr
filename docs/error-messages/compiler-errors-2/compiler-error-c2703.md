---
title: Derleyici hatası C2703
description: Microsoft C/C++ derleyicisi hata C2703 açıklar.
ms.date: 08/24/2020
f1_keywords:
- C2703
helpviewer_keywords:
- C2703
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
ms.openlocfilehash: 4d5b5ccad1cd15c1a107c81423e2372e14165776
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898606"
---
# <a name="compiler-error-c2703"></a>Derleyici hatası C2703

> Geçersiz `__leave` ifade

## <a name="remarks"></a>Açıklamalar

Bir **`__leave`** deyimin bir blok içinde olması gerekir **`__try`** .

## <a name="example"></a>Örnek

Aşağıdaki örnek C2703 oluşturur:

```cpp
// C2703.cpp
int main() {
   __leave;   // C2703
   __try {
      // try the following line instead
      __leave;
   }
   __finally {}
}
```

## <a name="see-also"></a>Ayrıca bkz.

[`__leave`Anahtar sözcüğü](../../cpp/try-except-statement.md#__leave)\
[`try-except` Ekstre](../../cpp/try-except-statement.md)\
[`try-finally` Ekstre](../../cpp/try-finally-statement.md)
