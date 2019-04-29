---
title: _aligned_msize_dbg
ms.date: 11/04/2016
apiname:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
ms.openlocfilehash: 054f7b88f93eef37a9a88fbb7895452f7c158716
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62342041"
---
# <a name="alignedmsizedbg"></a>_aligned_msize_dbg

(Yalnızca hata ayıklama sürümü) yığında ayrılan bir bellek bloğu boyutu döndürür.

## <a name="syntax"></a>Sözdizimi

```C
size_t _aligned_msize_dbg(
   void *memblock,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Bellek bloğuna işaretçi.

*Hizalama*<br/>
Hizalama değeri 2'in tam sayı üssü olması gerekir.

*uzaklık*<br/>
Hizalama zorlamak için bellek ayırma olan uzaklık.

## <a name="return-value"></a>Dönüş Değeri

Boyut (bayt cinsinden), işaretsiz bir tamsayı olarak döndürür.

## <a name="remarks"></a>Açıklamalar

*Hizalama* ve *uzaklığı* değerleri blok ayrılan işleve geçirilen değerlerin aynı olması gerekir.

**_aligned_msize_dbg** bir hata ayıklama sürümü [_aligned_msize](aligned-msize.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_aligned_msize_dbg** çağrısı azaltılır **_aligned_msize**. Her ikisi de **_aligned_msize** ve **_aligned_msize_dbg** taban yığının bellek bloğunda boyutunu hesaplamak ancak **_aligned_msize_dbg** hata ayıklama özelliğini ekler: Bu, döndürülen boyutunda bellek bloğu kullanıcı bölümünü her iki tarafındaki arabelleklerin içerir.

Bu işlev, parametresini doğrular. Varsa *memblock* null bir işaretçiyse veya *hizalama* 2 ' nin kuvveti değil **_msize** açıklandığı gibi geçersiz parametre işleyicisini çağırır [parametre doğrulama ](../../c-runtime-library/parameter-validation.md). Hatanın işlenip, işlev ayarlar **errno** için **EINVAL** ve -1 döndürür.

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details). Standart yığın işlevi ve hata ayıklama sürümü, bir uygulamanın hata ayıklama derlemesinde çağırma arasındaki farklar hakkında daha fazla bilgi için bkz. [hata ayıklama sürümleri, yığın ayırma işlevleri](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_msize_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
