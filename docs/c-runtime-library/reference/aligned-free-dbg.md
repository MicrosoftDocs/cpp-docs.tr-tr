---
title: _aligned_free_dbg
ms.date: 11/04/2016
apiname:
- _aligned_free_dbg
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
- _aligned_free_dbg
- aligned_free_dbg
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
ms.openlocfilehash: f51b9b9573ab2e23a0a60979c55a33d2e5cff747
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341905"
---
# <a name="alignedfreedbg"></a>_aligned_free_dbg

İle ayrılmış olan bellek bloğunu serbest bırakır [_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) (yalnızca hata ayıklama).

## <a name="syntax"></a>Sözdizimi

```C
void _aligned_free_dbg(
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
İçin döndürülen bellek bloğuna işaretçi [_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) işlevi.

## <a name="remarks"></a>Açıklamalar

**_Aligned_free_dbg** işlev, hata ayıklama sürümü [_aligned_free](aligned-free.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_aligned_free_dbg** çağrısı azaltılır `_aligned_free`. Her ikisi de `_aligned_free` ve **_aligned_free_dbg** temel yığında bir bellek öbeğini serbest ancak **_aligned_free_dbg** hata ayıklama özelliği karşılar: yığının bağlantılı listesinde için serbest bırakılan tutma imkanıyla engeller yetersiz bellek durumları benzetimini yapar.

**_aligned_free_dbg** ücretsiz işlemi gerçekleştirmeden önce belirtilen tüm dosyaları ve blok konumları üzerinde bir geçerlilik denetimi gerçekleştirir. Uygulama, bu bilgiyi sağlamak için beklenmiyor. Bir bellek bloğunu serbest bırakılır, hata ayıklama yığını Yöneticisi otomatik olarak kullanıcı bölümünün iki tarafındaki arabelleklerin bütünlüğünü denetler ve üzerine yazma olduysa bir hata raporu yayınlar. _CRTDBG_DELAY_FREE_MEM_DF bit alanı, [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağı ayarlandığında, serbest bırakılan blok 0xDD değeriyle doldurulur, _FREE_BLOCK bloğu türü atanmış ve bellek blokları yığının bağlantılı listesinde saklanır.

Bellek serbest bırakma hata oluşması durumunda `errno` bilgilerle hata işletim sisteminden yapısı üzerinde ayarlanır. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemesinde çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_free_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)