---
title: Derleyici Hatası C3490 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3490
dev_langs:
- C++
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 503302d323f45b5f7c3971803fef0547ff28e0c8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077704"
---
# <a name="compiler-error-c3490"></a>Derleyici Hatası C3490

'var' değiştirilemez çünkü bir const nesnesi üzerinden erişiliyor

Bölümünde bildirilen bir lambda ifadesi bir `const` yöntemi değişemeyen üye verilerini değiştiremez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Kaldırma `const` , yöntem bildiriminde'den değiştiricisi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3490 oluşturur, üye değişkeni değiştirir çünkü `_i` içinde bir `const` yöntemi:

```
// C3490a.cpp
// compile with: /c

class C
{
   void f() const
   {
      auto x = [=]() { _i = 20; }; // C3490
   }

   int _i;
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, kaldırarak C3490 çözümler `const` değiştirici yöntem bildiriminde'nden:

```
// C3490b.cpp
// compile with: /c

class C
{
   void f()
   {
      auto x = [=]() { _i = 20; };
   }

   int _i;
};
```

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)