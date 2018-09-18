---
title: Derleyici Hatası C3813 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3813
dev_langs:
- C++
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8984feb5b657c26d2137eb9a3c648f1bcf442bf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066277"
---
# <a name="compiler-error-c3813"></a>Derleyici Hatası C3813

bir özellik bildirimi yalnızca bir yönetilen tanımını veya WinRT türü içinde yer alabilir

A [özelliği](../../dotnet/how-to-use-properties-in-cpp-cli.md) yalnızca yönetilen veya Windows çalışma zamanı içinde bildirilebilir türü. Yerel türler desteklemez `property` anahtar sözcüğü.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3813 oluşturur ve bu sorunun nasıl gösterir:

```cpp
// C3813.cpp
// compile by using: cl /c /clr C3813.cpp
class A
{
   property int Int; // C3813
};

ref class B
{
   property int Int; // OK - declared within managed type
};
```