---
title: Derleyici hatası C2299
ms.date: 11/04/2016
f1_keywords:
- C2299
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
ms.openlocfilehash: 009a441ec610053176e79126d9f2663f29b26bc6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759054"
---
# <a name="compiler-error-c2299"></a>Derleyici hatası C2299

' function ': davranış değişikliği: bir açık özelleştirme bir kopya Oluşturucusu veya kopya atama işleci olamaz

Bu hata, Visual Studio 2005 için yapılan derleyici uygunluk işinin sonucu olarak da oluşturulabilir: önceki görsel C++ sürümleri, bir kopya Oluşturucusu veya kopya atama işleci için açık uzmanlıklarla izin verilir.

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
