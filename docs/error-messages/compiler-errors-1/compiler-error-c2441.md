---
title: Derleyici Hatası C2441 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d4224d9090f3ace43f61a10c599fafa78d21600
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705286"
---
# <a name="compiler-error-c2441"></a>Derleyici Hatası C2441

> '*değişkeni*': __declspec(process) ile bildirilen bir simge/CLR const: Saf modu

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Varsayılan olarak, her uygulama etki alanı altında değişkenlerdir **/CLR: pure**. Bir değişken olarak işaretlenmiş `__declspec(process)` altında **/CLR: pure** değiştiren bir uygulama etki alanı ve başka bir programda okuma hataları yatkındır.

Bu nedenle, her işlem değişkenlerin olması derleyici zorlar `const` altında **/CLR: pure**, yalnızca tüm uygulama etki alanlarında yapma bunları okuyun.

Daha fazla bilgi için bkz: [işlem](../../cpp/process.md) ve [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2441 oluşturur.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```