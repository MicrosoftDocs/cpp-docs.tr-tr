---
title: Derleyici Hatası C3496 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3496
dev_langs:
- C++
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ec4602e6a0061f5eb750ab29587209a6c97985d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062299"
---
# <a name="compiler-error-c3496"></a>Derleyici Hatası C3496

'this' her zaman değere göre yakalanan: '&' yoksayıldı

Yakalama gerçekleştiremez `this` başvuruya göre işaretçi.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Yakalama `this` işaretçi değeri.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3496 oluşturur çünkü bir başvuru `this` işaretçi bir lambda ifadesinin yakalama listede görünür:

```
// C3496.cpp
// compile with: /c

class C
{
   void f()
   {
      [&this] {}(); // C3496
   }
};
```

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)