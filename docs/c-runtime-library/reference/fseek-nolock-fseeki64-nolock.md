---
title: _fseek_nolock, _fseeki64_nolock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fseek_nolock
- _fseeki64_nolock
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
- _fseek_nolock
- _fseeki64_nolock
- fseek_nolock
- fseeki64_nolock
dev_langs:
- C++
helpviewer_keywords:
- _fseek_nolock function
- fseeki64_nolock function
- file pointers [C++], moving
- fseek_nolock function
- _fseeki64_nolock function
- seek file pointers
ms.assetid: 2dd4022e-b715-462b-b935-837561605a02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40eca7e4944d74e8b86d5318702c954d86a3f54f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fseeknolock-fseeki64nolock"></a>_fseek_nolock, _fseeki64_nolock

Dosya işaretçisini belirtilen bir konuma taşır.

## <a name="syntax"></a>Sözdizimi

```C
int _fseek_nolock(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64_nolock(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Parametreler

*Akış*<br/>
İşaretçi **dosya** yapısı.

*uzaklık*<br/>
Bayt sayısı *kaynak*.

*Kaynak*<br/>
Başlangıç konumu.

## <a name="return-value"></a>Dönüş Değeri

Aynı [fseek](fseek-fseeki64.md) ve [_fseeki64](fseek-fseeki64.md)sırasıyla.

## <a name="remarks"></a>Açıklamalar

Bu işlevler kilitleme olmayan sürümleri şunlardır: [fseek](fseek-fseeki64.md) ve [_fseeki64](fseek-fseeki64.md)sırasıyla. Bunlar aynı [fseek](fseek-fseeki64.md) ve [_fseeki64](fseek-fseeki64.md) dışında diğer iş parçacıkları tarafından girişime korunmaz. Bunlar başka bir iş parçacığı kilitleme zahmetine değil çünkü bu işlevler daha hızlı olabilir. Bu işlevler yalnızca iş parçacığı bağlamları tek iş parçacıklı uygulamalar veya arama kapsamı zaten iş parçacığı yalıtım işleme olduğu gibi kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fseek_nolock**, **_fseeki64_nolock**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
