---
title: Derleyici Hatası C3481
ms.date: 11/04/2016
f1_keywords:
- C3481
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
ms.openlocfilehash: eff7c7a4f39524aa1d894b7b4590aa809714aae6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041208"
---
# <a name="compiler-error-c3481"></a>Derleyici Hatası C3481

'var': lambda yakalama değişkeni bulunamadı

Derleyici bir lambda ifadesinin yakalama listesine geçirilen bir değişkenin tanımı bulunamadı.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Değişkeni, lambda ifadesinin yakalama listeden kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3481 oluşturur çünkü değişken `n` tanımlı değil:

```
// C3481.cpp

int main()
{
   [n] {}(); // C3481
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)