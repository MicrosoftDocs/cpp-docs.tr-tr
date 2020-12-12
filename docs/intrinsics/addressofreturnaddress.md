---
description: 'Hakkında daha fazla bilgi edinin: _AddressOfReturnAddress'
title: _AddressOfReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _AddressOfReturnAddress_cpp
- _AddressOfReturnAddress
helpviewer_keywords:
- _AddressOfReturnAddress intrinsic
- AddressOfReturnAddress intrinsic
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
ms.openlocfilehash: 1a79ccbe7ddc2865d8225a62cd0d294f0bc66b4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331925"
---
# <a name="_addressofreturnaddress"></a>_AddressOfReturnAddress

**Microsoft'a Özgü**

Geçerli işlevin dönüş adresini tutan bellek konumunun adresini sağlar. Bu adres, diğer bellek konumlarına (örneğin, işlevin bağımsız değişkenleri) erişmek için kullanılamaz.

## <a name="syntax"></a>Syntax

```C
void * _AddressOfReturnAddress();
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_AddressOfReturnAddress`|x86, x64, ARM, ARM64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

`_AddressOfReturnAddress` [/Clr](../build/reference/clr-common-language-runtime-compilation.md)ile derlenen bir programda kullanıldığında, çağrıyı içeren işlev `_AddressOfReturnAddress` yerel bir işlev olarak derlenir. İçeren işleve yönetilen çağrı olarak derlenen bir işlev `_AddressOfReturnAddress` `_AddressOfReturnAddress` beklendiği gibi davranmayabilir.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```cpp
// compiler_intrinsics_AddressOfReturnAddress.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

// This function will print three values:
//   (1) The address retrieved from _AddressOfReturnAdress
//   (2) The return address stored at the location returned in (1)
//   (3) The return address retrieved the _ReturnAddress* intrinsic
// Note that (2) and (3) should be the same address.
__declspec(noinline)
void func() {
   void* pvAddressOfReturnAddress = _AddressOfReturnAddress();
   printf_s("%p\n", pvAddressOfReturnAddress);
   printf_s("%p\n", *((void**) pvAddressOfReturnAddress));
   printf_s("%p\n", _ReturnAddress());
}

int main() {
   func();
}
```

```Output
0012FF78
00401058
00401058
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar sözcükler](../cpp/keywords-cpp.md)
