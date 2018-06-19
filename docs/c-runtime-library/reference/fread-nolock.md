---
title: _fread_nolock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- fread_nolock function
- _fread_nolock function
- streams [C++], reading data from
ms.assetid: 60e4958b-1097-46f5-a77b-94af5e7dba40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 444a4b371eb6b4add140c5d0d96f48a69e35152c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396715"
---
# <a name="freadnolock"></a>_fread_nolock

Verileri başka bir iş parçacığı kilitlemeden bir akıştan okur.

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
Verileri için depolama konumu.

*Boyutu*<br/>
Öğe boyutunu bayt cinsinden.

*Sayısı*<br/>
Okunacak öğe maksimum sayısı.

*Akış*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Bkz: [fread](fread.md).

## <a name="remarks"></a>Açıklamalar

Bu işlev bir kilitleme sürümüdür **fread**. Aynı **fread** dışında girişime diğer iş parçacıkları tarafından korunmuyor. Başka bir iş parçacığı kilitleme yükünü artırmak değil olduğundan daha hızlı olabilir. Tek iş parçacıklı uygulamalar veya arama kapsamı zaten iş parçacığı yalıtım işler burada gibi iş parçacığı bağlamlarda yalnızca bu işlevi kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fread_nolock**|\<stdio.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
