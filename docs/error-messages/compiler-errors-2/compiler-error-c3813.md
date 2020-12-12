---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3813'
title: Derleyici hatası C3813
ms.date: 11/04/2016
f1_keywords:
- C3813
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
ms.openlocfilehash: ae7157166083a4a86d9a5b170cbff3e127c87abb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181006"
---
# <a name="compiler-error-c3813"></a>Derleyici hatası C3813

bir özellik bildirimi yalnızca yönetilen veya WinRT türünün tanımı içinde yer alabilir

Bir [özellik](../../dotnet/how-to-use-properties-in-cpp-cli.md) yalnızca yönetilen veya Windows çalışma zamanı türü içinde bildirilemez. Yerel türler **`property`** anahtar sözcüğünü desteklemez.

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
