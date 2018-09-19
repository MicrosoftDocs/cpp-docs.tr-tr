---
title: Derleyici Hatası C2989 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2989
dev_langs:
- C++
helpviewer_keywords:
- C2989
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df67a24fa9bae63bbaf1bba344aa7f684ec91123
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081916"
---
# <a name="compiler-error-c2989"></a>Derleyici Hatası C2989

'class': sınıf türü zaten sınıf olmayan türü olarak bildirildi

Genel bir sınıf veya şablonu bir şablon olmayan veya genel olmayan sınıf yeniden tanımlar. Çakışmaları için üst bilgi dosyaları denetleyin.

Sınıf şablonu kısmi uzmanlıklar kullanıyorsanız Q240866 Bilgi Bankası makalesine bakın.

Aşağıdaki örnek, C2989 oluşturur:

```
// C2989.cpp
// compile with: /c
class C{};

template <class T>
class C{};  // C2989
class C2{};
```

C2989, genel türler kullanırken da meydana gelebilir:

```
// C2989b.cpp
// compile with: /clr /c
ref class GC1;

generic <typename T> ref class GC1;   // C2989
template <typename T> ref class GC2;

generic <typename T> ref class GC2;   // C2989
generic <typename T> ref class GCb;
template <typename T> ref class GC2;
generic <typename T> ref class GCc;
```