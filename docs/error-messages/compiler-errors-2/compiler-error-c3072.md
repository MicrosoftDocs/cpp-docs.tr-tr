---
title: Derleyici Hatası C3072 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3072
dev_langs:
- C++
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a36eaaf12cf9f8909455847036f670f6fc0cd40b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047518"
---
# <a name="compiler-error-c3072"></a>Derleyici Hatası C3072

' operator 'işleci bir başvuru sınıfının bir örneğine uygulanamaz

birli Kullan '`operator` ' işleci bir başvuru sınıfının bir örneğini tanıtıcı türüne dönüştürmek için

Bir CLR türü, CLR işleçleri, yerel (veya standart) işleçleri gerektirir.  Daha fazla bilgi için [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3072 oluşturur.

```
// C3072.cpp
// compile with: /clr
ref class R {};

int main() {
   R r1;
   R^ r2 = &r1;   // C3072
   R^ r3 = %r1;   // OK
}
```