---
title: _AddressOfReturnAddress
ms.date: 11/04/2016
f1_keywords:
- _AddressOfReturnAddress_cpp
- _AddressOfReturnAddress
helpviewer_keywords:
- _AddressOfReturnAddress intrinsic
- AddressOfReturnAddress intrinsic
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
ms.openlocfilehash: 79d1e4645c60fb4231a53aaefdcf1fe0f3c876c4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024783"
---
# <a name="addressofreturnaddress"></a>_AddressOfReturnAddress

**Microsoft'a özgü**

Geçerli fonksiyonun dönüş adresi tutan bellek konumunun adresini sağlar. Bu adres, diğer bellek konumları (örneğin, işlev bağımsız) erişmek için kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
void * _AddressOfReturnAddress();
```

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_AddressOfReturnAddress`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Zaman `_AddressOfReturnAddress` ile derlenmiş bir program kullanılır [/CLR](../build/reference/clr-common-language-runtime-compilation.md), işlevi içeren `_AddressOfReturnAddress` yerel bir işlev çağrısı derlenmiştir. Ne zaman olarak bir işlev derlenmiş yönetilen işlevi içeren içine çağrıları `_AddressOfReturnAddress`, `_AddressOfReturnAddress` beklendiği gibi çalışmayabilir.

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```
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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)