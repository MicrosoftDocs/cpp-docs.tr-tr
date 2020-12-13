---
description: 'Hakkında daha fazla bilgi edinin: _aligned_free_dbg'
title: _aligned_free_dbg
ms.date: 11/04/2016
api_name:
- _aligned_free_dbg
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
- _aligned_free_dbg
- aligned_free_dbg
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
ms.openlocfilehash: 7320cb800cf42f7b641ed1d60afaf5d2144990e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335688"
---
# <a name="_aligned_free_dbg"></a>_aligned_free_dbg

[_Aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) ayrılmış bir bellek bloğunu serbest bırakır (yalnızca Hata Ayıkla).

## <a name="syntax"></a>Sözdizimi

```C
void _aligned_free_dbg(
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
[_Aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md) işlevine döndürülen bellek bloğunun işaretçisi.

## <a name="remarks"></a>Açıklamalar

**_Aligned_free_dbg** işlevi, [_aligned_free](aligned-free.md) işlevinin hata ayıklama sürümüdür. [_DEBUG](../../c-runtime-library/debug.md) tanımlanmadığı zaman, her **_aligned_free_dbg** çağrısı öğesine yapılan çağrıya düşürülür `_aligned_free` . Hem hem de `_aligned_free` **_aligned_free_dbg** temel yığında bir bellek bloğu boşaltın, ancak **_aligned_free_dbg** bir hata ayıklama özelliğine sahiptir: düşük bellek koşullarına benzetmek için yığının bağlantılı listesinde serbest bırakılan blokları saklama özelliği.

**_aligned_free_dbg** , ücretsiz işlemi gerçekleştirmeden önce belirtilen tüm dosyalar ve blok konumları üzerinde bir geçerlilik denetimi gerçekleştirir. Uygulamanın bu bilgileri sağlaması beklenmez. Bir bellek bloğu serbest bırakıldığında, hata ayıklama yığın Yöneticisi kullanıcı bölümünün her iki tarafındaki arabelleklerin bütünlüğünü otomatik olarak denetler ve üzerine yazma oluştuysa bir hata raporu yayınlar. [_CrtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağının _CRTDBG_DELAY_FREE_MEM_DF bit alanı ayarlandıysa, serbest bırakılan blok 0xDD değeri ile doldurulur, _free_block blok türü atanır ve yığının bağlı bellek blokları listesinde tutulur.

Belleği serbest bırakma bölümünde bir hata oluşursa, `errno` hata doğasından işletim sisteminden bilgi olarak ayarlanır. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_free_dbg**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)
