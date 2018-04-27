---
title: _aligned_offset_realloc_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _aligned_offset_realloc_dbg
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
- aligned_offset_realloc_dbg
- _aligned_offset_realloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_realloc_dbg function
- _aligned_offset_realloc_dbg function
ms.assetid: 64e30a12-887e-453b-aea8-aed793fca9d8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 40d4215a7f9dbd4037305a2498d869211fa14165
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="alignedoffsetreallocdbg"></a>_aligned_offset_realloc_dbg

İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_offset_realloc_dbg(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Geçerli bellek bloğu işaretçisi.

*Boyutu*<br/>
Bellek ayırma boyutu.

*Hizalama*<br/>
Hizalama değeri bir tamsayı güç 2 olmalıdır.

*uzaklık*<br/>
Hizalama zorlamak için bellek ayırma içine uzaklığı.

*Dosya adı*<br/>
İstenen kaynak dosyasının adını işaretçi **aligned_offset_realloc** işlemi ya da NULL.

*LineNumber*<br/>
Satır numarası kaynak dosyasında nerede **aligned_offset_realloc** işlemi istenen veya NULL.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_offset_realloc_dbg** bırakılan (ve muhtemelen taşınan) bellek bloğuna void işaretçi döndürür. Dönüş değeri **NULL** boyutu sıfır ise ve arabellek bağımsız değişken değil **NULL**, veya blok verilen boyuta genişletmek için yeterli kullanılabilir bellek değilse. İlk durumda, özgün blok serbest bırakılır. İkinci durumda, özgün blok değiştirilmez. Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun hizalanacak garanti bir depolama alanı işaret eder. Dönüş değerini cast türü void, kullanım dışında bir tür için bir işaretçi almak için.

## <a name="remarks"></a>Açıklamalar

**_aligned_offset_realloc_dbg** bir hata ayıklama sürümü [_aligned_offset_realloc](aligned-offset-realloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_aligned_offset_realloc_dbg** yapılan bir çağrı için sınırlı **_aligned_offset_realloc**. Her ikisi de **_aligned_offset_realloc** ve **_aligned_offset_realloc_dbg** bir bellek bloğu temel yığınındaki yeniden tahsis ancak **_aligned_offset_realloc_dbg** düzenler birkaç hata ayıklama özelliği: belirli ayırma türleri izlemek için bir blok türü parametresi sızıntıları için test etmek için blok kullanıcı kısmının her iki tarafında arabellekleri ve *filename*/*linenumber*  ayırma isteklerini kökenini belirlemek için bilgi.

Gibi [_aligned_offset_malloc](aligned-offset-malloc.md), **_aligned_offset_realloc_dbg** yapısı içinde bir uzaklığındaki hizalanacak yapısı sağlar.

**_realloc_dbg** istenen biraz daha fazla alan ile belirtilen bellek bloğu yeniden ayırır *newSize*. *newSize* büyük ya da özgün olarak ayrılmış bellek bloğu boyutu küçüktür olabilir. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Yeniden ayırma özgün bellek bloğu yığınındaki farklı bir konuma taşıyarak, aynı zamanda bellek bloğu boyutunu değiştirme neden olabilir. Bellek bloğu taşınırsa, özgün bloğun içeriğinin üzerine yazılır.

Bu işlev ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya istenen boyutu büyük olursa **_HEAP_MAXREQ**. Hakkında daha fazla bilgi için **errno**, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_realloc_dbg** parametrelerini doğrular. Varsa *hizalama* 2'in üssü değil veya *uzaklık* büyük veya eşit *boyutu* ve sıfır dışında bu işlev geçersiz parametre işleyicisi anlatıldığıgibiçağırır.[ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_realloc_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
