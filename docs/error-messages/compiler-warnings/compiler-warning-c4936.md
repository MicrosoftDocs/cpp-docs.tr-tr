---
title: Derleyici Uyarısı C4936 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4936
dev_langs:
- C++
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0be4a565dd251da77174c401c23b8ed8bfc531b0
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34703945"
---
# <a name="compiler-warning-c4936"></a>Derleyici Uyarısı C4936

> Bu __declspec yalnızca/CLR veya/CLR ile derlendiğinde desteklenir: Saf

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

A `__declspec` değiştiricisi, ancak kullanıldı `__declspec` değiştiricisi geçerli yalnızca biri ile derlendiğinde [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) seçenekleri.

Daha fazla bilgi için bkz: [appdomain](../../cpp/appdomain.md) ve [işlem](../../cpp/process.md).

C4936 her zaman hata olarak verilir.  C4936 ile devre dışı bırakabilirsiniz [uyarı](../../preprocessor/warning.md) pragması.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4936 oluşturur:

```cpp
// C4936.cpp
// compile with: /c
// #pragma warning (disable : 4936)
__declspec(process) int i;   // C4936
__declspec(appdomain) int j;   // C4936
```