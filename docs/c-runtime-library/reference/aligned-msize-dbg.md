---
title: _aligned_msize_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c16fd1292f78c8c3f6b3133050e27046fb003343
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="alignedmsizedbg"></a>_aligned_msize_dbg

Yığın (yalnızca hata ayıklama sürümü) ayrılan bellek bloğu boyutu döndürür.

## <a name="syntax"></a>Sözdizimi

```C
size_t _aligned_msize_dbg(
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

*Hizalama* ve *uzaklık* değerler blok ayrılan işleve değerleri aynı olmalıdır.

**_aligned_msize_dbg** bir hata ayıklama sürümü [_aligned_msize](aligned-msize.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_aligned_msize_dbg** yapılan bir çağrı için sınırlı **_aligned_msize**. Her ikisi de **_aligned_msize** ve **_aligned_msize_dbg** bir bellek bloğu içinde temel öbek boyutunu hesaplamak ancak **_aligned_msize_dbg** hata ayıklama özelliği ekler: içerir Her iki tarafında bellek kullanıcı kısmının arabellekleri döndürülen boyutu engelleyin.

Bu işlev, parametre doğrular. Varsa *memblock* null işaretçi veya *hizalama* 2 ' nin güç değil **_msize** açıklandığı gibi bir geçersiz parametre işleyiciyi çağırır [parametre doğrulama ](../../c-runtime-library/parameter-validation.md). Hata işleniyorsa işlevi ayarlar **errno** için **EINVAL** ve -1 döndürür.

Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_msize_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
