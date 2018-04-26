---
title: _countof makrosu | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _countof
- countof
dev_langs:
- C++
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e9e5dc49b59ac534d871d6b31efdeec0afef5c8d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="countof-macro"></a>_countof Makrosu

Statik olarak ayrılmış bir dizi öğe sayısı hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>Parametreler

*Dizi*<br/>
Bir dizinin adı.

## <a name="return-value"></a>Dönüş Değeri

Dizideki olarak ifade edilen öğelerin sayısı bir **size_t**.

## <a name="remarks"></a>Açıklamalar

**_countof** işlevi benzeri önişlemci makrosu uygulanır. C++ sürümü bir işaretçi bir statik olarak bildirilen dizi yerine aktarılırsa derleme zamanında algılamak için ek şablon makineler içerir.

Emin *dizi* aslında bir dizi, işaretçisi değil. C, **_countof** , hatalı sonuçlar üretir *dizi* gösteren bir işaretçidir. C++ ' ta **_countof** derlemeniz başarısız *dizi* gösteren bir işaretçidir.  Bir dizi işlevi için parametre olarak geçirilen *işaretçisi decays*, yani işlevi içinde kullanamazsınız **_countof** dizi kapsamını belirlemek için.

## <a name="requirements"></a>Gereksinimler

|Makrosu|Gerekli başlık|
|-----------|---------------------|
|**_countof**|\<stdlib.h >|

## <a name="example"></a>Örnek

```cpp
// crt_countof.cpp
#define _UNICODE
#include <stdio.h>
#include <stdlib.h>
#include <tchar.h>

int main( void )
{
   _TCHAR arr[20], *p;
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );
   // In C++, the following line would generate a compile-time error:
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)

   _tcscpy_s( arr, _countof(arr), _T("a string") );
   // unlike sizeof, _countof works here for both narrow- and wide-character strings
}
```

```Output
sizeof(arr) = 40 bytes
_countof(arr) = 20 elements
```

## <a name="see-also"></a>Ayrıca bkz.

[sizeof İşleci](../../cpp/sizeof-operator.md)<br/>
