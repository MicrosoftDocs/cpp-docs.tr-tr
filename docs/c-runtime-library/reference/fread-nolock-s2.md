---
title: _fread_nolock_s2
ms.date: 11/04/2016
apiname:
- _fread_nolock_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fread_nolock_s
- stdio/_fread_nolock_s
ms.assetid: 5badb9ab-11df-4e17-8162-30bda2a4572e
ms.openlocfilehash: 1dccbd362577e524f0455a2248d4d0f209ea6295
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333111"
---
# <a name="freadnolocks"></a>_fread_nolock_s

Veriler başka iş parçacıklarının kilitleme olmadan bir akıştan okur. Bu sürümü [fread_nolock](fread-nolock.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*Arabellek*<br/>
Veri için depolama konumu.

*BufferSize*<br/>
Hedef arabelleğin bayt cinsinden boyutu.

*elementSize*<br/>
Okunan bayt öğe boyutu.

*elementCount*<br/>
Okunacak öğe maksimum sayısı.

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Bkz: [fread_s](fread-s.md).

## <a name="remarks"></a>Açıklamalar

Bu işlev, kilitleme yapılmayan bir sürümünü **fread_s**. Aynıdır **fread_s** , başka iş parçacıklarının engellemelerinden korunmamaları hariç aynıdırlar. Diğer iş parçacıklarının kilitleme yüküne tabi olmayan çünkü daha hızlı olabilir. Bu işlev yalnızca tek iş parçacıklı uygulamalar ve burada çağırma kapsamının iş parçacığı yalıtımını zaten işlediği gibi iş parçacığı bakımından güvenli bağlamlarda kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fread_nolock_s**|C: \<stdio.h >; C++: \<cstdio > veya \<stdio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
