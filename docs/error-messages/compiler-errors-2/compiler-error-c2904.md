---
title: Derleyici Hatası C2904 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2904
dev_langs:
- C++
helpviewer_keywords:
- C2904
ms.assetid: d5802f2e-d3fc-473d-aa04-36957b4eaca5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 76f305ccab68a5b0d59cb3d4246b51fed61c6bf7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061571"
---
# <a name="compiler-error-c2904"></a>Derleyici Hatası C2904

'identifier': bir şablon geçerli kapsamda zaten kullanılan adı

Yinelenen adlara kodunu kontrol edin.

Aşağıdaki örnek, C2904 oluşturur:

```
// C2904.cpp
// compile with: /c
void X();  // X is declared as a function
template<class T> class X{};  // C2904
```