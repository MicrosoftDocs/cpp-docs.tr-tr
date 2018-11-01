---
title: Derleyici Hatası C3499
ms.date: 11/04/2016
f1_keywords:
- C3499
helpviewer_keywords:
- C3499
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
ms.openlocfilehash: 937b4e993919f5b6e28e3c389476854be36fa1cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668292"
---
# <a name="compiler-error-c3499"></a>Derleyici Hatası C3499

dönüş türü void olacak şekilde belirtilen lambdanın bir dönüş değeri olamaz

Derleyicinin belirten bir lambda ifadesi, bu hatayı oluşturmasının `void` dönüş türü bir değer döndürmektedir veya geçersiz bir lambda ifadesi birden fazla deyim içerir ve bir değer döndürür, ancak dönüş türü belirtmiyor.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Lambda ifadesinden bir değer döndürmeyen veya

- Lambda ifadesinin dönüş türü sağlayan veya

- Tek bir deyimde içine lambda ifadesinin gövdesi oluşturan deyimleri birleştirin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir lambda ifadesinin gövdesinin birden çok deyim içermiyor ve bir değer döndürür, ancak lambda ifadesinin dönüş türü belirtmeyen C3499 oluşturur:

```
// C3499a.cpp

int main()
{
   [](int x) { int n = x * 2; return n; } (5); // C3499
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, iki olası çözüm için C3499 gösterir. İlk çözümleme, lambda ifadesinin dönüş türü sağlar. İkinci çözüm, tek bir deyimde içine lambda ifadesinin gövdesi oluşturan deyimleri birleştirir.

```
// C3499b.cpp

int main()
{
   // Possible resolution 1:
   // Provide the return type of the lambda expression.
   [](int x) -> int { int n = x * 2; return n; } (5);

   // Possible resolution 2:
   // Combine the statements that make up the body of
   // the lambda expression into a single statement.
   [](int x) { return x * 2; } (5);
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)