---
title: Derleyici Hatası C2847 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2847
dev_langs:
- C++
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41e3b49c509240fd0d782aacaa9fae836b62702a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054447"
---
# <a name="compiler-error-c2847"></a>Derleyici Hatası C2847

Yönetilen için sizeof veya WinRT türü 'class' uygulanamaz

[Sizeof](../../cpp/sizeof-operator.md) işleci, derleme zamanında bir nesnenin değerini alır. Yönetilen boyutunu veya WinRT sınıf, arabirim veya değer türü dinamiktir ve bu nedenle derleme zamanında bilinen olamaz.

Örneğin, aşağıdaki örnek C2847 oluşturur:

```
// C2847.cpp
// compile with: /clr
ref class A {};

int main() {
   A ^ xA = gcnew A;
   sizeof(*xA);   // C2847 cannot use sizeof on managed object
}
```
