---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2434'
title: Derleyici hatası C2434
ms.date: 11/04/2016
f1_keywords:
- C2434
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
ms.openlocfilehash: e24eb3fdf2ae60dadc270bed1bdda251acfc70a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189970"
---
# <a name="compiler-error-c2434"></a>Derleyici hatası C2434

> '*symbol*': __declspec (Process) ile belirtilen bir simge/clr: Pure modunda dinamik olarak başlatılamaz

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

**/Clr: Pure** altında işlem başına değişkeni dinamik olarak başlatmak mümkün değildir. Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [işlemi](../../cpp/process.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2434 oluşturur. Bu sorunu onarmak için, değişkenleri başlatmak üzere sabitleri kullanın `process` .

```cpp
// C2434.cpp
// compile with: /clr:pure /c
int f() { return 0; }
__declspec(process) int i = f();   // C2434
__declspec(process) int i2 = 0;   // OK
```
