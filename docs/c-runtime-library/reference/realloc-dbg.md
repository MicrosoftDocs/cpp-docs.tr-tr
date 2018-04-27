---
title: _realloc_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _realloc_dbg
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
- _realloc_dbg
- realloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- reallocating memory blocks
- realloc_dbg function
- memory blocks, reallocating
- memory, reallocating
- _realloc_dbg function
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dffe9ab2f63e39953749586341e1977126ca70d8
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="reallocdbg"></a>_realloc_dbg

Belirtilen bir yığınındaki bellek bloğu taşıma ve/veya blok (yalnızca hata ayıklama sürümü) yeniden boyutlandırma yeniden ayırır.

## <a name="syntax"></a>Sözdizimi

```C
void *_realloc_dbg(
   void *userData,
   size_t newSize,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*UserData*<br/>
Önceden ayrılmış bellek bloğu işaretçi.

*newSize*<br/>
Boyutu (bayt) reallocated bloğunun istedi.

*blockType*<br/>
İstenen reallocated bloğunun türü: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
İstenen kaynak dosyasının adını işaretçi **realloc** işlemi ya da NULL.

*LineNumber*<br/>
Satır numarası kaynak dosyasında nerede **realloc** işlemi istenen veya NULL.

*Filename* ve *linenumber* parametreleri yalnızca kullanılabilir olduğunda **_realloc_dbg** açıkça çağrılan veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) önişlemci sabiti tanımlandı.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev bir işaretçi ayrılabilecek bellek bloğu kullanıcı bölümünü döndürür, yeni işleyici işlevini çağırır ya da NULL döndürür. Dönüş davranışı tam bir açıklaması için aşağıdaki Açıklamalar bölümüne bakın. Yeni işleyici işlevi nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [realloc](realloc.md) işlevi.

## <a name="remarks"></a>Açıklamalar

**_realloc_dbg** bir hata ayıklama sürümü [realloc](realloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_realloc_dbg** yapılan bir çağrı için sınırlı **realloc**. Her ikisi de **realloc** ve **_realloc_dbg** bir bellek bloğu temel yığınındaki yeniden tahsis ancak **_realloc_dbg** birkaç hata ayıklama özelliği düzenler: her iki tarafında arabellekler belirli ayırma türleri izlemek için bir blok türü parametresi sızıntıları için test etmek için blok kullanıcı bölümünü ve *filename*/*linenumber* kökenini belirlemek için bilgi ayırma istek sayısı.

**_realloc_dbg** istenen biraz daha fazla alan ile belirtilen bellek bloğu yeniden ayırır *newSize*. *newSize* büyük ya da özgün olarak ayrılmış bellek bloğu boyutu küçüktür olabilir. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Yeniden ayırma özgün bellek bloğu yığınındaki farklı bir konuma taşıyarak, aynı zamanda bellek bloğu boyutunu değiştirme neden olabilir. Bellek bloğu taşınırsa, özgün bloğun içeriğinin üzerine yazılır.

**_realloc_dbg** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa veya (daha önce bahsedilen ek yük dahil) gerekli bellek miktarını aşarsa **_HEAP_ MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_realloc_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Örnekte bkz [_msize_dbg](msize-dbg.md) konu.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
