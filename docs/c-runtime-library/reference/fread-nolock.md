---
title: _fread_nolock
ms.date: 11/04/2016
apiname:
- _fread_nolock
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
- _fread_nolock
- fread_nolock
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- fread_nolock function
- _fread_nolock function
- streams [C++], reading data from
ms.assetid: 60e4958b-1097-46f5-a77b-94af5e7dba40
ms.openlocfilehash: 81827363d670c7cdeeddcb86390323bf431c6f98
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597294"
---
# <a name="freadnolock"></a>_fread_nolock

Veriler başka iş parçacıklarının kilitleme olmadan bir akıştan okur.

## <a name="syntax"></a>Sözdizimi

```C
size_t _fread_nolock(
   void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Veri için depolama konumu.

*Boyutu*<br/>
Bayt olarak öğe boyutu.

*Sayısı*<br/>
Okunacak öğe maksimum sayısı.

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Bkz: [fread](fread.md).

## <a name="remarks"></a>Açıklamalar

Bu işlev, kilitleme yapılmayan bir sürümünü **fread**. Aynıdır **fread** , başka iş parçacıklarının engellemelerinden korunmamaları hariç aynıdırlar. Diğer iş parçacıklarının kilitleme yüküne tabi olmayan çünkü daha hızlı olabilir. Bu işlev yalnızca tek iş parçacıklı uygulamalar ve burada çağırma kapsamının iş parçacığı yalıtımını zaten işlediği gibi iş parçacığı bakımından güvenli bağlamlarda kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fread_nolock**|\<stdio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
