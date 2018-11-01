---
title: _recalloc_dbg
ms.date: 11/04/2016
apiname:
- _recalloc_dbg
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
- recalloc_dbg
- _recalloc_dbg
helpviewer_keywords:
- _recalloc_dbg function
- recalloc_dbg function
ms.assetid: 43c3e9b2-be6d-4508-9b0f-3220c8a47ca3
ms.openlocfilehash: e2782492d3338b5b548db0153b6123fb82ff5e72
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653277"
---
# <a name="recallocdbg"></a>_recalloc_dbg

Bir dizi yeniden ayırır ve öğeleri 0 (yalnızca hata ayıklama sürümü) başlatır.

## <a name="syntax"></a>Sözdizimi

```C
void *_recalloc_dbg(
   void *userData,
   size_t num,
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*userData*<br/>
Daha önce ayrılmış bellek bloğuna işaretçi.

*Sayı*<br/>
İstenen bellek bloğu sayısı.

*Boyutu*<br/>
İstenen boyut (bayt) her bellek bloğu.

*blockType*<br/>
İstenen bellek bloğu türü: **_clıent_block** veya **_NORMAL_BLOCK**.

Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details).

*Dosya adı*<br/>
Ayırma işlemi istenen kaynak dosyasının adı işaretçi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada ayırma işlemi burada istendi veya **NULL**.

*Filename* ve *linenumber* parametreleri yalnızca kullanılabilir olduğunda **_recalloc_dbg** açıkça çağrılan veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) ön işlemci sabiti tanımlanmış.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev bir işaretçi bırakılan bellek bloğu kullanıcı bölümünü döndürür, yeni işleyici işlevi çağırır veya döndürür **NULL**. Dönüş davranışı eksiksiz bir açıklaması için aşağıdaki Açıklamalar bölümüne bakın. Yeni işleyici işlevi nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [_recalloc](recalloc.md) işlevi.

## <a name="remarks"></a>Açıklamalar

**_recalloc_dbg** bir hata ayıklama sürümü [_recalloc](recalloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_recalloc_dbg** çağrısı azaltılır **_recalloc**. Her ikisi de **_recalloc** ve **_recalloc_dbg** taban yığının bellek bloğunda yeniden tahsis ancak **_recalloc_dbg** birkaç hata ayıklama özellikleri kapsar: iki tarafındaki arabellekler sızıntıları için test edilecek blok kullanıcı bölümünü bir blok spesifik ayırma türleri izlemek için parametre türü ve *filename*/*linenumber* belirlemek için bilgi ayırma isteği başlangıcı.

**_recalloc_dbg** istenen boyuttan biraz daha fazla alan ile belirtilen bellek bloğu yeniden tahsis ederse (*numarası* * *boyutu*) olabilen büyük veya boyutundan küçük ilk olarak ayrılan bellek bloğu. Ek alan, hata ayıklama bellek bloklarını bağlantı ve uygulama ile hata ayıklama üstbilgi bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Tahsisat, orijinal bellek bloğunun yığınındaki farklı bir konuma taşımak, yanı sıra bellek blok boyutu değiştirme neden olabilir. Blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve 0xFD ile doldurulmuş her üzerine yaz arabellek.

**_recalloc_dbg** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa; **EINVAL** (daha önce bahsedilen ek yük dahil) ihtiyaç duyulan bellek miktarı aşması durumunda döndürülen **_HEAP_MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemesinde çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_recalloc_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
