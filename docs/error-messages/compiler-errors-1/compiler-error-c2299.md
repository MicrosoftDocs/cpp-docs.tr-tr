---
title: Derleyici Hatası C2299
ms.date: 11/04/2016
f1_keywords:
- C2299
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
ms.openlocfilehash: 39659baebf7dc1859a69021f60ed452964ae61af
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447951"
---
# <a name="compiler-error-c2299"></a>Derleyici Hatası C2299

'function': davranış değişikliği: bir açık özelleştirme bir kopya Oluşturucusu veya kopya atama işleci olamaz

Bu hata için Visual Studio 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak da oluşturulabilir: önceki sürümleri Visual C++ açık uzmanlık bir kopya Oluşturucusu veya kopya atama işlecine izin.

C2299 gidermek için kopya oluşturucu veya atama işleci bir şablon işlevi, ancak bunun yerine bir sınıf türü alan bir şablon olmayan işlev yapmayın. Şablon bağımsız değişkenlerini kaldırmak şablon bağımsız değişkenleri açıkça belirterek kopya oluşturucu veya atama işlecini çağıran herhangi bir kod gerekir.

Aşağıdaki örnek, C2299 oluşturur:

```
// C2299.cpp
// compile with: /c
class C {
   template <class T>
   C (T t);

   template <> C (const C&);   // C2299
   C (const C&);   // OK
};
```