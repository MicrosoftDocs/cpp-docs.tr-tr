---
title: Derleyici Hatası C2890 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2890
dev_langs:
- C++
helpviewer_keywords:
- C2890
ms.assetid: 49147375-182c-42b1-b170-f475cd436d47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbad8e1e46364579f4c7bc4bd6928e3a44d3cd66
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042669"
---
# <a name="compiler-error-c2890"></a>Derleyici Hatası C2890

'class': başvuru sınıfı yalnızca arabirim olmayan bir taban sınıfı olabilir

Başvuru sınıfı, yalnızca bir temel sınıf olabilir.

Aşağıdaki örnek, C2890 oluşturur:

```
// C2890.cpp
// compile with: /clr /c
ref class A {};
ref class B {};
ref class C : public A, public B {};   // C2890
ref class D : public A {};   // OK
```
