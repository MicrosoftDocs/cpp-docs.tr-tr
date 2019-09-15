---
title: _aligned_malloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_malloc_dbg
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
- _aligned_malloc_dbg
- aligned_malloc_dbg
helpviewer_keywords:
- aligned_malloc_dbg function
- _aligned_malloc_dbg function
ms.assetid: fb0429c3-685d-4826-9075-2515c5bdc5c6
ms.openlocfilehash: 3db61d494ea94c9ccbf2844c9f47df66dad87ff7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939892"
---
# <a name="_aligned_malloc_dbg"></a>_aligned_malloc_dbg

Bir hata ayıklama üst bilgisi ve üzerine yazma arabellekleri (yalnızca hata ayıklama sürümü) için ek alanla belirtilen hizalama sınırında bellek ayırır.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_malloc_dbg(
    size_t size,
    size_t alignment,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
İstenen bellek ayırmasının boyutu.

*hizalar*<br/>
2 ' nin tam sayı üssü olması gereken hizalama değeri.

*kısaltın*<br/>
Ayırma işlemini veya NULL değerini isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Ayırma işleminin istendiği veya NULL olduğu kaynak dosyadaki satır numarası.

## <a name="return-value"></a>Dönüş Değeri

İşlem başarısız olursa, ayrılan veya NULL olan bellek bloğunun işaretçisi.

## <a name="remarks"></a>Açıklamalar

**_aligned_malloc_dbg** , [_aligned_malloc](aligned-malloc.md) işlevinin bir hata ayıklama sürümüdür. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_aligned_malloc_dbg** öğesine yapılan her çağrı, öğesine `_aligned_malloc`yapılan çağrıya düşürülür. Hem `_aligned_malloc` hem de **_aligned_malloc_dbg** , temel yığında bir bellek bloğu ayırır, ancak **_aligned_malloc_dbg** birçok hata ayıklama özelliği sunar: sızıntıların Kullanıcı bölümünün her iki tarafında da sızıntı ve *dosya adı* ayırma isteklerinin kaynağını tespit etmek için *onayın bilgileri.* / Bir blok türü parametresiyle belirli ayırma türlerini izlemek, hizalanmış ayırmalar için desteklenen bir hata ayıklama özelliği değildir. Hizalanmış ayırmalar, _NORMAL_BLOCK blok türü olarak görünür.

**_aligned_malloc_dbg** bellek bloğunu istenen *boyuttan*biraz daha fazla alanla ayırır. Hata ayıklama bellek bloklarını bağlamak ve uygulamanın hata ayıklama üstbilgi bilgilerini ve üzerine yazma arabelleğini sağlamak için ek alan, hata ayıklama yığın Yöneticisi tarafından kullanılır. Blok ayrıldığında, bloğun Kullanıcı bölümü, 0xCD değeri ile doldurulur ve üzerine yazma arabelleklerinin her biri 0xFD ile doldurulur.

**_aligned_malloc_dbg** , `errno` bir `ENOMEM` bellek ayırma başarısız olursa veya gerekli bellek miktarı (daha önce bahsedilen ek yük dahil) ile aşarsa `_HEAP_MAXREQ`olarak ayarlanır. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_malloc_dbg** kendi parametrelerini doğrular. *Hizalama* 2 ' nin üssü veya *boyutu* sıfır değilse, bu işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev null döndürür ve öğesini olarak `errno` `EINVAL`ayarlar.

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_malloc_dbg**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)