---
title: Derleyici hatası C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 2117832ffd5a90612e9745a3706f01e3b5d1b18d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87197676"
---
# <a name="compiler-error-c3485"></a>Derleyici hatası C3485

bir lambda tanımında CV niteleyicileri bulunamaz

Bir **`const`** veya **`volatile`** niteleyicisi bir lambda ifadesinin tanımının bir parçası olarak kullanılamaz.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- **`const`** **`volatile`** Lambda ifadeniz tanımından veya niteleyicisini kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, **`const`** bir lambda ifadesinin tanımının bir parçası olarak niteleyiciyi kullandığından, C3485 oluşturur:

```cpp
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
