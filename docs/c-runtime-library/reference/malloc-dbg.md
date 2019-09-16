---
title: _malloc_dbg
ms.date: 11/04/2016
api_name:
- _malloc_dbg
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
- malloc_dbg
- _malloc_dbg
helpviewer_keywords:
- malloc_dbg function
- memory allocation
- _malloc_dbg function
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
ms.openlocfilehash: cfaaaec17dc8546c937045f93027e9609981bd93
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952872"
---
# <a name="_malloc_dbg"></a>_malloc_dbg

Bir hata ayıklama üst bilgisi ve üzerine yazma arabellekleri (yalnızca hata ayıklama sürümü) için ek alana sahip yığında bir bellek bloğu ayırır.

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

*boyutla*<br/>
Bellek bloğunun istenen boyutu (bayt).

*blockType*<br/>
Bellek bloğunun istenen türü: **_Client_block** veya **_NORMAL_BLOCK**.

*kısaltın*<br/>
Ayırma işlemini veya **null değerini**isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Ayırma işleminin istendiği veya **null**olduğu kaynak dosyadaki satır numarası.

*Filename* ve *onayın* parametreleri yalnızca **_malloc_dbg** açıkça çağrıldığında veya [_crtdbg_map_ayırma](../../c-runtime-library/crtdbg-map-alloc.md) Önişlemci sabiti tanımlandığında kullanılabilir.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev ayrılan bellek bloğunun Kullanıcı kısmına bir işaretçi döndürür, yeni işleyici işlevini çağırır veya **null**değerini döndürür. Dönüş davranışının ayrıntılı bir açıklaması için aşağıdaki açıklamalar bölümüne bakın. Yeni işleyici işlevinin nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [malloc](malloc.md) işlevi.

## <a name="remarks"></a>Açıklamalar

**_malloc_dbg** , [malloc](malloc.md) işlevinin hata ayıklama sürümüdür. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_malloc_dbg** öğesine yapılan her çağrı, **malloc**çağrısına düşürülür. Hem **malloc** hem de **_malloc_dbg** , temel yığında bir bellek bloğu ayırır, ancak **_malloc_dbg** birçok hata ayıklama özelliği sunar: sızıntıların test olması için bloğun Kullanıcı bölümünün her iki tarafında da arabellekler, izlenecek bir blok türü parametresi ayırma isteklerinin kaynağını tespit etmek için belirli ayırma türleri ve *dosya adı*/*onayın* bilgileri.

**_malloc_dbg** bellek bloğunu istenen *boyuttan*biraz daha fazla alanla ayırır. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Blok ayrıldığında, bloğun Kullanıcı bölümü, 0xCD değeri ile doldurulur ve üzerine yazma arabelleklerinin her biri 0xFD ile doldurulur.

**_malloc_dbg** , bir bellek ayırma başarısız olursa veya gerekli bellek miktarı (daha önce bahsedilen ek yük dahil) **_Heap_maxreq**değerini aşarsa, **errno** değerini **ENOMEM** olarak ayarlar. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_malloc_dbg**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

**_Malloc_dbg**öğesinin nasıl kullanılacağına ilişkin bir örnek için bkz. [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[malloc](malloc.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
