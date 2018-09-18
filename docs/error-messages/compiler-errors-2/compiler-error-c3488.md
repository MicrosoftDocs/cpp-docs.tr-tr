---
title: Derleyici Hatası C3488 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3488
dev_langs:
- C++
helpviewer_keywords:
- C3488
ms.assetid: 0a6fcd76-dd3b-48d7-abb3-22eccda96034
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15e1a21781eed96ee3a2a1430da8e43013393912
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061806"
---
# <a name="compiler-error-c3488"></a>Derleyici Hatası C3488

varsayılan yakalama modu başvuruya göre olduğunda 'var' izin verilmiyor

Bir lambda ifadesi için varsayılan yakalama modu başvuruya göre olduğunu belirttiğinizde, ifadesinin yakalama yan tümcesi, başvuru tarafından bir değişken geçiremezsiniz.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Yakalama yan tümcesi için açıkça değişken geçmeyin veya

- Başvuruya göre varsayılan yakalama modu belirtmeyin veya

- Varsayılan yakalama modu değere göre belirtin veya

- Değişkeni değere göre yakalama yan tümcesine geçirin. (Bu lambda ifadesi davranışını değiştirebilirsiniz.)

## <a name="example"></a>Örnek

Aşağıdaki örnek C3488 oluşturur çünkü değişken başvuru `n` olan varsayılan mod budur başvuruya göre lambda ifadesinin yakalama yan tümcesinde görünür:

```
// C3488a.cpp

int main()
{
   int n = 5;
   [&, &n]() { return n; } (); // C3488
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnekte, dört olası çözümler için C3488 gösterilmektedir:

```
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

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)