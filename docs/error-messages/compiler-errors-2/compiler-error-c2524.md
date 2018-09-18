---
title: Derleyici Hatası C2524 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2524
dev_langs:
- C++
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e091abdf9f61512d99625c0111f73d0d5fc5315
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060687"
---
# <a name="compiler-error-c2524"></a>Derleyici Hatası C2524

'yok edici': bir yok edici/Sonlandırıcı bir 'void' parametre listesine sahip olmalıdır

Yıkıcı veya Sonlandırıcı olmayan bir parametre listesine sahip [void](../../cpp/void-cpp.md). Diğer parametre türleri izin verilmez.

## <a name="example"></a>Örnek

Aşağıdaki kod C2524 yeniden oluşturur.

```
// C2524.cpp
// compile with: /c
class A {
   A() {}
   ~A(int i) {}    // C2524
   // try the following line instead
   // ~A() {}
};
```

## <a name="example"></a>Örnek

Aşağıdaki kod C2524 yeniden oluşturur.

```
// C2524_b.cpp
// compile with: /clr /c
ref struct I1 {
protected:
   !I1(int i);   // C2524
   // try the following line instead
   // !I1();
};
```