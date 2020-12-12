---
description: 'Hakkında daha fazla bilgi edinin: _aligned_free'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 2efbda028f1a5c23ce8a6f02da543a114534985d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303732"
---
# <a name="_aligned_free"></a>_aligned_free

[_Aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md)ayrılmış bir bellek bloğunu serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```C
void _aligned_free (
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Or işlevine döndürülen bellek bloğunun işaretçisi `_aligned_malloc` `_aligned_offset_malloc` .

## <a name="remarks"></a>Açıklamalar

**_aligned_free** işaretlenir `__declspec(noalias)` , yani işlevin genel değişkenleri değiştirmeyeceği garanti edilir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md).

Bu işlev, diğer _aligned CRT işlevlerinin aksine parametresini doğrulamaz. Eğer *MEMBLOCK* null bir işaretçisiyse, bu işlev yalnızca bir eylem gerçekleştirir. Değişiklik yapmaz `errno` ve geçersiz parametre işleyicisini çağırmaz. İşlevde bir hata oluşursa, daha önce bellek bloğunu ayırmak için _aligned işlevleri veya bazı öngörülemeyen Calamity nedeniyle bir hatalı hizalanmış bellek hatası oluşursa, işlev [_rpt, _rptf, _RPTW _rptfw makrolarını](rpt-rptf-rptw-rptfw-macros.md)kullanarak bir hata ayıklama raporu oluşturur.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_free**|\<malloc.h>|

## <a name="example"></a>Örnek

Daha fazla bilgi için bkz. [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri hizalaması](../../c-runtime-library/data-alignment.md)
