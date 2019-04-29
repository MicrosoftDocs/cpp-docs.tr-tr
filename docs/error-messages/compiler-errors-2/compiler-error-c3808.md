---
title: Derleyici Hatası C3808
ms.date: 11/04/2016
f1_keywords:
- C3808
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
ms.openlocfilehash: 0a1b0b82241c6e48d2c1941ff8122697d11492eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352994"
---
# <a name="compiler-error-c3808"></a>Derleyici Hatası C3808

> '*türü*': ComImport özniteliğine sahip sınıf üyesi olarak tanımlanamaz '*üye*', yalnızca soyut veya dllimport işlevlerine izin veriliyor

## <a name="remarks"></a>Açıklamalar

Tan türetilmiş bir tür <xref:System.Runtime.InteropServices.ComImportAttribute> tanımlanamaz *üye*.

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3808 oluşturur.

```cpp
// C3808.cpp
// compile with: /c /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 {
   int f() {}   // C3808
   virtual int g() abstract;   // OK

   [DllImport("msvcrt.dll")]
   int printf(System::String ^, int i);   // OK
};
```