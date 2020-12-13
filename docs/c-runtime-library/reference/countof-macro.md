---
description: 'Hakkında daha fazla bilgi edinin: _countof makrosu'
title: _countof Makrosu
ms.date: 03/22/2018
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _countof
- countof
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
ms.openlocfilehash: 190f47aa7bb6bcf6bbd9478cce9df90aca81b437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146464"
---
# <a name="_countof-macro"></a>_countof Makrosu

Statik olarak ayrılan dizideki öğelerin sayısını hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>Parametreler

*array*<br/>
Bir dizinin adı.

## <a name="return-value"></a>Dönüş Değeri

Dizide **size_t** olarak ifade edilen öğe sayısı.

## <a name="remarks"></a>Açıklamalar

**_countof** , işlev benzeri bir önişlemci makrosu olarak uygulanır. C++ sürümünde, statik olarak tanımlanmış bir dizi yerine bir işaretçi geçirilirse, derleme zamanında tespit edilecek ek şablon makineleri vardır.

*Dizinin* işaretçi değil, gerçekten bir dizi olduğundan emin olun. C 'de, *dizi* işaretçiyse **_countof** hatalı sonuçlar üretir. C++ ' da, *dizi* işaretçiyse **_countof** derlenemiyor.  Bir işleve parametre olarak geçirilen bir dizi, *bir işaretçiye işaret* eden, bu, işlevin içinde, dizinin kapsamını belirlemede **_countof** kullanamıyoruz.

## <a name="requirements"></a>Gereksinimler

|Makroya|Gerekli başlık|
|-----------|---------------------|
|**_countof**|\<stdlib.h>|

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

[sizeof Işleci](../../cpp/sizeof-operator.md)<br/>
