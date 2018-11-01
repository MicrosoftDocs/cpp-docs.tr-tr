---
title: _aligned_malloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_malloc_dbg
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
- _aligned_malloc_dbg
- aligned_malloc_dbg
helpviewer_keywords:
- aligned_malloc_dbg function
- _aligned_malloc_dbg function
ms.assetid: fb0429c3-685d-4826-9075-2515c5bdc5c6
ms.openlocfilehash: 4fc6789e5fecda38678052c7e805728a49219bc9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631880"
---
# <a name="alignedmallocdbg"></a>_aligned_malloc_dbg

Hata ayıklama üst bilgisi için ek alana sahip bir belirtilen hizalama sınırındaki belleği ayırır ve arabellek (yalnızca hata ayıklama sürümü) üzerine yazılır.

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

*Boyutu*<br/>
İstenen bellek ayırmasının boyutu.

*Hizalama*<br/>
Hizalama değeri 2'in tam sayı üssü olması gerekir.

*Dosya adı*<br/>
Ayırma işlemi veya NULL istenen kaynak dosyasının adı için işaretçi.

*LineNumber*<br/>
Satır numarası kaynak dosyada ayırma işlemi burada istendi veya NULL.

## <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek bloğuna işaretçi veya işlem başarısız olursa NULL.

## <a name="remarks"></a>Açıklamalar

**_aligned_malloc_dbg** bir hata ayıklama sürümü [_aligned_malloc](aligned-malloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_aligned_malloc_dbg** çağrısı azaltılır `_aligned_malloc`. Her ikisi de `_aligned_malloc` ve **_aligned_malloc_dbg** taban yığının bellek bloğu ayrılamadı ancak **_aligned_malloc_dbg** birkaç hata ayıklama özellikleri sunar: her iki tarafında bir kullanıcı bölümünü arabellekler Blok için sızıntılara, test etmek ve *filename*/*linenumber* ayırma isteklerini kökenini belirlemek için bilgi.

**_aligned_malloc_dbg** ile biraz daha fazla alan istenen bellek bloğu ayırır *boyutu*. Ek alan, hata ayıklama bellek bloklarını bağlantı ve uygulama ile hata ayıklama üstbilgi bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Blok atandığında, blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve 0xFD ile doldurulmuş her üzerine yaz arabellek.

**_aligned_malloc_dbg** ayarlar `errno` için `ENOMEM` bir bellek ayırma başarısız olursa veya (daha önce bahsedilen ek yük dahil) gerekli bellek miktarını aşıyorsa `_HEAP_MAXREQ`. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_malloc_dbg** kendi parametrelerini doğrular. Varsa *hizalama* 2'in kuvveti değil veya *boyutu* sıfırsa bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlev dönüşleri NULL ve kümeleri yürütülmesine izin veriliyorsa `errno` için `EINVAL`.

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemesinde çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_malloc_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)