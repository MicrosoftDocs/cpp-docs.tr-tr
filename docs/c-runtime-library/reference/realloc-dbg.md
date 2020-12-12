---
description: 'Hakkında daha fazla bilgi edinin: _realloc_dbg'
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
ms.openlocfilehash: 1a211ac886de34d6b251622dec2f4500bb290d14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274794"
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

*Blok türü*<br/>
Yeniden ayrılan blok için istenen tür: **_CLIENT_BLOCK** veya **_NORMAL_BLOCK**.

*filename*<br/>
**Realloc** Işlemini veya **null değerini** isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyadaki **realloc** işleminin Istendiği veya **null** olduğu satır numarası.

*Filename* ve *onayın* parametreleri yalnızca **_realloc_dbg** açıkça çağrıldığında veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) Önişlemci sabiti tanımlandığında kullanılabilir.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev yeniden ayrılan bellek bloğunun Kullanıcı kısmına bir işaretçi döndürür, yeni işleyici işlevini çağırır veya **null** değerini döndürür. Dönüş davranışının ayrıntılı bir açıklaması için aşağıdaki açıklamalar bölümüne bakın. Yeni işleyici işlevinin nasıl kullanıldığı hakkında daha fazla bilgi için [realloc](realloc.md) işlevine bakın.

## <a name="remarks"></a>Açıklamalar

**_realloc_dbg** , [realloc](realloc.md) işlevinin bir hata ayıklama sürümüdür. [_DEBUG](../../c-runtime-library/debug.md) tanımlanmadığı zaman, her **_realloc_dbg** çağrısı **realloc** çağrısına düşürülür. Hem **realloc** hem de **_realloc_dbg** , temel yığında bir bellek bloğunu yeniden ayırır, ancak **_realloc_dbg** , bazı hata ayıklama özelliklerini (örneğin, belirli ayırma türlerini izlemek için bir blok türü parametresi ve ayırma isteklerinin kaynağını belirlemede *dosya adı* / *onayın* bilgileri) sağlar.

**_realloc_dbg** Istenen *newSize* göre biraz daha fazla alanla belirtilen bellek bloğunu yeniden konumlandırır. *newSize* , başlangıçta ayrılan bellek bloğunun boyutundan daha büyük veya daha küçük olabilir. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Yeniden ayırma, özgün bellek bloğunun yığında farklı bir konuma taşınmasına ve bellek bloğunun boyutunu değiştirmeye neden olabilecek. Bellek bloğu taşınırsa, orijinal bloğunun içeriğinin üzerine yazılır.

bir bellek ayırma başarısız olursa veya gerekli bellek miktarı (daha önce bahsedilen ek yük dahil) **_HEAP_MAXREQ** aştığında, **_realloc_dbg** **errno** değerini **ENOMEM** olarak ayarlar. Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_realloc_dbg**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

[_Msize_dbg](msize-dbg.md) konusundaki örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
