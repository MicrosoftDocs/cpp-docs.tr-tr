---
title: Derleyici Hatası C3489
ms.date: 11/04/2016
f1_keywords:
- C3489
helpviewer_keywords:
- C3489
ms.assetid: 47b58d69-459d-4499-abc7-5f0b9303d773
ms.openlocfilehash: d2ba8d919ab71b566950cc227588e071d24016bc
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026441"
---
# <a name="compiler-error-c3489"></a>Derleyici Hatası C3489

varsayılan yakalama modu değere göre olduğunda 'var' gereklidir

Varsayılan yakalama modu için bir lambda ifadesi değere göre olduğunu belirttiğinizde, bu ifadesinin yakalama yan tümcesi değere göre bir değişken geçiremezsiniz.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Yakalama yan tümcesi için açıkça değişken geçmeyin veya

- Değere göre varsayılan yakalama modu belirtmeyin veya

- Varsayılan yakalama modu başvuruya göre belirtin veya

- Yakalama yan tümcesi için başvuruya göre değişken geçirin. (Bu lambda ifadesi davranışını değiştirebilirsiniz.)

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3489 değişkeni oluşturur `n` değere, varsayılan mod budur değere göre bir lambda ifadesinin yakalama yan tümcesi içinde görünür:

```
// C3489a.cpp

int main()
{
   int n = 5;
   [=, n]() { return n; } (); // C3489
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnekte, dört olası çözümler için C3489 gösterilmektedir:

```
// C3489b.cpp

int main()
{
   int n = 5;

   // Possible resolution 1:
   // Do not explicitly pass n to the capture clause.
   [=]() { return n; } ();

   // Possible resolution 2:
   // Do not specify by-value as the default capture mode.
   [n]() { return n; } ();

   // Possible resolution 3:
   // Specify by-reference as the default capture mode.
   [&, n]() { return n; } ();

   // Possible resolution 4:
   // Pass n by reference to the capture clause.
   [&n]() { return n; } ();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)