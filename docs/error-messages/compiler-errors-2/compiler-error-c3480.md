---
title: Derleyici Hatası C3480 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3480
dev_langs:
- C++
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fd58a8c38ee6dc5f77ef280ba3b7a546a666cd6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107870"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)