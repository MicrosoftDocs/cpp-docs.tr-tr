---
title: Derleyici hatası C3492
ms.date: 11/04/2016
f1_keywords:
- C3492
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
ms.openlocfilehash: 37129c198096be91a8104aedcb508732d79e3630
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738316"
---
# <a name="compiler-error-c3492"></a>Derleyici hatası C3492

' var ': anonim birleşimin bir üyesini yakalayamazsınız

Adlandırılmamış bir birleşimin üyesini yakalayamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Birleşime bir ad verin ve tüm birleşim yapısını lambda ifadesinin yakalama listesine geçirin.

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

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

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
