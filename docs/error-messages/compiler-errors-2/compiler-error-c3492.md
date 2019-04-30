---
title: Derleyici Hatası C3492
ms.date: 11/04/2016
f1_keywords:
- C3492
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
ms.openlocfilehash: facd8c78e775945924d77b09f9dc754bdc301ddd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381130"
---
# <a name="compiler-error-c3492"></a>Derleyici Hatası C3492

'var': anonim bir birleşim üyesi yakalayamazsınız

Adlandırılmamış bir birleşim üyesi yakalayamaz.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Birleşimin bir ad verin ve tam bileşim yapısı lambda ifadesinin yakalama listesine geçirin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, anonim birleşim üyesi yakaladığından C3492 oluşturur:

```
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

Aşağıdaki örnek, birleşim bir ad vererek ve tam bileşim yapısı lambda ifadesinin yakalama listesine geçirerek C3492 çözer:

```
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