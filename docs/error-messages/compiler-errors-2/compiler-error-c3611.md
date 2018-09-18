---
title: Derleyici Hatası C3611 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3611
dev_langs:
- C++
helpviewer_keywords:
- C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bc7f1f96e774c7b0dd9df2f760d9c45a522de1c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039653"
---
# <a name="compiler-error-c3611"></a>Derleyici Hatası C3611

'function': korumalı bir işlevin saf belirticisi olamaz

Korumalı bir işlevin yanlış bildirildi.  Daha fazla bilgi için [korumalı](../../windows/sealed-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3611 oluşturur.

```
// C3611.cpp
// compile with: /clr /c

ref struct V {
   virtual void Test() sealed = 0;   // C3611
   virtual void Test2() sealed;   // OK
   virtual void Test3() = 0;   // OK
};
```