---
title: Derleyici Uyarısı C4958 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4958
dev_langs:
- C++
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e32acc4ec45275976e7fb56f993b10ba8a2a855
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704879"
---
# <a name="compiler-warning-c4958"></a>Derleyici Uyarısı C4958

> '*işlemi*': işaretçi aritmetiği doğrulanabilen değil

## <a name="remarks"></a>Açıklamalar

İşaretçi aritmetiği kullanarak doğrulanamayan bir görüntü oluşturur.

Daha fazla bilgi için bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: safe** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Bu uyarıyı hata olarak verilir ve ile devre dışı bırakılabilir [uyarı](../../preprocessor/warning.md) pragma veya [/wd](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4958 oluşturur:

```cpp
// C4958.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )
using namespace System;

int main( ) {
   Int32 arr[] = new Int32[10];
   Int32* p = &arr[0];
   p++;   // C4958
}
```

İşaretçi aritmetiği dizi işlemleriyle derleyici uygular. Bu nedenle, yerel diziler doğrulanabilir değildir; CLR dizisi kullanın. Daha fazla bilgi için bkz: [dizi](../../windows/arrays-cpp-component-extensions.md).

Aşağıdaki örnek C4958 oluşturur:

```cpp
// C4958b.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )

int main() {
   int array[5];
   array[4] = 0;   // C4958
}
```