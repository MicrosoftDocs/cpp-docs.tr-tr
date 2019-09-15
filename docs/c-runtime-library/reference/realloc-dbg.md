---
title: _realloc_dbg
ms.date: 11/04/2016
api_name:
- _realloc_dbg
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 58d12ed6f4b013996f3f59cba1b146b823adbee6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949509"
---
# <a name="_realloc_dbg"></a>_realloc_dbg

Bloğu taşıyarak ve/veya yeniden boyutlandırarak (yalnızca hata ayıklama sürümü) yığında belirtilen bellek bloğunu yeniden konumlandırır.

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
Önceden ayrılmış bellek bloğuna yönelik işaretçi.

*newSize*<br/>
Yeniden ayrılan blok için istenen boyut (bayt).

*blockType*<br/>
Yeniden ayrılan blok için istenen tür: **_Client_block** veya **_NORMAL_BLOCK**.

*kısaltın*<br/>
**Realloc** Işlemini veya **null değerini**isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyadaki **realloc** işleminin Istendiği veya **null**olduğu satır numarası.

*Filename* ve *onayın* parametreleri yalnızca **_realloc_dbg** açıkça çağrıldığında veya [_crtdbg_map_ayırma](../../c-runtime-library/crtdbg-map-alloc.md) Önişlemci sabiti tanımlandığında kullanılabilir.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev yeniden ayrılan bellek bloğunun Kullanıcı kısmına bir işaretçi döndürür, yeni işleyici işlevini çağırır veya **null**değerini döndürür. Dönüş davranışının ayrıntılı bir açıklaması için aşağıdaki açıklamalar bölümüne bakın. Yeni işleyici işlevinin nasıl kullanıldığı hakkında daha fazla bilgi için [realloc](realloc.md) işlevine bakın.

## <a name="remarks"></a>Açıklamalar

**_realloc_dbg** , [realloc](realloc.md) işlevinin bir hata ayıklama sürümüdür. [_Debug](../../c-runtime-library/debug.md) tanımlanmadığında, **_realloc_dbg** öğesine yapılan her çağrı, **realloc**çağrısına düşürülür. Hem **realloc** hem de **_realloc_dbg** , temel yığında bir bellek bloğunu yeniden ayırır, ancak **_realloc_dbg** çeşitli hata ayıklama özelliklerini karşılar: sızıntıların test olması için bloğun Kullanıcı bölümünün her iki tarafında da bir blok türü parametresi belirli ayırma türlerini izleyin ve ayırma isteklerinin kaynağını öğrenmek için *dosya adı*/*linumarası* bilgilerini izleyin.

**_realloc_dbg** Istenen *newSize*göre biraz daha fazla alanla belirtilen bellek bloğunu yeniden konumlandırır. *newSize* , başlangıçta ayrılan bellek bloğunun boyutundan daha büyük veya daha küçük olabilir. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Yeniden ayırma, özgün bellek bloğunun yığında farklı bir konuma taşınmasına ve bellek bloğunun boyutunu değiştirmeye neden olabilecek. Bellek bloğu taşınırsa, orijinal bloğunun içeriğinin üzerine yazılır.

**_realloc_dbg** bir bellek ayırma başarısız olursa ya da gerekli bellek miktarı (daha önce bahsedilen ek yük dahil) **_Heap_maxreq**değerini aşarsa, **errno** değerini **ENOMEM** olarak ayarlar. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_realloc_dbg**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

[_Msize_dbg](msize-dbg.md) konusunun örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
