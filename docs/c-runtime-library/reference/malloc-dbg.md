---
title: _malloc_dbg
ms.date: 11/04/2016
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
helpviewer_keywords:
- malloc_dbg function
- memory allocation
- _malloc_dbg function
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
ms.openlocfilehash: 64fb40028d9130278077f3d05dd1e25914dba212
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156947"
---
# <a name="mallocdbg"></a>_malloc_dbg

Hata ayıklama üst bilgisi için bir ek alana sahip yığında bellek bloğu ayırır ve arabellek (yalnızca hata ayıklama sürümü) üzerine yazılır.

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
Ayırma işlemi istenen kaynak dosyasının adını işaretçisi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada ayırma işlemi burada istendi veya **NULL**.

*Filename* ve *linenumber* parametreleri yalnızca kullanılabilir olduğunda **_malloc_dbg** açıkça çağrılan veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)ön işlemci sabiti tanımlanmış.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev için ayrılmış bellek bloğu kullanıcı bölümünü bir işaretçi döndürür, yeni işleyici işlevi çağırır veya döndürür **NULL**. Dönüş davranışı eksiksiz bir açıklaması için aşağıdaki Açıklamalar bölümüne bakın. Yeni işleyici işlevi nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [malloc](malloc.md) işlevi.

## <a name="remarks"></a>Açıklamalar

**_malloc_dbg** bir hata ayıklama sürümü [malloc](malloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_malloc_dbg** çağrısı azaltılır **malloc**. Her ikisi de **malloc** ve **_malloc_dbg** taban yığının bellek bloğu ayrılamadı ancak **_malloc_dbg** birkaç hata ayıklama özellikleri sunar: kullanıcı her iki tarafındaki arabellekler Blok için sızıntılara, belirli bir ayırma türleri izlemek için bir blok türü parametresi test etmek için bir kısmı ve *filename*/*linenumber* kökenini belirlemek için bilgi ayırma isteklerini.

**_malloc_dbg** ile biraz daha fazla alan istenen bellek bloğu ayırır *boyutu*. Ek alan, hata ayıklama bellek bloklarını bağlantı ve uygulama ile hata ayıklama üstbilgi bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Blok atandığında, blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve 0xFD ile doldurulmuş her üzerine yaz arabellek.

**_malloc_dbg** ayarlar **errno** için **ENOMEM** bir bellek ayırma başarısız olursa veya (daha önce bahsedilen ek yük dahil) gerekli bellek miktarını aşıyorsa **_HEAP_ MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemesinde çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_malloc_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek **_malloc_dbg**, bkz: [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[malloc](malloc.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
