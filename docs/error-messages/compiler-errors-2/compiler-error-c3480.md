---
title: Derleyici Hatası C3480
ms.date: 11/04/2016
f1_keywords:
- C3480
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
ms.openlocfilehash: 2ebcce496fd06c30420558d80cc0a0c9318d4376
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173430"
---
# <a name="compiler-error-c3480"></a>Derleyici Hatası C3480

'var': bir lambda yakalama değişkeni bir kapsayan işlev kapsamından gelmelidir

Lambda yakalama değişkeni bir kapsayan işlev kapsamından değil.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Değişkeni, lambda ifadesinin yakalama listeden kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3480 oluşturur çünkü değişken `global` bir kapsayan işlev kapsamından değil:

```
// C3480a.cpp

int global = 0;
int main()
{
   [&global] { global = 5; }(); // C3480
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnekte, değişken kaldırarak C3480 çözümler `global` lambda ifadesinin yakalama listesinden:

```
// C3480b.cpp

int global = 0;
int main()
{
   [] { global = 5; }();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)