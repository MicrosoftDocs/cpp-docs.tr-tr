---
title: _aligned_free
ms.date: 11/04/2016
api_name:
- _aligned_free
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
ms.openlocfilehash: 44556d3f044a567f4903ef14a4b2a9b353af02ff
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943977"
---
# <a name="_aligned_free"></a>_aligned_free

[_Aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md)ile ayrılmış bir bellek bloğunu serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```C
void _aligned_free (
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
`_aligned_malloc` Or`_aligned_offset_malloc` işlevine döndürülen bellek bloğunun işaretçisi.

## <a name="remarks"></a>Açıklamalar

**_aligned_free** işaretlenir `__declspec(noalias)`, yani işlevin genel değişkenleri değiştirmeyeceği garanti edilir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md).

Bu işlev, diğer _hizalanmış CRT işlevlerinin aksine parametresini doğrulamaz. Eğer *MEMBLOCK* null bir işaretçisiyse, bu işlev yalnızca bir eylem gerçekleştirir. Değişiklik `errno` yapmaz ve geçersiz parametre işleyicisini çağırmaz. _Aligned işlevleri daha önce bellek bloğu ayrılamadı kullanmayan nedeniyle işlevi içinde bir hata oluşursa veya bazı öngörülemeyen calamity nedeniyle bellek hizalanması gerçekleşir, işlev bir hata ayıklama raporu oluşturur [_RPT, _RPTF, _RPTW, _Rptfw makrosu](rpt-rptf-rptw-rptfw-macros.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_free**|\<malloc. h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için bkz. [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)