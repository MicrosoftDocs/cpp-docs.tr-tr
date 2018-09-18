---
title: Derleyici Hatası C3087 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3087
dev_langs:
- C++
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a95b14df3701d26a249e8e0d0e8ec4bafe5eb0d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041616"
---
# <a name="compiler-error-c3087"></a>Derleyici Hatası C3087

'named_argument': 'attribute' çağrısı bu üyeyi zaten başlatıyor

Aynı öznitelik engelle adlandırılmamış bir bağımsız değişken için aynı değer olarak adlandırılmış bir bağımsız değişken belirtildi. Yalnızca bir adlandırılmış veya adsız bağımsız değişkenini belirtin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3087 oluşturur.

```
// C3087.cpp
// compile with: /c
[idl_quote("quote1", text="quote2")];   // C3087
[idl_quote(text="quote3")];   // OK
[idl_quote("quote4")];   // OK
```