---
title: Derleyici Uyarısı (düzey 1) C4620
ms.date: 11/04/2016
f1_keywords:
- C4620
helpviewer_keywords:
- C4620
ms.assetid: fed29934-b797-47e8-bbea-c7e5f8dd6e93
ms.openlocfilehash: d03c7d845923b918fbb665933147d8ff97cda7ab
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051462"
---
# <a name="compiler-warning-level-1-c4620"></a>Derleyici Uyarısı (düzey 1) C4620

' Type ' türü için hiçbir ' operator + + ' sonek biçimi bulunamadı; önek biçimi kullanılıyor

Verilen tür için tanımlanmış bir sonek artışı işleci yok. Derleyici aşırı yüklenmiş ön ek işlecini kullandı.

Bu uyarı, bir sonek `++` işleci tanımlayarak önlenebilir. `++` işlecinin iki bağımsız değişkenli bir sürümünü burada gösterildiği gibi oluşturun:

```cpp
// C4620.cpp
// compile with: /W1
class A
{
public:
   A(int nData) : m_nData(nData)
   {
   }

   A operator++()
   {
      m_nData -= 1;
      return *this;
   }

   // A operator++(int)
   // {
   //    A tmp = *this;
   //    m_nData -= 1;
   //    return tmp;
   // }

private:
   int m_nData;
};

int main()
{
   A a(10);
   ++a;
   a++;   // C4620
}
```