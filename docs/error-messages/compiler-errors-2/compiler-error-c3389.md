---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3389'
title: Derleyici hatası C3389
ms.date: 11/04/2016
f1_keywords:
- C3389
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
ms.openlocfilehash: b9fedf0993738d054cd5ded605d96001b3db13eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285506"
---
# <a name="compiler-error-c3389"></a>Derleyici hatası C3389

> __declspec (*anahtar sözcük*)/clr: pure veya/clr: Safe ile kullanılamaz

## <a name="remarks"></a>Açıklamalar

**`/clr:pure`** Ve **`/clr:safe`** derleyici seçenekleri visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

[`__declspec`](../../cpp/declspec.md)Kullanılan değiştirici işlem başına durumu gösterir.  [`/clr:pure`](../../build/reference/clr-common-language-runtime-compilation.md) durum başına anlamına gelir [`appdomain`](../../cpp/appdomain.md) .  Bu nedenle, *anahtar sözcük* **`__declspec`** değiştiricisi ve derleme ile birlikte bir değişken bildirmek için **`/clr:pure`** izin verilmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3389 oluşturur:

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```
