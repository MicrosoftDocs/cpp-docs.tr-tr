---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3808'
title: Derleyici hatası C3808
ms.date: 11/04/2016
f1_keywords:
- C3808
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
ms.openlocfilehash: e5d31e884de0b04caba7c52e8d6abc01b3d21a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315159"
---
# <a name="compiler-error-c3808"></a>Derleyici hatası C3808

> '*Type*': ComImport özniteliği olan bir sınıf '*member*' üyesini tanımlanamaz, yalnızca abstract veya dllimport işlevlerine izin verilir

## <a name="remarks"></a>Açıklamalar

Öğesinden türetilen bir tür <xref:System.Runtime.InteropServices.ComImportAttribute> *üye* tanımlayamazsınız.

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3808 oluşturur.

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
