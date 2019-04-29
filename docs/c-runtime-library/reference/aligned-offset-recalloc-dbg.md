---
title: _aligned_offset_recalloc_dbg
ms.date: 11/04/2016
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
helpviewer_keywords:
- aligned_offset_recalloc_dbg function
- _aligned_offset_recalloc_dbg function
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
ms.openlocfilehash: 671635e6cdc0f3f9bcd140de40500ed49beb4a8f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348035"
---
# <a name="alignedoffsetrecallocdbg"></a>_aligned_offset_recalloc_dbg

İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) ve belleği 0 (yalnızca hata ayıklama sürümü) başlatır.

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
Hizalama değeri 2'in tam sayı üssü olması gerekir.

*uzaklık*<br/>
Hizalama zorlamak için bellek ayırma olan uzaklık.

*Dosya adı*<br/>
İstenen realloc işlem kaynak dosyasının adını işaretçisi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada realloc işlemi burada istendi veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_offset_recalloc_dbg** yeniden (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Dönüş değeri **NULL** boyutu sıfırsa ve arabellek bağımsız değişken değil **NULL**, ya da blok verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa. Bu durumda, özgün blok serbest bırakılır. İkinci durumda, özgün blok değiştirilmez. Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun şekilde hizalanması garanti bir depolama alanına işaret eder. Bir işaretçi bir türü void, kullanımı dışında bir tür dönüş değerini almak için.

## <a name="remarks"></a>Açıklamalar

**_aligned_offset_realloc_dbg** bir hata ayıklama sürümü [_aligned_offset_recalloc](aligned-offset-recalloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_aligned_offset_recalloc_dbg** çağrısı azaltılır **_aligned_offset_recalloc**. Her ikisi de **_aligned_offset_recalloc** ve **_aligned_offset_recalloc_dbg** taban yığının bellek bloğunda yeniden tahsis ancak **_aligned_offset_recalloc_dbg** barındırır birçok hata ayıklama özellikleri: arabellek bloğu için sızıntılara, test etmek için kullanıcı bölümünü her iki tarafındaki ve *filename*/*linenumber* kökenini belirlemek için bilgi ayırma isteklerini. Bir blok türü parametresiyle belirli ayırma türleri izleme hizalanmış ayırma desteklenen hata ayıklama özelliği değil. Hizalanmış ayırma _NORMAL_BLOCK bloğu türü olarak görünür.

**_aligned_offset_realloc_dbg** istenen biraz daha fazla alan ile belirtilen bellek bloğu yeniden tahsis ederse *newSize*. *newSize* büyük ya da ilk olarak ayrılan bellek blok boyutundan küçük olabilir. Ek alan, hata ayıklama bellek bloklarını bağlantı ve uygulama ile hata ayıklama üstbilgi bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Tahsisat, orijinal bellek bloğunun yığınındaki farklı bir konuma taşımak, yanı sıra bellek blok boyutu değiştirme neden olabilir. Bellek bloğu taşınırsa, özgün blok içeriği üzerine yazılır.

Bu işlev ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya istenen boyut (*numarası* * *boyutu* ) daha büyük **_HEAP_MAXREQ**. Hakkında daha fazla bilgi için **errno**, bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_recalloc_dbg** kendi parametrelerini doğrular. Varsa *hizalama* 2'in kuvveti değil veya *uzaklığı* büyükse veya istenen boyutuna eşit ve sıfır değilse, bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevi döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemesinde çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_recalloc_dbg**|\<malloc.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
