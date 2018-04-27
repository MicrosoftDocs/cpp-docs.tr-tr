---
title: _malloc_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _malloc_dbg
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
- malloc_dbg
- _malloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- malloc_dbg function
- memory allocation
- _malloc_dbg function
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 080bd3813fe14187df7f6b6184a0cfe21e9c5243
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="mallocdbg"></a>_malloc_dbg

Ek alan yığınla bellek bloğu için hata ayıklama üstbilgi ayırır ve arabellekler (yalnızca hata ayıklama sürümü) üzerine yazılır.

## <a name="syntax"></a>Sözdizimi

```C
void *_malloc_dbg(
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
İstenen boyut (bayt cinsinden) bellek bloğu.

*blockType*<br/>
İstenen bellek bloğu türü: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
İşaretçi ayırma işlemi ya da NULL istenen kaynak dosyanın adı.

*LineNumber*<br/>
Satır numarası burada ayırma işlemi istendi, ancak kaynak dosyasında veya NULL.

*Filename* ve *linenumber* parametreleri yalnızca kullanılabilir olduğunda **_malloc_dbg** açıkça çağrılan veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)önişlemci sabiti tanımlandı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlev bir işaretçi ayrılmış bellek bloğu kullanıcı bölümünü döndürür başarıyla tamamlandığında, yeni işleyici işlev çağrıları veya NULL döndürür. Dönüş davranışı tam bir açıklaması için aşağıdaki Açıklamalar bölümüne bakın. Yeni işleyici işlevi nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [malloc](malloc.md) işlevi.

## <a name="remarks"></a>Açıklamalar

**_malloc_dbg** bir hata ayıklama sürümü [malloc](malloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_malloc_dbg** yapılan bir çağrı için sınırlı **malloc**. Her ikisi de **malloc** ve **_malloc_dbg** bir temel yığınındaki bellek bloğu tahsis ancak **_malloc_dbg** birkaç hata ayıklama özellikleri sunar: kullanıcının her iki tarafında arabellekler belirli ayırma türleri izlemek için bir blok türü parametresi sızıntıları için test etmek için blok bölümünü ve *filename*/*linenumber* kökenini belirlemek için bilgi ayırma istek sayısı.

**_malloc_dbg** istenen biraz daha fazla alan ile bellek bloğu ayırır *boyutu*. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Blok atandığında, blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve 0xFD ile doldurulmuş her üzerine yaz arabellek.

**_malloc_dbg** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa veya (daha önce bahsedilen ek yük dahil) gerekli bellek miktarını aşarsa **_HEAP_ MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_malloc_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Nasıl kullanılacağına ilişkin bir örnek için **_malloc_dbg**, bkz: [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[malloc](malloc.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
