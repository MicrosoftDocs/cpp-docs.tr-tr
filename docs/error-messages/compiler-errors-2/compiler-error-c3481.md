---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3481'
title: Derleyici hatası C3481
ms.date: 11/04/2016
f1_keywords:
- C3481
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
ms.openlocfilehash: 31f13b56a2b5df66a5765ee63313ffe265c15fe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113408"
---
# <a name="compiler-error-c3481"></a>Derleyici hatası C3481

' var ': Lambda yakalama değişkeni bulunamadı

Derleyici, bir lambda ifadesinin yakalama listesine geçirilmiş bir değişkenin tanımını bulamadı.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Değişkeni lambda ifadesinin yakalama listesinden kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3481 oluşturuyor çünkü değişken `n` tanımlı değil:

```cpp
// C3481.cpp

int main()
{
   [n] {}(); // C3481
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
