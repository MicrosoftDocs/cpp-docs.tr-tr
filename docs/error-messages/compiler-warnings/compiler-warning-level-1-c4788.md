---
title: Derleyici Uyarısı (düzey 1) C4788
ms.date: 11/04/2016
f1_keywords:
- C4788
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
ms.openlocfilehash: c51a4409c2a3028823462539343654b5eac365d0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598178"
---
# <a name="compiler-warning-level-1-c4788"></a>Derleyici Uyarısı (düzey 1) C4788

'identifier': tanımlayıcı 'number' karakter olarak kesildi

Derleyici, bir işlev adı için izin verilen uzunluk sınırını kısıtlar. Derleyici funclets EH/SEH kodu oluşturduğunda, bazı metinleri işlevi adıyla eklenerek funclet'inde adı oluşturur, örneğin "__catch", "\__unwind", veya başka bir dize.

Sonuçta elde edilen funclet'inde adı çok uzun olabilir ve derleyici kesme ve C4788 oluşturur.

Bu uyarıyı çözmek için orijinal işlev adını kısaltın. İşlevi, bir C++ şablon işlevi veya yöntemi ise, adın bir bölümü için bir typedef kullanın. Örneğin:

```
C1<x, y, z<T>>::C2<a,b,c>::f
```

tarafından değiştirilebilir:

```
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;
new_class::f
```

Bu uyarı yalnızca içinde x64 oluşur derleyici.