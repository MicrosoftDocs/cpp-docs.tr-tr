---
title: _aligned_offset_recalloc_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_offset_recalloc_dbg
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
- aligned_offset_recalloc_dbg
- _aligned_offset_recalloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_recalloc_dbg function
- _aligned_offset_recalloc_dbg function
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02b920832d462c88c13d68525a1a4038cf6720f1
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="alignedoffsetrecallocdbg"></a>_aligned_offset_recalloc_dbg

İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) ve bellek 0 (yalnızca hata ayıklama sürümü) başlatır.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_offset_recalloc_dbg(
   void *memblock,
   size_t num,
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

*Sayı*<br/>
Öğe sayısı.

*Boyutu*<br/>
Her öğenin bayt cinsinden uzunluğu.

*Hizalama*<br/>
Hizalama değeri bir tamsayı güç 2 olmalıdır.

*uzaklık*<br/>
Hizalama zorlamak için bellek ayırma içine uzaklığı.

*Dosya adı*<br/>
Realloc işlemi istenen kaynak dosyasının adını işaretçi veya **NULL**.

*LineNumber*<br/>
Satır numarası realloc işlemi istenen burada kaynak dosyasında veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_offset_recalloc_dbg** bırakılan (ve muhtemelen taşınan) bellek bloğuna void işaretçi döndürür. Dönüş değeri **NULL** boyutu sıfır ise ve arabellek bağımsız değişken değil **NULL**, veya blok verilen boyuta genişletmek için yeterli kullanılabilir bellek değilse. İlk durumda, özgün blok serbest bırakılır. İkinci durumda, özgün blok değiştirilmez. Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun hizalanacak garanti bir depolama alanı işaret eder. Dönüş değerini cast türü void, kullanım dışında bir tür için bir işaretçi almak için.

## <a name="remarks"></a>Açıklamalar

**_aligned_offset_realloc_dbg** bir hata ayıklama sürümü [_aligned_offset_recalloc](aligned-offset-recalloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_aligned_offset_recalloc_dbg** yapılan bir çağrı için sınırlı **_aligned_offset_recalloc**. Her ikisi de **_aligned_offset_recalloc** ve **_aligned_offset_recalloc_dbg** bir bellek bloğu temel yığınındaki yeniden tahsis ancak **_aligned_offset_recalloc_dbg** düzenler birkaç hata ayıklama özelliği: belirli ayırma türleri izlemek için bir blok türü parametresi sızıntıları için test etmek için blok kullanıcı kısmının her iki tarafında arabellekleri ve *filename*/*linenumber*  ayırma isteklerini kökenini belirlemek için bilgi.

**_aligned_offset_realloc_dbg** istenen biraz daha fazla alan ile belirtilen bellek bloğu yeniden ayırır *newSize*. *newSize* büyük ya da özgün olarak ayrılmış bellek bloğu boyutu küçüktür olabilir. Ek alanı, hata ayıklama bellek blokları bağlantı ve uygulama ile hata ayıklama üst bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Yeniden ayırma özgün bellek bloğu yığınındaki farklı bir konuma taşıyarak, aynı zamanda bellek bloğu boyutunu değiştirme neden olabilir. Bellek bloğu taşınırsa, özgün bloğun içeriğinin üzerine yazılır.

Bu işlev ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya istenen boyuta (*numarası* * *boyutu* ) daha büyük olan **_HEAP_MAXREQ**. Hakkında daha fazla bilgi için **errno**, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_recalloc_dbg** parametrelerini doğrular. Varsa *hizalama* 2'in üssü değil veya *uzaklık* daha büyük veya eşit istenen boyuta ve sıfır olmayan, açıklandığı gibi bu işlevi geçersiz parametre işleyicisi çağırır [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türlerini ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemede çağırma arasındaki farklar hakkında daha fazla bilgi için bkz: [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_recalloc_dbg**|\<malloc.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
