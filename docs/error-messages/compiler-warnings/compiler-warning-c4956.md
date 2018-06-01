---
title: Derleyici Uyarısı C4956 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4956
dev_langs:
- C++
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be92eb948e31a0a5367f92f5c2ed59baac2bd39b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34703710"
---
# <a name="compiler-warning-c4956"></a>Derleyici Uyarısı C4956

> '*türü*': Bu tür doğrulanabilen değil

## <a name="remarks"></a>Açıklamalar

Bu uyarı oluşturulduğu zaman [/CLR: safe](../../build/reference/clr-common-language-runtime-compilation.md) belirtilir ve kodunuzu doğrulanabilen değil bir türü içeriyor. **/CLR: safe** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Daha fazla bilgi için bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Bu uyarıyı hata olarak verilir ve ile devre dışı bırakılabilir [uyarı](../../preprocessor/warning.md) pragma veya [/wd](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4956 oluşturur:

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```