---
title: Derleyici Hatası C3880
ms.date: 11/04/2016
f1_keywords:
- C3880
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
ms.openlocfilehash: 0b169309db88291f8a83b6d1192787b6396e84a5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776341"
---
# <a name="compiler-error-c3880"></a>Derleyici Hatası C3880

'var': sabit değerli veri üyesi olamaz

Türü bir [değişmez değer](../../extensions/literal-cpp-component-extensions.md) özniteliği olmalıdır, ya da derleme zamanı dönüştürülebilir için aşağıdaki türlerden biri:

- tamsayı türü

- dize

- bir tamsayı ya da temel alınan türü ile numaralandırma

Aşağıdaki örnek, C3880 oluşturur:

```
// C3880.cpp
// compile with: /clr /c
ref struct Y1 {
   literal System::Decimal staticConst1 = 10;   // C3880
   literal int staticConst2 = 10;   // OK
};
```