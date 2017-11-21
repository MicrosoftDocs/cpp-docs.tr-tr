---
title: _countof makrosu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 71d4310525f1d96184749b5b0b24cb0cf1da8512
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="countof-macro"></a>_countof Makrosu
Statik olarak ayrılmış bir dizi öğelerin sayısını hesaplayın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t _countof(   
   array  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `array`  
 Bir dizinin adı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dizideki olarak ifade edilen öğelerin sayısı bir `size_t`.  
  
## <a name="remarks"></a>Açıklamalar  
 Emin `array` aslında bir dizi, işaretçisi değil. C, `_countof` , hatalı sonuçlar oluşturabilir `array` gösteren bir işaretçidir. C++ ' ta `_countof` derlemeniz başarısız olur `array` gösteren bir işaretçidir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Makrosu|Gerekli başlık|  
|-----------|---------------------|  
|`_countof`|\<stdlib.h >|  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [sizeof işleci](../../cpp/sizeof-operator.md)