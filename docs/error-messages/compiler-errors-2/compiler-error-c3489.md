---
title: Derleyici Hatası C3489 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3489
dev_langs:
- C++
helpviewer_keywords:
- C3489
ms.assetid: 47b58d69-459d-4499-abc7-5f0b9303d773
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b1631c9be33204edfa697cb349148d274fe30e6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081227"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)