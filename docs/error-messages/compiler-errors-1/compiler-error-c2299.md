---
title: Derleyici Hatası C2299 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2299
dev_langs:
- C++
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4977f4a5ac81cf4c04d3b143f6f7e670a9d9279
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049624"
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