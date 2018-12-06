---
title: _aligned_recalloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_recalloc_dbg
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
- _aligned_recalloc_dbg
- aligned_recalloc_dbg
helpviewer_keywords:
- aligned_recalloc_dbg function
- _aligned_recalloc_dbg function
ms.assetid: 55c3c27e-561c-4d6b-9bf9-1e34cc556e4b
ms.openlocfilehash: c0f0cacc5efa5e63cbe05b481f922b35742e3924
ms.sourcegitcommit: beeb77b2976e997debc55b1af35024cc62e62799
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2018
ms.locfileid: "52977790"
---
# <a name="alignedrecallocdbg"></a>_aligned_recalloc_dbg

İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) ve belleği 0 (yalnızca hata ayıklama sürümü) başlatır.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_recalloc_dbg(
   void * memblock,
   size_t num,
   size_t size,
   size_t alignment,
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
Her öğenin bayt cinsinden boyutu.

*Hizalama*<br/>
Hizalama değeri 2'in tam sayı üssü olması gerekir.

*Dosya adı*<br/>
Ayırma işlemi istenen kaynak dosyasının adı işaretçi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada ayırma işlemi burada istendi veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_recalloc_dbg** yeniden (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Dönüş değeri **NULL** boyutu sıfırsa ve arabellek bağımsız değişken değil **NULL**, ya da blok verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa. Bu durumda, özgün blok serbest bırakılır. İkinci durumda, özgün blok değiştirilmez. Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun şekilde hizalanması garanti bir depolama alanına işaret eder. Bir işaretçi bir türü void, kullanımı dışında bir tür dönüş değerini almak için.

Bu belleği yeniden tahsis ve bir blok hizalamasını değiştirmek için bir hatadır.

## <a name="remarks"></a>Açıklamalar

**_aligned_recalloc_dbg** bir hata ayıklama sürümü [_aligned_recalloc](aligned-recalloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_aligned_recalloc_dbg** çağrısı azaltılır **_aligned_recalloc**. Her ikisi de **_aligned_recalloc** ve **_aligned_recalloc_dbg** taban yığının bellek bloğunda yeniden tahsis ancak **_aligned_recalloc_dbg** birkaç hata ayıklama barındırır Özellikler: arabellek bloğu için sızıntılara, test etmek için kullanıcı bölümünü her iki tarafındaki ve *filename*/*linenumber* ayırma kökenini belirlemek için bilgi istek sayısı. Bir blok türü parametresiyle belirli ayırma türleri izleme hizalanmış ayırma desteklenen hata ayıklama özelliği değil. Hizalanmış ayırma _NORMAL_BLOCK bloğu türü olarak görünür.

**_aligned_recalloc_dbg** istenen boyuttan biraz daha fazla alan ile belirtilen bellek bloğu yeniden tahsis ederse (*numarası* * *boyutu*) olabilen büyük veya küçük daha ilk olarak ayrılan bellek blok boyutu. Ek alan, hata ayıklama bellek bloklarını bağlantı ve uygulama ile hata ayıklama üstbilgi bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Tahsisat, orijinal bellek bloğunun yığınındaki farklı bir konuma taşımak, yanı sıra bellek blok boyutu değiştirme neden olabilir. Blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve üzerine yazma arabelleği 0xFD ile doludur.

**_aligned_recalloc_dbg** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa; **EINVAL** (daha önce bahsedilen ek yük dahil) ihtiyaç duyulan bellek miktarı aşması durumunda döndürülen **_HEAP_MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Ayrıca, **_aligned_recalloc_dbg** kendi parametrelerini doğrular. Varsa *hizalama* güç değil açıklandığı gibi bu işlev 2, geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevi döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemesinde çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_recalloc_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
