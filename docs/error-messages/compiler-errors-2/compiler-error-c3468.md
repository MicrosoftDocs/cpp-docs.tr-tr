---
title: Derleyici Hatası C3468 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3468
dev_langs:
- C++
helpviewer_keywords:
- C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ccd7238fa7101f70ce2e15a6cd39030934901fb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023962"
---
# <a name="compiler-error-c3468"></a>Derleyici Hatası C3468

'type': bir tür yalnızca bir derlemeye iletebilirsiniz:

'`file`' bir derleme değil

Yalnızca bir bütünleştirilmiş kodundaki türler iletilebilir.

Daha fazla bilgi için [tür iletme (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir modül oluşturur.

```
// C3468.cpp
// compile with: /LN /clr
public ref class R {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3468 oluşturur.

```
// C3468_b.cpp
// compile with: /clr /c
#using "C3468.netmodule"
[ assembly:TypeForwardedTo(R::typeid) ];   // C3468
```