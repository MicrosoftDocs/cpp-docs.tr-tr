---
description: 'Hakkında daha fazla bilgi edinin: _recalloc_dbg'
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
ms.openlocfilehash: abad8ff877a78bc589a48da689766322ad8438de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254267"
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

*Blok türü*<br/>
İstenen bellek bloğu türü: **_CLIENT_BLOCK** veya **_NORMAL_BLOCK**.

Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details).

*filename*<br/>
Ayırma işlemi veya **null** için istenen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyasındaki ayırma işleminin istendiği veya **null** olduğu satır numarası.

*Filename* ve *onayın* parametreleri yalnızca **_recalloc_dbg** açıkça çağrıldığında veya [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) Önişlemci sabiti tanımlandığında kullanılabilir.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla tamamlandığında, bu işlev yeniden ayrılan bellek bloğunun Kullanıcı kısmına bir işaretçi döndürür, yeni işleyici işlevini çağırır veya **null** değerini döndürür. Dönüş davranışının ayrıntılı bir açıklaması için aşağıdaki açıklamalar bölümüne bakın. Yeni işleyici işlevinin nasıl kullanıldığı hakkında daha fazla bilgi için [_recalloc](recalloc.md) işlevine bakın.

## <a name="remarks"></a>Açıklamalar

**_recalloc_dbg** , [_recalloc](recalloc.md) işlevinin hata ayıklama sürümüdür. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, her **_recalloc_dbg** çağrısı **_recalloc** çağrısına düşürülür. Hem **_recalloc** hem de **_recalloc_dbg** , temel yığında bir bellek bloğunu yeniden tahsis ediyor, ancak **_recalloc_dbg** bazı hata ayıklama özelliklerini karşılar: sızıntı için test etmek üzere bloğun Kullanıcı bölümünün her iki tarafındaki arabellekler, belirli ayırma türlerini izlemek için bir blok türü parametresi ve ayırma isteklerinin kaynağını belirlemede *dosya adı* / *onayın* bilgileri.

**_recalloc_dbg** , belirtilen bellek bloğunu,  *  başlangıçta ayrılan bellek bloğunun boyutundan daha büyük veya daha az olabilen istenen boyuttan (sayı *boyutu*) biraz daha fazla alan ile yeniden konumlandırır. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Yeniden ayırma, özgün bellek bloğunun yığında farklı bir konuma taşınmasına ve bellek bloğunun boyutunu değiştirmeye neden olabilecek. Bloğun Kullanıcı bölümü, 0xCD değeri ile doldurulmuştur ve üzerine yazma arabelleklerinin her biri 0xFD ile doldurulur.

bellek ayırma başarısız olursa, **_recalloc_dbg** **errno** , **ENOMEM** olarak ayarlanır; **EINVAL** , gereken bellek miktarı (daha önce bahsedilen ek yük dahil) **_HEAP_MAXREQ** aşarsa döndürülür. Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_recalloc_dbg**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
