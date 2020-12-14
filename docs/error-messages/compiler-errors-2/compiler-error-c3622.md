---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3622'
title: Derleyici hatası C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: 19c599fced524001f360a4ad462a9dbebbfb2fa3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223041"
---
# <a name="compiler-error-c3622"></a>Derleyici hatası C3622

' class ': ' anahtar sözcük ' olarak belirtilen bir sınıf başlatılamaz

[Soyut](../../extensions/abstract-cpp-component-extensions.md)olarak işaretlenmiş bir sınıfın örneğini oluşturma girişiminde bulunuldu. Olarak işaretlenmiş bir sınıf **`abstract`** , temel bir sınıf olabilir, ancak örneklenemez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3622 oluşturur.

```cpp
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
