---
title: Derleyici Hatası C3498 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3498
dev_langs:
- C++
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bb87abc113e586aa4f3097444df4c5a46a6a92c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106785"
---
# <a name="compiler-error-c3498"></a>Derleyici Hatası C3498

'var': bir yönetilen sahip bir değişken veya WinRTtype yakalayamazsınız

Bir lambda içinde yönetilen bir türe veya bir Windows çalışma zamanı türü içeren bir değişkeni yakalayamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Yönetilen geçirin veya lambda ifadesi parametre listesine Windows çalışma zamanı değişken.

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilen bir türe sahip bir değişken bir lambda ifadesinin yakalama listede göründüğünden C3498 oluşturur:

```
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

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilen değişkeni geçirerek C3498 çözümler `s` lambda ifadesi parametre listesine:

```
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

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)