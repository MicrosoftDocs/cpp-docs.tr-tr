---
description: 'Hakkında daha fazla bilgi edinin: __emul __emulu'
title: __emul, __emulu
ms.date: 09/02/2019
f1_keywords:
- __emulu_cpp
- __emul
- __emul_cpp
- __emulu
helpviewer_keywords:
- __emul intrinsic
- __emulu intrinsic
ms.assetid: 79545236-cca2-40b8-a4e1-8abce9b26311
ms.openlocfilehash: cdcbd14e4e72bcaf7d2c7fd5f098a291e32227cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337058"
---
# <a name="__emul-__emulu"></a>__emul, __emulu

**Microsoft'a Özgü**

32 bit tamsayının tutabileceğinden taşan çoğullications gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```C
__int64 __emul(
   int a,
   int b
);
unsigned __int64 __emulu(
   unsigned int a,
   unsigned int b
);
```

### <a name="parameters"></a>Parametreler

*a*\
'ndaki Çarpma 'nın ilk tamsayı işleneni.

*kenarı*\
'ndaki Çarpma 'nın ikinci tamsayı işleneni.

## <a name="return-value"></a>Döndürülen değer

Çarpma sonucu.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__emul`|x86, x64|
|`__emulu`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

`__emul` 2 32 bitlik imzalı değerler alır ve çarpma 'nın sonucunu 64 bit işaretli tamsayı değeri olarak döndürür.

`__emulu` 2 32 bitlik işaretsiz tamsayı değerleri alır ve çarpma 'nın sonucunu 64 bit işaretsiz bir tamsayı değeri olarak döndürür.

## <a name="example"></a>Örnek

```cpp
// emul.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__emul)
#pragma intrinsic(__emulu)

int main()
{
   int a = -268435456;
   int b = 2;

   __int64 result = __emul(a, b);

   cout << a << " * " << b << " = " << result << endl;

   unsigned int ua = 0xFFFFFFFF; // Dec value: 4294967295
   unsigned int ub = 0xF000000;  // Dec value: 251658240

   unsigned __int64 uresult = __emulu(ua, ub);

   cout << ua << " * " << ub << " = " << uresult << endl;

}
```

## <a name="output"></a>Çıktı

```Output
-268435456 * 2 = -536870912
4294967295 * 251658240 = 1080863910317260800
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
