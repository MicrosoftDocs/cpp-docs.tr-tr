---
title: Derleyici hatası C3808
ms.date: 11/04/2016
f1_keywords:
- C3808
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
ms.openlocfilehash: e854764dc3f8d3ede79965302b62055b91df0a4c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165632"
---
# <a name="compiler-error-c3808"></a>Derleyici hatası C3808

> '*Type*': ComImport özniteliği olan bir sınıf '*member*' üyesini tanımlanamaz, yalnızca abstract veya dllimport işlevlerine izin verilir

## <a name="remarks"></a>Açıklamalar

<xref:System.Runtime.InteropServices.ComImportAttribute> türetilen bir tür *üye*tanımlayamazsınız.

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
