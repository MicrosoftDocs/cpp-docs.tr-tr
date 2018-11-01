---
title: Derleyici Uyarısı (Düzey 3) C4240
ms.date: 11/04/2016
f1_keywords:
- C4240
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
ms.openlocfilehash: fe5306cc7909138fea0159553b53c2adc6a46dc0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498247"
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