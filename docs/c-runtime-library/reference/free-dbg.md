---
description: 'Hakkında daha fazla bilgi edinin: _free_dbg'
title: _free_dbg
ms.date: 11/04/2016
api_name:
- _free_dbg
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
- _free_dbg
- free_dbg
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
ms.openlocfilehash: 4baba591349c197b301b0dcd11b1998adfc7a971
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314041"
---
# <a name="_free_dbg"></a>_free_dbg

Yığında bir bellek bloğunu serbest bırakır (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void _free_dbg(
   void *userData,
   int blockType
);
```

### <a name="parameters"></a>Parametreler

*userData*<br/>
Serbest bırakmak için ayrılan bellek bloğunun işaretçisi.

*Blok türü*<br/>
Boşaltılacak ayrılmış bellek bloğunun türü: **_CLIENT_BLOCK**, **_NORMAL_BLOCK** veya **_IGNORE_BLOCK**.

## <a name="remarks"></a>Açıklamalar

**_Free_dbg** işlevi, [ücretsiz](free.md) işlevin hata ayıklama sürümüdür. [_DEBUG](../../c-runtime-library/debug.md) tanımlanmadığı zaman, **_free_dbg** her bir çağrı **ücretsiz** çağrıya düşürülür. Hem **ücretsiz** hem de **_free_dbg** temel yığında bir bellek bloğu boşaltın, ancak **_free_dbg** iki hata ayıklama özelliğini de karşılar: düşük bellek koşullarının benzetimini yapmak için yığın bağlantılı listesinde serbest bırakılan blokları ve belirli ayırma türlerini serbest bırakmak için bir blok türü parametresini serbest bırakma özelliği.

**_free_dbg** , ücretsiz işlemi gerçekleştirmeden önce belirtilen tüm dosyalar ve blok konumları üzerinde bir geçerlilik denetimi gerçekleştirir. Uygulamanın bu bilgileri sağlaması beklenmez. Bir bellek bloğu serbest bırakıldığında, hata ayıklama yığın Yöneticisi kullanıcı bölümünün her iki tarafındaki arabelleklerin bütünlüğünü otomatik olarak denetler ve üzerine yazma oluştuysa bir hata raporu yayınlar. [_CrtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağının **_CRTDBG_DELAY_FREE_MEM_DF** bit alanı ayarlandıysa, serbest bırakılan blok 0xDD değeri ile doldurulur, **_free_block** blok türü atanır ve yığının bağlı bellek blokları listesinde tutulur.

Belleği boşaltmaya yönelik bir hata oluşursa, **errno** , işletim sisteminden hata doğasından bilgi olarak ayarlanır. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma bloğu türleri ve bunların nasıl kullanıldığı hakkında bilgi için bkz. [hata ayıklama yığınındaki blok türleri](/visualstudio/debugger/crt-debug-heap-details). Bir uygulamanın hata ayıklama sürümünde standart yığın işlevi çağırma ve hata ayıklama sürümü arasındaki farklar hakkında daha fazla bilgi için bkz. [yığın ayırma Işlevlerinin hata ayıklama sürümleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_free_dbg**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

**_Free_dbg** kullanmanın bir örneği için bkz. [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
