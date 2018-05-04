---
title: _aligned_msize | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_msize
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _aligned_msize
- aligned_msize
dev_langs:
- C++
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2375ec8f61a95ec018ea55cc1f891ad8049748c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="alignedmsize"></a>_aligned_msize

Yığın ayrılan bellek bloğu boyutu döndürür.

## <a name="syntax"></a>Sözdizimi

```C
size_t _msize(
   void *memblock,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Bellek bloğu işaretçi.

*Hizalama*<br/>
Hizalama değeri bir tamsayı güç 2 olmalıdır.

*uzaklık*<br/>
Hizalama zorlamak için bellek ayırma içine uzaklığı.

## <a name="return-value"></a>Dönüş Değeri

Boyutu (bayt) imzalanmamış tamsayı olarak döndürür.

## <a name="remarks"></a>Açıklamalar

**_Aligned_msize** işlevi için bir çağrı tarafından ayrılan bellek bloğu bayt cinsinden boyutu döndürüyor [_aligned_malloc](aligned-malloc.md) veya [_aligned_realloc](aligned-realloc.md). *Hizalama* ve *uzaklık* değerler blok ayrılan işleve değerleri aynı olmalıdır.

Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında **_aligned_msize** çözümler [_aligned_msize_dbg](aligned-msize-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

Bu işlev, parametre doğrular. Varsa *memblock* null işaretçi veya *hizalama* 2 ' nin güç değil **_msize** açıklandığı gibi bir geçersiz parametre işleyiciyi çağırır [parametre doğrulama ](../../c-runtime-library/parameter-validation.md). Hata işleniyorsa işlevi ayarlar **errno** için **EINVAL** ve -1 döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_msize**|\<malloc.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
