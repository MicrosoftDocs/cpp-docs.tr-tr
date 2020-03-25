---
title: Derleyici hatası C3813
ms.date: 11/04/2016
f1_keywords:
- C3813
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
ms.openlocfilehash: c16ce501e25040a7ac7672a9ea131b4fe89570f5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165619"
---
# <a name="compiler-error-c3813"></a>Derleyici hatası C3813

bir özellik bildirimi yalnızca yönetilen veya WinRT türünün tanımı içinde yer alabilir

Bir [özellik](../../dotnet/how-to-use-properties-in-cpp-cli.md) yalnızca yönetilen veya Windows çalışma zamanı türü içinde bildirilemez. Yerel türler `property` anahtar sözcüğünü desteklemez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3813 oluşturur ve nasıl düzeltileceğini gösterir:

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
