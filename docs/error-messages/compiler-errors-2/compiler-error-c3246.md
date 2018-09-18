---
title: Derleyici Hatası C3246 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3246
dev_langs:
- C++
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a588067fa21e0aeee54516bcec28cdf3648ac9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047817"
---
# <a name="compiler-error-c3246"></a>Derleyici Hatası C3246

'class': 'türünden' olarak bildirilmiş olsa devralınamıyor çünkü 'sealed' olarak

Olarak işaretlenmiş bir sınıf [korumalı](../../windows/sealed-cpp-component-extensions.md) herhangi diğer sınıflar için taban sınıf olamaz.

Aşağıdaki örnek, C3246 oluşturur:

```
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
