---
title: Derleyici hatası C3498
ms.date: 11/04/2016
f1_keywords:
- C3498
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
ms.openlocfilehash: f1b978a585f3404cd3a881f25d6ef6a0f66b212d
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686161"
---
# <a name="compiler-error-c3498"></a>Derleyici hatası C3498

' var ': yönetilen veya WinRTtype içeren bir değişken yakalayamazsınız

Lambda içinde yönetilen bir türe veya Windows Çalışma Zamanı türüne sahip bir değişken yakalayamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Yönetilen veya Windows Çalışma Zamanı değişkenini lambda ifadesinin parametre listesine geçirin.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, bir lambda ifadesinin yakalama listesinde yönetilen bir türe sahip bir değişken göründüğünden, C3498 oluşturur:

```cpp
// C3498a.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [&s](String ^ r)
      { return String::Concat(s, r); } (", World!"); // C3498
}
```

Aşağıdaki örnek, yönetilen değişkeni `s` lambda ifadesinin parametre listesine geçirerek C3498 'i çözer:

```cpp
// C3498b.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [](String ^ s, String ^ r)
      { return String::Concat(s, r); } (s, ", World!");
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
