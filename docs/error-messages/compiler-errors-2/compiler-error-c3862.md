---
title: Derleyici Hatası C3862 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b21e457feb6d090e4abaf531293987eb3504457
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704977"
---
# <a name="compiler-error-c3862"></a>Derleyici Hatası C3862

> '*işlevi*': / CLR ile yönetilmeyen işlev derlenemiyor: Saf veya/CLR: safe

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Derleme ile **/CLR: pure** veya **/CLR: safe** görüntüyü yerel (yönetilmeyen) kod olmadan bir MSIL yalnızca görüntü oluşturur.  Bu nedenle, kullanamazsınız `unmanaged` pragma içinde bir **/CLR: pure** veya **/CLR: safe** derleme.

Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3862 oluşturur:

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```