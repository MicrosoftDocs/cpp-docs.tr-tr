---
title: Derleyici Hatası C2674 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2674
dev_langs:
- C++
helpviewer_keywords:
- C2674
ms.assetid: 7cbd70d8-d992-44d7-a5cb-dd8cf9c759d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1e8a3533d1f2ac7a309f89e52a03b3ff8a62dec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037742"
---
# <a name="compiler-error-c2674"></a>Derleyici Hatası C2674

Bu bağlamda genel bir bildirimine izin verilmez

Genel yanlış bildirildi. Daha fazla bilgi için [genel türler](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2674 oluşturur.

```
// C2674.cpp
// compile with: /clr /c
void F(generic <class T> ref class R1);   // C2674
generic <class T> ref class R2 {};   // OK
```