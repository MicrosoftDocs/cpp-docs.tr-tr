---
title: _aligned_realloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_realloc_dbg
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
- aligned_realloc_dbg
- _aligned_realloc_dbg
helpviewer_keywords:
- _aligned_realloc_dbg function
- aligned_realloc_dbg function
ms.assetid: 8aede920-991e-44cd-867f-83dc2165db47
ms.openlocfilehash: aa0af73aced2e8f337582d58d8efac650d244dee
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939733"
---
# <a name="_aligned_realloc_dbg"></a>_aligned_realloc_dbg

[_Aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) (yalnızca hata ayıklama sürümü) ile ayrılmış bir bellek bloğunun boyutunu değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_realloc_dbg(
   void *memblock,
   size_t size,
   size_t alignment,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Geçerli bellek bloğu işaretçisi.

*boyutla*<br/>
İstenen bellek ayırmasının boyutu.

*hizalar*<br/>
2 ' nin tam sayı üssü olması gereken hizalama değeri.

*kısaltın*<br/>
**Realloc** Işlemini veya **null değerini**isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyadaki **realloc** işleminin Istendiği veya **null**olduğu satır numarası.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_realloc_dbg** , yeniden ayrılan (ve muhtemelen taşınan) bellek bloğuna void bir işaretçi döndürür. Boyut sıfır ise ve arabellek bağımsız değişkeni **null**olmadığında veya bloğu belirtilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa dönüş değeri **null** olur. İlk durumda, orijinal blok serbest bırakılır. İkincisi, orijinal blok değiştirilmez. Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. Void dışında bir türe işaretçi almak için, dönüş değerinde bir tür dönüştürme kullanın.

Belleği yeniden ayırmak ve bir bloğun hizalamasını değiştirmek hatadır.

## <a name="remarks"></a>Açıklamalar

**_aligned_realloc_dbg** , [_aligned_realloc](aligned-realloc.md) işlevinin bir hata ayıklama sürümüdür. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_aligned_realloc_dbg** öğesine yapılan her çağrı, **_aligned_realloc**çağrısına düşürülür. **_Aligned_realloc** ve **_aligned_realloc_dbg** , temel yığında bir bellek bloğunu yeniden ayırır, ancak **_aligned_realloc_dbg** birçok hata ayıklama özelliğini karşılar: sızıntıların test olması için bloğun Kullanıcı bölümünün her iki tarafındaki arabellekler ve ayırma isteklerinin kaynağını tespit etmek için *dosya adı*/*onayın* bilgisini. Bir blok türü parametresiyle belirli ayırma türlerini izlemek, hizalanmış ayırmalar için desteklenen bir hata ayıklama özelliği değildir. Hizalanmış ayırmalar, _NORMAL_BLOCK blok türü olarak görünür.

**_aligned_realloc_dbg** belirtilen bellek bloğunu Istenen *newSize*göre biraz daha fazla alanla yeniden konumlandırır. *newSize* , başlangıçta ayrılan bellek bloğunun boyutundan daha büyük veya daha küçük olabilir. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Yeniden ayırma, özgün bellek bloğunun yığında farklı bir konuma taşınmasına ve bellek bloğunun boyutunu değiştirmeye neden olabilecek. Bellek bloğu taşınırsa, orijinal bloğunun içeriğinin üzerine yazılır.

**_aligned_realloc_dbg** , bir bellek ayırma başarısız olursa veya gerekli bellek miktarı (daha önce bahsedilen ek yük dahil) **_Heap_maxreq**değerini aşarsa, **errno** değerini **ENOMEM** olarak ayarlar. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Ayrıca, **_aligned_realloc_dbg** kendi parametrelerini doğrular. *Hizalama* 2 ' nin üssü değilse, bu Işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **null** değerini döndürür ve **errno** 'ı **EINVAL**olarak ayarlar.

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_realloc_dbg**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
