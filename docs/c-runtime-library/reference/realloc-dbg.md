---
title: _realloc_dbg
ms.date: 11/04/2016
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
helpviewer_keywords:
- reallocating memory blocks
- realloc_dbg function
- memory blocks, reallocating
- memory, reallocating
- _realloc_dbg function
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
ms.openlocfilehash: 9b30dfd6fbae9a4831ff53e7896aeb995657da03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357752"
---
# <a name="reallocdbg"></a>_realloc_dbg

Belirtilen bir yığında bellek bloğu, taşıma ve/veya yeniden boyutlandırma (yalnızca hata ayıklama sürümü) blok tarafından yeniden ayırır.

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

*userData*<br/>
Daha önce ayrılmış bellek bloğuna işaretçi.

*newSize*<br/>
Boyut (bayt) reallocated bloğunun istedi.

*blockType*<br/>
Reallocated blok türü istendi: **_clıent_block** veya **_NORMAL_BLOCK**.

*Dosya adı*<br/>
İstenen kaynak dosyasının adını işaretçisine **realloc** işlemi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada burada **realloc** işlemi istendi veya **NULL**.

*Filename* ve *linenumber* parametreleri yalnızca kullanılabilir olduğunda **_realloc_dbg** açıkça çağrılan veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) ön işlemci sabiti tanımlanmış.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev bir işaretçi bırakılan bellek bloğu kullanıcı bölümünü döndürür, yeni işleyici işlevi çağırır veya döndürür **NULL**. Dönüş davranışı eksiksiz bir açıklaması için aşağıdaki Açıklamalar bölümüne bakın. Yeni işleyici işlevi nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [realloc](realloc.md) işlevi.

## <a name="remarks"></a>Açıklamalar

**_realloc_dbg** bir hata ayıklama sürümü [realloc](realloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_realloc_dbg** çağrısı azaltılır **realloc**. Her ikisi de **realloc** ve **_realloc_dbg** taban yığının bellek bloğunda yeniden tahsis ancak **_realloc_dbg** birkaç hata ayıklama özellikleri kapsar: her iki tarafındaki arabellekler Blok için sızıntılara, belirli bir ayırma türleri izlemek için bir blok türü parametresi test etmek için kullanıcı bölümünü ve *filename*/*linenumber* kökenini belirlemek için bilgi ayırma isteklerini.

**_realloc_dbg** istenen biraz daha fazla alan ile belirtilen bellek bloğu yeniden tahsis ederse *newSize*. *newSize* büyük ya da ilk olarak ayrılan bellek blok boyutundan küçük olabilir. Ek alan, hata ayıklama bellek bloklarını bağlantı ve uygulama ile hata ayıklama üstbilgi bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Tahsisat, orijinal bellek bloğunun yığınındaki farklı bir konuma taşımak, yanı sıra bellek blok boyutu değiştirme neden olabilir. Bellek bloğu taşınırsa, özgün blok içeriği üzerine yazılır.

**_realloc_dbg** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa veya (daha önce bahsedilen ek yük dahil) gerekli bellek miktarını aşıyorsa **_HEAP_ MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemesinde çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_realloc_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Örnekte bakın [_msize_dbg](msize-dbg.md) konu.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
