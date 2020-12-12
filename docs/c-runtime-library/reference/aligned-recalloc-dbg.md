---
description: 'Hakkında daha fazla bilgi edinin: _aligned_recalloc_dbg'
title: _aligned_recalloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_recalloc_dbg
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
- _aligned_recalloc_dbg
- aligned_recalloc_dbg
helpviewer_keywords:
- aligned_recalloc_dbg function
- _aligned_recalloc_dbg function
ms.assetid: 55c3c27e-561c-4d6b-9bf9-1e34cc556e4b
ms.openlocfilehash: bfe0450f4a1b63f7451ff148b183c94f59002efc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135739"
---
# <a name="_aligned_recalloc_dbg"></a>_aligned_recalloc_dbg

[_Aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) ile ayrılmış bir bellek bloğunun boyutunu değiştirir ve belleği 0 olarak başlatır (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_recalloc_dbg(
   void * memblock,
   size_t num,
   size_t size,
   size_t alignment,
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
Her öğenin bayt cinsinden boyutu.

*hizalar*<br/>
2 ' nin tam sayı üssü olması gereken hizalama değeri.

*filename*<br/>
Ayırma işlemi veya **null** için istenen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyasındaki ayırma işleminin istendiği veya **null** olduğu satır numarası.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_recalloc_dbg** , yeniden ayrılan (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Boyut sıfır ise ve arabellek bağımsız değişkeni **null** olmadığında veya bloğu belirtilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa dönüş değeri **null** olur. İlk durumda, orijinal blok serbest bırakılır. İkinci durumda, orijinal blok değiştirilmez. Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. Void dışında bir türe işaretçi almak için, dönüş değerinde bir tür dönüştürme kullanın.

Belleği yeniden ayırmak ve bir bloğun hizalamasını değiştirmek hatadır.

## <a name="remarks"></a>Açıklamalar

**_aligned_recalloc_dbg** , [_aligned_recalloc](aligned-recalloc.md) işlevinin hata ayıklama sürümüdür. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, her **_aligned_recalloc_dbg** çağrısı **_aligned_recalloc** çağrısına düşürülür. Hem **_aligned_recalloc** hem de **_aligned_recalloc_dbg** , temel yığında bir bellek bloğunu yeniden tahsis ediyor, ancak **_aligned_recalloc_dbg** birkaç hata ayıklama özelliğini karşılar: sızıntı için test etmek üzere bloğun Kullanıcı bölümünün her iki tarafında bulunan arabellekler ve  / ayırma isteklerinin kaynağını belirlemede dosya adı *onayın* bilgileri. Bir blok türü parametresiyle belirli ayırma türlerini izlemek, hizalanmış ayırmalar için desteklenen bir hata ayıklama özelliği değildir. Hizalanmış ayırmalar _NORMAL_BLOCK blok türü olarak görüntülenir.

**_aligned_recalloc_dbg** , belirtilen bellek bloğunu,  *  başlangıçta ayrılan bellek bloğunun boyutundan daha büyük veya daha az olabilen istenen boyuttan (sayı *boyutu*) biraz daha fazla alan ile yeniden konumlandırır. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Yeniden ayırma, özgün bellek bloğunun yığında farklı bir konuma taşınmasına ve bellek bloğunun boyutunu değiştirmeye neden olabilecek. Bloğun Kullanıcı bölümü, 0xCD değeri ile doldurulmuştur ve üzerine yazma arabellekleri 0xFD ile doldurulur.

bellek ayırma başarısız olursa, **_aligned_recalloc_dbg** **errno** , **ENOMEM** olarak ayarlanır; **EINVAL** , gereken bellek miktarı (daha önce bahsedilen ek yük dahil) **_HEAP_MAXREQ** aşarsa döndürülür. Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Ayrıca, **_aligned_recalloc_dbg** parametrelerini doğrular. *Hizalama* 2 ' nin üssü değilse, bu Işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **null** değerini döndürür ve **errno** 'ı **EINVAL** olarak ayarlar.

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_recalloc_dbg**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
