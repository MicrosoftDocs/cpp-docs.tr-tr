---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4621'
title: Derleyici Uyarısı (düzey 1) C4621
ms.date: 11/04/2016
f1_keywords:
- C4621
helpviewer_keywords:
- C4621
ms.assetid: 40931bd9-cb89-497e-86f0-cec9f016c63c
ms.openlocfilehash: 72e4adbb45488b200ff67f1d0b225591f9ea1a6b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281476"
---
# <a name="compiler-warning-level-1-c4621"></a>Derleyici Uyarısı (düzey 1) C4621

' Type ' türü için hiçbir ' operator--' sonek biçimi bulunamadı; önek biçimi kullanılıyor

Verilen tür için tanımlı sonek azaltma işleci yoktu. Derleyici aşırı yüklenmiş ön ek işlecini kullandı.

Bu uyarı, bir sonek operatörü tanımlayarak önlenebilir `--` . İşlecin iki bağımsız değişkenli bir sürümünü `--` aşağıda gösterildiği gibi oluşturun:

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
