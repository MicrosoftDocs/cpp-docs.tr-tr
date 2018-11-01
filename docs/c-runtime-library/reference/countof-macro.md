---
title: _countof Makrosu
ms.date: 03/22/2018
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
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
ms.openlocfilehash: 60b4350d6cf14a545de67de0bdaee70ee2099006
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536142"
---
# <a name="countof-macro"></a>_countof Makrosu

Statik olarak ayrılan bir dizideki öğelerin sayısını hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>Parametreler

*Dizi*<br/>
Bir dizinin adı.

## <a name="return-value"></a>Dönüş Değeri

İfade bir dizinin içindeki öğelerin sayısını bir **size_t**.

## <a name="remarks"></a>Açıklamalar

**_countof** işlev benzeri önişlemci makrosu uygulanır. C++ statik olarak bildirilen bir dizi yerine bir işaretçi geçirilirse, derleme zamanında algılamak için ek şablon makineler vardır.

Emin *dizi* aslında bir dizi, bir işaretçi. C'de, **_countof** , hatalı sonuçlar üreten *dizi* gösteren bir işaretçidir. C++ ' ta **_countof** derlemeniz başarısız *dizi* gösteren bir işaretçidir.  Bir dizi bir işleve parametre olarak geçen *decays işaretçi*, yani, işlev içinde kullanamazsınız **_countof** dizi kapsamını belirlemek için.

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
