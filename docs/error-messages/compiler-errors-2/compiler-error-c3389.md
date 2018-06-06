---
title: Derleyici Hatası C3389 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b540f87458c75ddf7d57626b6251248652b96213
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704311"
---
# <a name="compiler-error-c3389"></a>Derleyici Hatası C3389

> __declspec (*anahtar sözcüğü*) / CLR ile kullanılamaz: Saf veya/CLR: safe

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

A [__declspec](../../cpp/declspec.md) kullanılan değiştiricisi gelir bir başına işlem durumu.  [/ CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md) gelir bir başına [appdomain](../../cpp/appdomain.md) durumu.  Bu nedenle, sahip bir değişken bildirme `keyword` **__declspec** değiştiricisini ve ile derleme **/CLR: pure** verilmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3389 oluşturur:

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```