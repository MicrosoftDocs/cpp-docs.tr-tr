---
title: _fread_nolock_s2
ms.date: 11/04/2016
api_name:
- _fread_nolock_s
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
- _fread_nolock_s
- stdio/_fread_nolock_s
ms.assetid: 5badb9ab-11df-4e17-8162-30bda2a4572e
ms.openlocfilehash: e7fded9860b7a1364841d5f9b8a7e3aa478a8420
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956899"
---
# <a name="_fread_nolock_s"></a>_fread_nolock_s

Diğer iş parçacıklarını kilitlemeden bir akıştan verileri okur. Bu [fread_nolock](fread-nolock.md) sürümü, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri içerir.

## <a name="syntax"></a>Sözdizimi

```C
size_t _fread_nolock_s(
   void *buffer,
   size_t bufferSize,
   size_t elementSize,
   size_t elementCount,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*arabelleğin*<br/>
Veriler için depolama konumu.

*Boyutu*<br/>
Hedef arabelleğin bayt cinsinden boyutu.

*elementSize*<br/>
Okunan öğenin bayt cinsinden boyutu.

*elementCount*<br/>
Okunacak en fazla öğe sayısı.

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bkz. [fread_s](fread-s.md).

## <a name="remarks"></a>Açıklamalar

Bu işlev, **fread_s**'in kilitleme dışı bir sürümüdür. **Fread_s** ile aynıdır, ancak diğer iş parçacıkları tarafından girişim tarafından korunmamalıdır. Diğer iş parçacıklarını kilitleme yükünü karşılamadığından daha hızlı olabilir. Bu işlevi yalnızca tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fread_nolock_s**|C: \<stdio. h >; C++ :\<cstdio > veya \<stdio. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
