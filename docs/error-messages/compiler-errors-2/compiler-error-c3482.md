---
title: Derleyici Hatası C3482 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3482
dev_langs:
- C++
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9921c25575888ab2db1c092f9325002d1becb921
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053381"
---
# <a name="compiler-error-c3482"></a>Derleyici Hatası C3482

'this' yalnızca statik olmayan üye işlevin içinde lambda yakalaması olarak kullanılır

Geçiremezsiniz `this` statik bir yöntem veya genel bir işlev içinde bildirilen bir lambda ifadesinin yakalama listesi.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Kapsayan işlevin bir statik olmayan yönteme dönüştürmek veya

- Kaldırma `this` lambda ifadesinin yakalama listeden işaretçi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3482 oluşturur:

```
// C3482.cpp
// compile with: /c

class C
{
public:
   static void staticMethod()
   {
      [this] {}(); // C3482
   }
};
```

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)