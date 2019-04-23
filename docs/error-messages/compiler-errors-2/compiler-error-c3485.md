---
title: Derleyici Hatası C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 2fcaecd6be35e2ae6822133930b48b6bbf02aafe
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027590"
---
# <a name="compiler-error-c3485"></a>Derleyici Hatası C3485

bir lambda tanımında cv niteleyicileri bulunamaz

Kullanamazsınız bir `const` veya `volatile` bir lambda ifadesinin tanımının bir parçası olarak niteleyicisi.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Kaldırma `const` veya `volatile` , lambda ifadesinin tanımından niteleyicisi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3485 oluşturur, bunu kullandığından `const` niteleyicisi bir lambda ifadesinin tanımının bir parçası olarak:

```
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)