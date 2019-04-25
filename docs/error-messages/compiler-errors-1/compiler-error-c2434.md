---
title: Derleyici Hatası C2434
ms.date: 11/04/2016
f1_keywords:
- C2434
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
ms.openlocfilehash: c73a8d4fcde945ddf2495cc2d0d7dc47216f2db3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166340"
---
# <a name="compiler-error-c2434"></a>Derleyici Hatası C2434

> '*sembol*': __declspec(Process) ile bir simge/CLR dinamik olarak başlatılamaz: pure modunda

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Dinamik olarak bir işlem içi değişken altında başlatmak mümkün değil **/CLR: pure**. Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [işlem](../../cpp/process.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2434 oluşturur. Bu sorunu gidermek için başlatmak için sabitleri kullanın `process` değişkenleri.

```cpp
// C2434.cpp
// compile with: /clr:pure /c
int f() { return 0; }
__declspec(process) int i = f();   // C2434
__declspec(process) int i2 = 0;   // OK
```