---
title: Derleyici Hatası C2725
ms.date: 11/04/2016
f1_keywords:
- C2725
helpviewer_keywords:
- C2725
ms.assetid: 13cd5b1b-e906-4cd8-9b2b-510d587c665a
ms.openlocfilehash: da5fe354724427ae6806424122281d1653ebca22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558987"
---
# <a name="compiler-error-c2725"></a>Derleyici Hatası C2725

'özel durum': throw veya catch yönetilen ya da değer veya başvuruyla WinRT nesnesi

Yönetilen tür veya WinRT özel durumu doğru değildi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2725 oluşturur ve bu sorunun nasıl gösterir.

```
// C2725.cpp
// compile with: /clr
ref class R {
public:
   int i;
};

int main() {
   R % r1 = *gcnew R;
   throw r1;   // C2725

   R ^ r2 = gcnew R;
   throw r2;   // OK
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2725 oluşturur ve bu sorunun nasıl gösterir.

```
// C2725b.cpp
// compile with: /clr
using namespace System;
int main() {
   try {}
   catch( System::Exception%) {}   // C2725
   // try the following line instead
   // catch( System::Exception ^e) {}
}
```
