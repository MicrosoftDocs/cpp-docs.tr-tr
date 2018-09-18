---
title: Derleyici Uyarısı (Düzey 3) C4240 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4240
dev_langs:
- C++
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2f3c059e63bcca9bbde9e863cc17c9e240e4f78
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057021"
---
# <a name="compiler-warning-level-3-c4240"></a>Derleyici Uyarısı (Düzey 3) C4240

Standart olmayan uzantı kullanıldı: erişimi şimdi 'erişim belirticisi', daha önce tanımlanmış'classname ', 'erişim belirticisi' olacak şekilde tanımlandı

ANSI Uyumluluğu altında ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), iç içe geçmiş bir sınıf için erişim değiştiremezsiniz. Varsayılan Microsoft uzantıları altında (/Ze), bu uyarı ile kullanabilirsiniz.

## <a name="example"></a>Örnek

```
// C4240.cpp
// compile with: /W3
class X
{
private:
   class N;
public:
   class N
   {   // C4240
   };
};

int main()
{
}
```