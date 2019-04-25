---
title: Derleyici Hatası C2299
ms.date: 11/04/2016
f1_keywords:
- C2299
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
ms.openlocfilehash: 4776ddede31dbcebe56a5919fd111f4df7248215
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182697"
---
# <a name="compiler-error-c2299"></a>Derleyici Hatası C2299

'function': davranış değişikliği: bir açık özelleştirme bir kopya Oluşturucusu veya kopya atama işleci olamaz

Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak da oluşturulabilir: Visual C++'ın önceki sürümlerinde izin verilen açık uzmanlık bir kopya Oluşturucusu veya kopya atama işleci.

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