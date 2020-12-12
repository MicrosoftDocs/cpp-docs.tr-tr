---
description: 'Hakkında daha fazla bilgi edinin: _set_controlfp'
title: _set_controlfp
ms.date: 04/05/2018
api_name:
- _set_controlfp
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_controlfp
- _set_controlfp
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
ms.openlocfilehash: 44316cb4114d06ced1b3d67a261bc8d3ceb1aee6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288873"
---
# <a name="_set_controlfp"></a>_set_controlfp

Kayan nokta denetim sözcüğünü ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
void __cdecl _set_controlfp(
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>Parametreler

*newControl*<br/>
Yeni denetim-sözcük bit değerleri.

*maske*<br/>
Ayarlanacak yeni denetim-sözcük bitleri için maske.

## <a name="return-value"></a>Dönüş Değeri

Yok.

## <a name="remarks"></a>Açıklamalar

**_Set_controlfp** işlevi **_control87** benzerdir, ancak yalnızca kayan nokta denetim sözcüğünü *newControl* olarak ayarlar. Değerlerde bulunan bitler, kayan nokta denetim durumunu gösterir. Kayan nokta denetim durumu, programın kayan nokta matematik paketindeki duyarlık, yuvarlama ve sonsuzluk modlarını değiştirmesine izin verir. Ayrıca, **_set_controlfp** kullanarak kayan nokta özel durumlarını maskeleyebilir veya maskeleyebilirsiniz. Daha fazla bilgi için bkz. [_control87, _controlfp, \_ _control87_2](control87-controlfp-control87-2.md).

Ortak dil çalışma zamanı yalnızca varsayılan kayan nokta duyarlığını desteklediğinden, bu işlev [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ile derlenirken kullanım dışıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|Uyumluluk|
|-------------|---------------------|-------------------|
|**_set_controlfp**|\<float.h>|yalnızca x86 işlemcisi|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
