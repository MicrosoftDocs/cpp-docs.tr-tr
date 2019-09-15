---
title: _rmtmp
ms.date: 11/04/2016
api_name:
- _rmtmp
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- rmtmp
- _rmtmp
helpviewer_keywords:
- removing temporary files
- _rmtmp function
- files [C++], temporary
- rmtmp function
- files [C++], removing
- temporary files [C++], removing
ms.assetid: 7419501e-2587-4f2a-b469-0dca07f84736
ms.openlocfilehash: 314399cf174974132a3635631162a7ffa89342c4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949155"
---
# <a name="_rmtmp"></a>_rmtmp

Geçici dosyaları kaldırır.

## <a name="syntax"></a>Sözdizimi

```C

int _rmtmp( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_rmtmp** kapatılan ve silinen geçici dosya sayısını döndürür.

## <a name="remarks"></a>Açıklamalar

**_Rmtmp** işlevi, geçerli dizindeki tüm geçici dosyaları temizler. İşlevi yalnızca **tmpfile**tarafından oluşturulan dosyaları kaldırır; Bunu yalnızca geçici dosyaların oluşturulduğu dizinde kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_rmtmp**|\<stdio. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

[Tmpfile](tmpfile.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_flushall](flushall.md)<br/>
[tmpfile](tmpfile.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
