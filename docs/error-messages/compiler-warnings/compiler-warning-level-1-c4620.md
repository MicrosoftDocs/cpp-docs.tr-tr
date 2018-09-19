---
title: Derleyici Uyarısı (düzey 1) C4620 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4620
dev_langs:
- C++
helpviewer_keywords:
- C4620
ms.assetid: fed29934-b797-47e8-bbea-c7e5f8dd6e93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 117cd6d34ca25aebcfa392efcd95940891491e70
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118213"
---
# <a name="compiler-warning-level-1-c4620"></a>Derleyici Uyarısı (düzey 1) C4620

hiçbir sonek biçimi ' operator ++' 'type' önek biçimi kullanılıyor, türü için bulunamadı

Verilen tür için tanımlanmış herhangi bir sonek artırma işlecini yoktur. Derleyici, aşırı yüklenmiş bir önek işleci kullanılır.

Bu uyarı, bir sonek tanımlayarak önlenebilir `++` işleci. İki bağımsız değişkenli sürümü oluşturma `++` burada gösterildiği gibi işleç:

```
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