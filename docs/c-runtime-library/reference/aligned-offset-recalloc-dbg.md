---
description: 'Hakkında daha fazla bilgi edinin: _aligned_offset_recalloc_dbg'
title: _aligned_offset_recalloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_offset_recalloc_dbg
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
- aligned_offset_recalloc_dbg
- _aligned_offset_recalloc_dbg
helpviewer_keywords:
- aligned_offset_recalloc_dbg function
- _aligned_offset_recalloc_dbg function
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
ms.openlocfilehash: 35857ef25a01170343f8d35b2c3532db573cc688
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312529"
---
# <a name="_aligned_offset_recalloc_dbg"></a>_aligned_offset_recalloc_dbg

[_Aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) ile ayrılmış bir bellek bloğunun boyutunu değiştirir ve belleği 0 olarak başlatır (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_offset_recalloc_dbg(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Geçerli bellek bloğu işaretçisi.

*sayısından*<br/>
Öğe sayısı.

*boyutla*<br/>
Her öğenin bayt cinsinden uzunluğu.

*hizalar*<br/>
2 ' nin tam sayı üssü olması gereken hizalama değeri.

*konumu*<br/>
Hizalamayı zorlamak için bellek ayırmaya olan fark.

*filename*<br/>
Realloc işlemini veya **null değerini** isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyadaki realloc işleminin istendiği veya **null** olduğu satır numarası.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_offset_recalloc_dbg** , yeniden ayrılan (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Boyut sıfır ise ve arabellek bağımsız değişkeni **null** olmadığında veya bloğu belirtilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa dönüş değeri **null** olur. İlk durumda, orijinal blok serbest bırakılır. İkinci durumda, orijinal blok değiştirilmez. Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. Void dışında bir türe işaretçi almak için, dönüş değerinde bir tür dönüştürme kullanın.

## <a name="remarks"></a>Açıklamalar

**_aligned_offset_realloc_dbg** , [_aligned_offset_recalloc](aligned-offset-recalloc.md) işlevinin hata ayıklama sürümüdür. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, her **_aligned_offset_recalloc_dbg** çağrısı **_aligned_offset_recalloc** çağrısına düşürülür. Hem **_aligned_offset_recalloc** hem de **_aligned_offset_recalloc_dbg** , temel yığında bir bellek bloğunu yeniden tahsis ediyor, ancak **_aligned_offset_recalloc_dbg** birkaç hata ayıklama özelliğini karşılar: sızıntı için test etmek üzere bloğun Kullanıcı bölümünün her iki tarafında bulunan arabellekler ve  / ayırma isteklerinin kaynağını belirlemede dosya adı *onayın* bilgileri. Bir blok türü parametresiyle belirli ayırma türlerini izlemek, hizalanmış ayırmalar için desteklenen bir hata ayıklama özelliği değildir. Hizalanmış ayırmalar _NORMAL_BLOCK blok türü olarak görüntülenir.

**_aligned_offset_realloc_dbg** Istenen *newSize* göre biraz daha fazla alanla belirtilen bellek bloğunu yeniden konumlandırır. *newSize* , başlangıçta ayrılan bellek bloğunun boyutundan daha büyük veya daha küçük olabilir. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Yeniden ayırma, özgün bellek bloğunun yığında farklı bir konuma taşınmasına ve bellek bloğunun boyutunu değiştirmeye neden olabilecek. Bellek bloğu taşınırsa, orijinal bloğunun içeriğinin üzerine yazılır.

Bu işlev, bellek ayırma başarısız olursa veya istenen boyut (*sayı* boyutu) _HEAP_MAXREQ fazlaysa, **errno** ' dan **ENOMEM** olarak ayarlanır  *   . **Errno** hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_recalloc_dbg** parametrelerini doğrular. *Hizalama* 2 ' nin üssü değilse veya *Aralık* istenen boyuttan büyük veya bu değere eşitse, bu işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **null** değerini döndürür ve **errno** 'ı **EINVAL** olarak ayarlar.

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_recalloc_dbg**|\<malloc.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri hizalaması](../../c-runtime-library/data-alignment.md)<br/>
