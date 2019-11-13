---
title: Derleyici Uyarısı (düzey 1) C4621
ms.date: 11/04/2016
f1_keywords:
- C4621
helpviewer_keywords:
- C4621
ms.assetid: 40931bd9-cb89-497e-86f0-cec9f016c63c
ms.openlocfilehash: 9dd4defe18a94f65e265d02f6c26c715667cd696
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052599"
---
# <a name="compiler-warning-level-1-c4621"></a>Derleyici Uyarısı (düzey 1) C4621

' Type ' türü için hiçbir ' operator--' sonek biçimi bulunamadı; önek biçimi kullanılıyor

Verilen tür için tanımlı sonek azaltma işleci yoktu. Derleyici aşırı yüklenmiş ön ek işlecini kullandı.

Bu uyarı, bir sonek `--` işleci tanımlayarak önlenebilir. `--` işlecinin iki bağımsız değişkenli bir sürümünü aşağıda gösterildiği gibi oluşturun:

```cpp
// C4621.cpp
// compile with: /W1
class A
{
public:
   A(int nData) : m_nData(nData)
   {
   }

   A operator--()
   {
      m_nData -= 1;
      return *this;
   }

   // A operator--(int)
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
   --a;
   a--;   // C4621
}
```