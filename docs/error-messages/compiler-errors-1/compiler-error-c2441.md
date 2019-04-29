---
title: Derleyici Hatası C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: 7fcf333f62253eb676c0f0ada1c927ab962ae1ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338928"
---
# <a name="compiler-error-c2441"></a>Derleyici Hatası C2441

> '*değişkeni*': __declspec(Process) ile bir simge const/CLR: pure modunda

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Varsayılan olarak, her uygulama etki alanı altında değişkenlerdir **/CLR: pure**. Bir değişken olarak işaretlenmiş `__declspec(process)` altında **/CLR: pure** değiştiren bir uygulama etki alanında ve diğer okuma hataları yatkındır.

Bu nedenle, derleyici her işlem değişkenleri olması zorunlu kılar `const` altında **/CLR: pure**, yalnızca tüm uygulama etki alanlarında yapma bunları okuyun.

Daha fazla bilgi için [işlem](../../cpp/process.md) ve [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2441 oluşturur.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```