---
title: _recalloc_dbg
ms.date: 11/04/2016
api_name:
- _recalloc_dbg
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
- recalloc_dbg
- _recalloc_dbg
helpviewer_keywords:
- _recalloc_dbg function
- recalloc_dbg function
ms.assetid: 43c3e9b2-be6d-4508-9b0f-3220c8a47ca3
ms.openlocfilehash: 6274e749b2c4e6f64c7c7f82f8764dcf5ba642fe
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949471"
---
# <a name="_recalloc_dbg"></a>_recalloc_dbg

Bir diziyi yeniden konumlandırır ve öğelerini 0 olarak başlatır (yalnızca hata ayıklama sürümü).

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
Önceden ayrılmış bellek bloğuna yönelik işaretçi.

*sayısından*<br/>
İstenen bellek bloğu sayısı.

*boyutla*<br/>
Her bellek bloğunun istenen boyutu (bayt).

*blockType*<br/>
İstenen bellek bloğu türü: **_Client_block** veya **_NORMAL_BLOCK**.

Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

*kısaltın*<br/>
Ayırma işlemi veya **null**için istenen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyasındaki ayırma işleminin istendiği veya **null**olduğu satır numarası.

*Filename* ve *onayın* parametreleri yalnızca **_yeniden hesaplama loc_dbg** açıkça çağrıldığında veya [_crtdbg_map_ayırma](../../c-runtime-library/crtdbg-map-alloc.md) Önişlemci sabiti tanımlandığında kullanılabilir.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev yeniden ayrılan bellek bloğunun Kullanıcı kısmına bir işaretçi döndürür, yeni işleyici işlevini çağırır veya **null**değerini döndürür. Dönüş davranışının ayrıntılı bir açıklaması için aşağıdaki açıklamalar bölümüne bakın. Yeni işleyici işlevinin nasıl kullanıldığı hakkında daha fazla bilgi için, bkz. [_yeniden hesapla Loc](recalloc.md) işlevi.

## <a name="remarks"></a>Açıklamalar

**_yeniden hesapla loc_dbg** , [_yeniden hesapla](recalloc.md) işlevinin bir hata ayıklama sürümüdür. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_yeniden hesapla loc_dbg** öğesine yapılan her çağrı, **_yeniden hesapla**öğesine yapılan çağrıya düşürülür. Hem **_yeniden** hesapla hem de **_yeniden hesapla loc_dbg** , temel yığında bir bellek bloğunu yeniden tahsis ediyor, ancak **_yeniden hesapla loc_dbg** çeşitli hata ayıklama özelliklerini karşılar: sızıntıların her iki tarafında da belirli ayırma türlerini izlemek ve ayırma isteklerinin kaynağını belirleyebilmek için *dosya adı*/*linumarası* bilgilerini izlemek için.

**_yeniden hesapla** , belirtilen bellek bloğunu istenen boyuttan (*sayı* * *boyutu*) biraz daha fazla alan ile, başlangıçta ayrılan bellek bloğunun boyutundan büyük veya küçük olabilir. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Yeniden ayırma, özgün bellek bloğunun yığında farklı bir konuma taşınmasına ve bellek bloğunun boyutunu değiştirmeye neden olabilecek. Bloğun Kullanıcı bölümü, 0xCD değeri ile doldurulmuştur ve üzerine yazma arabelleklerinin her biri 0xFD ile doldurulur.

bir bellek ayırma başarısız olursa, **_yeniden hesapla loc_dbg** , **errmem** çağrısı yapar; **EINVAL** , gereken bellek miktarı (daha önce bahsedilen ek yük dahil) **_Heap_maxreq**değerini aşarsa döndürülür. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_recalloc_dbg**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
