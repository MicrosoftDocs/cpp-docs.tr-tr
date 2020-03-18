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
- _rmtmp
helpviewer_keywords:
- removing temporary files
- _rmtmp function
- files [C++], temporary
- rmtmp function
- files [C++], removing
- temporary files [C++], removing
ms.assetid: 7419501e-2587-4f2a-b469-0dca07f84736
ms.openlocfilehash: de28768f479df00eae315c99b80103c5319b38af
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442787"
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
