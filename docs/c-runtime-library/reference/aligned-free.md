---
title: _aligned_free
ms.date: 11/04/2016
apiname:
- _aligned_free
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- aligned_free
- _aligned_free
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
ms.openlocfilehash: e2d1dc1172d1cd0d31f8daa8125bd052252393c0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432170"
---
# <a name="alignedfree"></a>_aligned_free

İle ayrılmış olan bellek bloğunu serbest bırakır [_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md).

## <a name="syntax"></a>Sözdizimi

```C
void _aligned_free (
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
İçin döndürülen bellek bloğuna işaretçi `_aligned_malloc` veya `_aligned_offset_malloc` işlevi.

## <a name="remarks"></a>Açıklamalar

**_aligned_free** işaretlenmiş `__declspec(noalias)`, işlevin genel değişkenleri garanti anlamına gelir. Daha fazla bilgi için [noalias](../../cpp/noalias.md).

Bu işlev bir _aligned CRT işlevlerinin aksine, parametresinin doğrulamaz. Varsa *memblock* bir NULL işaretçiyse, bu işlev yalnızca eylem gerçekleştirir. Değiştirme `errno` ve geçersiz parametre işleyicisi çağırma kullanılamaz. _Aligned işlevleri daha önce bellek bloğu ayrılamadı kullanmayan nedeniyle işlevi içinde bir hata oluşursa veya bazı öngörülemeyen calamity nedeniyle bellek hizalanması gerçekleşir, işlev bir hata ayıklama raporu oluşturur [_RPT, _RPTF, _RPTW, _Rptfw makrosu](rpt-rptf-rptw-rptfw-macros.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_free**|\<malloc.h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)