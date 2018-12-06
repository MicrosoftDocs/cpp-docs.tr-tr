---
title: _aligned_realloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_realloc_dbg
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
- aligned_realloc_dbg
- _aligned_realloc_dbg
helpviewer_keywords:
- _aligned_realloc_dbg function
- aligned_realloc_dbg function
ms.assetid: 8aede920-991e-44cd-867f-83dc2165db47
ms.openlocfilehash: 136edf6b5c95149302920af0c8a8dc9c07458e3b
ms.sourcegitcommit: beeb77b2976e997debc55b1af35024cc62e62799
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2018
ms.locfileid: "52977777"
---
# <a name="alignedreallocdbg"></a>_aligned_realloc_dbg

İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_realloc_dbg(
   void *memblock,
   size_t size,
   size_t alignment,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Geçerli bellek bloğu işaretçisi.

*Boyutu*<br/>
İstenen bellek ayırmasının boyutu.

*Hizalama*<br/>
Hizalama değeri 2'in tam sayı üssü olması gerekir.

*Dosya adı*<br/>
İstenen kaynak dosyasının adını işaretçisine **realloc** işlemi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada burada **realloc** işlemi istendi veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_realloc_dbg** yeniden (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Dönüş değeri **NULL** boyutu sıfırsa ve arabellek bağımsız değişken değil **NULL**, ya da blok verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa. Bu durumda, özgün blok serbest bırakılır. İkinci, özgün blok değiştirilmez. Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun şekilde hizalanması garanti bir depolama alanına işaret eder. Bir işaretçi bir türü void, kullanımı dışında bir tür dönüş değerini almak için.

Bu belleği yeniden tahsis ve bir blok hizalamasını değiştirmek için bir hatadır.

## <a name="remarks"></a>Açıklamalar

**_aligned_realloc_dbg** bir hata ayıklama sürümü [_aligned_realloc](aligned-realloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_aligned_realloc_dbg** çağrısı azaltılır **_aligned_realloc**. Her ikisi de **_aligned_realloc** ve **_aligned_realloc_dbg** taban yığının bellek bloğunda yeniden tahsis ancak **_aligned_realloc_dbg** birkaç hata ayıklama özellikleri barındırır : arabellek bloğu için sızıntılara, test etmek için kullanıcı bölümünü her iki tarafındaki ve *filename*/*linenumber* ayırma isteklerini kökenini belirlemek için bilgi. Bir blok türü parametresiyle belirli ayırma türleri izleme hizalanmış ayırma desteklenen hata ayıklama özelliği değil. Hizalanmış ayırma _NORMAL_BLOCK bloğu türü olarak görünür.

**_aligned_realloc_dbg** istenen biraz daha fazla alan ile belirtilen bellek bloğu yeniden tahsis ederse *newSize*. *newSize* büyük ya da ilk olarak ayrılan bellek blok boyutundan küçük olabilir. Ek alan, hata ayıklama bellek bloklarını bağlantı ve uygulama ile hata ayıklama üstbilgi bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Tahsisat, orijinal bellek bloğunun yığınındaki farklı bir konuma taşımak, yanı sıra bellek blok boyutu değiştirme neden olabilir. Bellek bloğu taşınırsa, özgün blok içeriği üzerine yazılır.

**_aligned_realloc_dbg** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa veya (daha önce bahsedilen ek yük dahil) gerekli bellek miktarını aşıyorsa **_ HEAP_MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Ayrıca, **_aligned_realloc_dbg** kendi parametrelerini doğrular. Varsa *hizalama* güç değil açıklandığı gibi bu işlev 2, geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevi döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemesinde çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_realloc_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
