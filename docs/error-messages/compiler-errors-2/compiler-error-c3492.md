---
title: Derleyici Hatası C3492 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3492
dev_langs:
- C++
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54b3689a6ee565788e2a469a8321727a9fdd822f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089222"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)