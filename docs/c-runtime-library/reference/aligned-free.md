---
title: _aligned_free
ms.date: 4/2/2020
api_name:
- _aligned_free
- _o__aligned_free
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- aligned_free
- _aligned_free
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
ms.openlocfilehash: a6e5f0dcd0bbea436ecdad7abb1fd6fc948f80dc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350709"
---
# <a name="_aligned_free"></a>_aligned_free

[_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md)ile ayrılan bellek bloğunu boşaltıyor.

## <a name="syntax"></a>Sözdizimi

```C
void _aligned_free (
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Veya `_aligned_malloc` `_aligned_offset_malloc` işleve döndürülen bellek bloğuna işaretçi.

## <a name="remarks"></a>Açıklamalar

**_aligned_free** işaretlenir, `__declspec(noalias)`yani işlev in global değişkenleri değiştirmemesi garanti edilir. Daha fazla bilgi için [noalias'a](../../cpp/noalias.md)bakın.

Bu işlev, diğer _aligned CRT işlevlerinin aksine parametresini doğrulamaz. *Memblock* bir NULL işaretçisiyse, bu işlev yalnızca hiçbir eylem gerçekleştirmez. Değişmez `errno` ve geçersiz parametre işleyicisini çağırmaz. Bellek bloğunu ayırmak için daha önce _aligned işlevlerinin kullanılmaması nedeniyle işlevde bir hata oluşursa veya öngörülemeyen bir felaket nedeniyle belleğin yanlış hizalanması oluşursa, işlev [_RPT, _RPTF, _RPTW _RPTFW Makrolardan](rpt-rptf-rptw-rptfw-macros.md)bir hata ayıklama raporu oluşturur.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_free**|\<malloc.h>|

## <a name="example"></a>Örnek

Daha fazla bilgi için [_aligned_malloc.](aligned-malloc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)
