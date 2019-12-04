---
title: Derleyici hatası C3488
ms.date: 11/04/2016
f1_keywords:
- C3488
helpviewer_keywords:
- C3488
ms.assetid: 0a6fcd76-dd3b-48d7-abb3-22eccda96034
ms.openlocfilehash: 2b69ed4ac8b7e706096d107e9dfaa4447ca1bc79
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738433"
---
# <a name="compiler-error-c3488"></a>Derleyici hatası C3488

varsayılan yakalama modu başvuruya göre olduğunda ' var ' öğesine izin verilmez

Bir lambda ifadesinin varsayılan yakalama modunun başvuruya göre olduğunu belirttiğinizde, bu ifadenin yakalama yan tümcesine başvuruya göre bir değişken geçirilemez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Değişkeni, yakalama yan tümcesine açıkça geçirmeyin veya

- Varsayılan yakalama modu olarak başvuruya göre belirtmeyin veya

- Varsayılan yakalama modu olarak değere göre belirtin veya

- Değişkeni değere göre yakalama yan tümcesine geçirin. (Bu durum lambda ifadesinin davranışını değiştirebilir.)

## <a name="example"></a>Örnek

Aşağıdaki örnek, varsayılan modu başvuruya göre olan bir lambda ifadesinin Capture yan tümcesinde `n` değişkenine bir başvuru göründüğünden C3488 oluşturur:

```cpp
// C3488a.cpp

int main()
{
   int n = 5;
   [&, &n]() { return n; } (); // C3488
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnekte, C3488 için dört olası çözüm gösterilmektedir:

```cpp
// C3488b.cpp

int main()
{
   int n = 5;

   // Possible resolution 1:
   // Do not explicitly pass &n to the capture clause.
   [&]() { return n; } ();

   // Possible resolution 2:
   // Do not specify by-reference as the default capture mode.
   [&n]() { return n; } ();

   // Possible resolution 3:
   // Specify by-value as the default capture mode.
   [=, &n]() { return n; } ();

   // Possible resolution 4:
   // Pass n by value to the capture clause.
   [n]() { return n; } ();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
