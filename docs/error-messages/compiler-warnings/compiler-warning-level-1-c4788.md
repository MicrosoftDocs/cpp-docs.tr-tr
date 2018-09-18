---
title: Derleyici Uyarısı (düzey 1) C4788 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4788
dev_langs:
- C++
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c8a6ad1aa3ae17944b8c2a292d484d55c24d9cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051743"
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