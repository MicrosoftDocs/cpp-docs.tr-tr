---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2299'
title: Derleyici hatası C2299
ms.date: 11/04/2016
f1_keywords:
- C2299
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
ms.openlocfilehash: eb96829c4e16153a0a304a5b2a9640d4591dec3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235105"
---
# <a name="compiler-error-c2299"></a>Derleyici hatası C2299

' function ': davranış değişikliği: bir açık özelleştirme bir kopya Oluşturucusu veya kopya atama işleci olamaz

Bu hata, Visual Studio 2005 için yapılan derleyici uygunluk işinin sonucu olarak da oluşturulabilir: önceki Visual C++, bir kopya Oluşturucusu veya kopya atama işleci için açık uzmanlıklarla izin verilir.

C2299 çözümlemek için, kopya Oluşturucuyu veya atama işlecini bir şablon işlevi yapmayın, bunun yerine bir sınıf türü alan şablon olmayan bir işlev. Şablon bağımsız değişkenlerini açıkça belirterek kopya Oluşturucuyu veya atama işlecini çağıran herhangi bir kod, şablon bağımsız değişkenlerini kaldırması gerekir.

Aşağıdaki örnek C2299 oluşturur:

```cpp
// C2299.cpp
// compile with: /c
class C {
   template <class T>
   C (T t);

   template <> C (const C&);   // C2299
   C (const C&);   // OK
};
```
