---
title: _free_dbg
ms.date: 11/04/2016
apiname:
- _free_dbg
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
- _free_dbg
- free_dbg
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
ms.openlocfilehash: 5a0024101e4f5a74f1573b271d444b27738db8e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442256"
---
# <a name="freedbg"></a>_free_dbg

(Yalnızca hata ayıklama sürümü) yığında bellek bloğunu serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```C
void _free_dbg(
   void *userData,
   int blockType
);
```

### <a name="parameters"></a>Parametreler

*userData*<br/>
Serbest bırakılacak ayrılan bellek bloğuna işaretçi.

*blockType*<br/>
Serbest bırakılacak ayrılmış bellek bloğu türü: **_clıent_block**, **_NORMAL_BLOCK**, veya **_ıgnore_block**.

## <a name="remarks"></a>Açıklamalar

**_Free_dbg** işlev, hata ayıklama sürümü [ücretsiz](free.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_free_dbg** çağrısı azaltılır **ücretsiz**. Her ikisi de **ücretsiz** ve **_free_dbg** temel yığında bir bellek öbeğini serbest ancak **_free_dbg** iki hata ayıklama özellikleri kapsar: yığının serbest bırakılan tutma imkanıyla engeller yetersiz bellek koşullarına ve belirli ayırma türleri boşaltmak için bir blok türü parametresi benzetimini yapmak için bağlantılı liste.

**_free_dbg** ücretsiz işlemi gerçekleştirmeden önce belirtilen tüm dosyaları ve blok konumları üzerinde bir geçerlilik denetimi gerçekleştirir. Uygulama, bu bilgiyi sağlamak için beklenmiyor. Bir bellek bloğunu serbest bırakılır, hata ayıklama yığını Yöneticisi otomatik olarak kullanıcı bölümünün iki tarafındaki arabelleklerin bütünlüğünü denetler ve üzerine yazma olduysa bir hata raporu yayınlar. Varsa **_CRTDBG_DELAY_FREE_MEM_DF** bit alanı [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağı ayarlandığında, atanan değer ile 0xDD, serbest bırakılan blok doldurulur **_FREE_BLOCK** blok türü, ve bellek blokları yığının bağlantılı listesinde saklanır.

Bellek serbest bırakma hata oluşması durumunda **errno** bilgilerle hata işletim sisteminden yapısı üzerinde ayarlanır. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemesinde çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_free_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek **_free_dbg**, bkz: [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
