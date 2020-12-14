---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3499'
title: Derleyici hatası C3499
ms.date: 11/04/2016
f1_keywords:
- C3499
helpviewer_keywords:
- C3499
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
ms.openlocfilehash: e4e572be1b5e39ccec6bf1ca64eaf62a3e44ef28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315484"
---
# <a name="compiler-error-c3499"></a>Derleyici hatası C3499

void dönüş türüne sahip olarak belirtilen bir lambda bir değer döndüremez

Derleyici, dönüş türü olarak belirten bir lambda ifadesi **`void`** bir değer döndürdüğünde veya bir lambda ifadesi birden fazla deyim içerdiğinde ve bir değer döndürdüğünde ve dönüş türünü belirtmezse bu hatayı üretir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Lambda ifadesinden bir değer döndürmeyin veya

- Lambda ifadesinin dönüş türünü sağlayın veya

- Lambda ifadesinin gövdesini oluşturan deyimleri tek bir ifadeye birleştirin.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, C3499 oluşturur çünkü bir lambda ifadesinin gövdesi birden çok deyim içeriyor ve bir değer döndürüyor, ancak lambda ifadesi dönüş türünü belirtmiyor:

```cpp
// C3499a.cpp

int main()
{
   [](int x) { int n = x * 2; return n; } (5); // C3499
}
```

Aşağıdaki örnekte, C3499 için iki olası çözüm gösterilmektedir. İlk çözüm, lambda ifadesinin dönüş türünü sağlar. İkinci çözüm, lambda ifadesinin gövdesini oluşturan deyimleri tek bir ifadeye birleştirir.

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
