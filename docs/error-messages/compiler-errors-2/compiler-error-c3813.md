---
title: Derleyici Hatası C3813
ms.date: 11/04/2016
f1_keywords:
- C3813
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
ms.openlocfilehash: 302b21d709424cda50abd0247f7b82048511cd73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384315"
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