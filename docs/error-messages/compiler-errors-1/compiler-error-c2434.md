---
title: Derleyici hatası C2434
ms.date: 11/04/2016
f1_keywords:
- C2434
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
ms.openlocfilehash: 869db3b49075fa477860e045e59306e22a381ca4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205471"
---
# <a name="compiler-error-c2434"></a>Derleyici hatası C2434

> '*symbol*': __declspec (Process) ile belirtilen bir simge/clr: Pure modunda dinamik olarak başlatılamaz

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

**/Clr: Pure**altında işlem başına değişkeni dinamik olarak başlatmak mümkün değildir. Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [işlemi](../../cpp/process.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2434 oluşturur. Bu sorunu onarmak için `process` değişkenlerini başlatmak için sabitleri kullanın.

```cpp
// C2434.cpp
// compile with: /clr:pure /c
int f() { return 0; }
__declspec(process) int i = f();   // C2434
__declspec(process) int i2 = 0;   // OK
```
