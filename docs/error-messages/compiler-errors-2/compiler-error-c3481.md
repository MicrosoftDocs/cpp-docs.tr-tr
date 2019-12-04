---
title: Derleyici hatası C3481
ms.date: 11/04/2016
f1_keywords:
- C3481
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
ms.openlocfilehash: 1719e9f1d3328be083f745498e6f4ad772b0b52a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755245"
---
# <a name="compiler-error-c3481"></a>Derleyici hatası C3481

' var ': Lambda yakalama değişkeni bulunamadı

Derleyici, bir lambda ifadesinin yakalama listesine geçirilmiş bir değişkenin tanımını bulamadı.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Değişkeni lambda ifadesinin yakalama listesinden kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `n` değişken tanımlanmadığı için C3481 oluşturur:

```cpp
// C3481.cpp

int main()
{
   [n] {}(); // C3481
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
