---
title: _set_controlfp
ms.date: 04/05/2018
apiname:
- _set_controlfp
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_controlfp
- _set_controlfp
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
ms.openlocfilehash: 1187502f09849d7ca4d8e595c237cfa511d00c6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499061"
---
# <a name="setcontrolfp"></a>_set_controlfp

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
Yeni Denetim sözcüğü bit değerleri.

*Maskesi*<br/>
Ayarlanacak yeni denetim sözcüğü bitleri için maske.

## <a name="return-value"></a>Dönüş Değeri

Yok.

## <a name="remarks"></a>Açıklamalar

**_Set_controlfp** işlevi benzer **_control87**, ancak yalnızca kayan nokta denetim sözcüğünü ayarlar *newControl*. Değerlerdeki bitler, kayan nokta denetim durumunu gösterir. Kayan nokta denetim durumu programın duyarlılık, yuvarlama ve sonsuzluk modlarını kayan nokta matematik paketindeki değiştirmesini sağlar. Ayrıca maskelemek veya maskesini kullanarak kayan nokta özel durumlarını **_set_controlfp**. Daha fazla bilgi için [_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md).

İle derlerken bu işlev kullanım dışı [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) çünkü ortak dil çalışma zamanı yalnızca varsayılan kayan nokta duyarlığını destekler.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|Uyumluluk|
|-------------|---------------------|-------------------|
|**_set_controlfp**|\<float.h >|x86 yalnızca işlemci|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
