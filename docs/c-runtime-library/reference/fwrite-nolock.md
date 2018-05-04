---
title: _fwrite_nolock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fwrite_nolock
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
- _fwrite_nolock
- fwrite_nolock
dev_langs:
- C++
helpviewer_keywords:
- fwrite_nolock function
- streams, writing data to
- _fwrite_nolock function
ms.assetid: 2b4ec6ce-742e-4615-8407-44a0a18ec1d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e22f2c281b076e64419686b9f7c058e284cc5532
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fwritenolock"></a>_fwrite_nolock

Verileri, iş parçacığı kilitlemeden bir akışa yazar.

## <a name="syntax"></a>Sözdizimi

```C
size_t _fwrite_nolock(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
İşaretçi yazılacak veriler.

*Boyutu*<br/>
Öğe boyutunu bayt cinsinden.

*Sayısı*<br/>
Yazılacak öğe maksimum sayısı.

*Akış*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Aynı [fwrite](fwrite.md).

## <a name="remarks"></a>Açıklamalar

Bu işlev bir kilitleme sürümüdür **fwrite**. Aynı **fwrite** dışında girişime diğer iş parçacıkları tarafından korunmuyor. Başka bir iş parçacığı kilitleme yükünü artırmak değil olduğundan daha hızlı olabilir. Tek iş parçacıklı uygulamalar veya arama kapsamı zaten iş parçacığı yalıtım işler burada gibi iş parçacığı bağlamlarda yalnızca bu işlevi kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fwrite_nolock**|\<stdio.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [fread](fread.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fread](fread.md)<br/>
[_write](write.md)<br/>
