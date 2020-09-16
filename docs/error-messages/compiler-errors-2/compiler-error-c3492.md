---
title: Derleyici hatası C3492
ms.date: 11/04/2016
f1_keywords:
- C3492
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
ms.openlocfilehash: bdaeb8797eb71b205f737d08e74430f161cb8caa
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686554"
---
# <a name="compiler-error-c3492"></a>Derleyici hatası C3492

' var ': anonim birleşimin bir üyesini yakalayamazsınız

Adlandırılmamış bir birleşimin üyesini yakalayamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Birleşime bir ad verin ve tüm birleşim yapısını lambda ifadesinin yakalama listesine geçirin.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, anonim bir birleşimin bir üyesini yakaladığı için C3492 oluşturur:

```cpp
// C3492a.cpp

int main()
{
   union
   {
      char ch;
      int x;
   };

   ch = 'y';
   [&x](char ch) { x = ch; }(ch); // C3492
}
```

Aşağıdaki örnek, birleşime bir ad vererek ve tüm birleşim yapısını lambda ifadesinin yakalama listesine geçirerek C3492 'i çözer:

```cpp
// C3492b.cpp

int main()
{
   union
   {
      char ch;
      int x;
   } u;

   u.ch = 'y';
   [&u](char ch) { u.x = ch; }(u.ch);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
