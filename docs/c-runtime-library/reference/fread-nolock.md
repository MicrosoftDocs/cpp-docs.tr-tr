---
title: _fread_nolock
ms.date: 11/04/2016
api_name:
- _fread_nolock
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
- _fread_nolock
- fread_nolock
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- fread_nolock function
- _fread_nolock function
- streams [C++], reading data from
ms.assetid: 60e4958b-1097-46f5-a77b-94af5e7dba40
ms.openlocfilehash: 2d896e3809d22c0f2752ef67c89233652bdade19
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956865"
---
# <a name="_fread_nolock"></a>_fread_nolock

Diğer iş parçacıklarını kilitlemeden bir akıştan verileri okur.

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

*arabelleğin*<br/>
Veriler için depolama konumu.

*boyutla*<br/>
Bayt cinsinden öğe boyutu.

*biriktirme*<br/>
Okunacak en fazla öğe sayısı.

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bkz. [fread](fread.md).

## <a name="remarks"></a>Açıklamalar

Bu işlev, **fread**'in kilitleme olmayan bir sürümüdür. Diğer iş parçacıkları tarafından girişime karşı korunmamaları dışında, **fread** ile özdeştir. Diğer iş parçacıklarını kilitleme yükünü karşılamadığından daha hızlı olabilir. Bu işlevi yalnızca tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fread_nolock**|\<stdio. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
