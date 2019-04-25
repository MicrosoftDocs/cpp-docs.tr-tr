---
title: Derleyici Uyarısı C4936
ms.date: 11/04/2016
f1_keywords:
- C4936
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
ms.openlocfilehash: bbb69cccbf93be6e97d13db5008780f57e63f9da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280860"
---
# <a name="compiler-warning-c4936"></a>Derleyici Uyarısı C4936

> Bu __declspec yalnızca/CLR veya/CLR ile derlendiğinde desteklenir: Saf

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

A `__declspec` değiştiricisi, ancak kullanıldı `__declspec` değiştiricisi geçerlidir yalnızca biri ile derlendiğinde [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) seçenekleri.

Daha fazla bilgi için [appdomain](../../cpp/appdomain.md) ve [işlem](../../cpp/process.md).

C4936 her zaman hata olarak verilir.  İle C4936 devre dışı bırakabilirsiniz [uyarı](../../preprocessor/warning.md) pragması.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4936 oluşturur:

```cpp
// C4936.cpp
// compile with: /c
// #pragma warning (disable : 4936)
__declspec(process) int i;   // C4936
__declspec(appdomain) int j;   // C4936
```