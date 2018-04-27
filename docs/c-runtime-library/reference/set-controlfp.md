---
title: _set_controlfp | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f45b852884596db243e306ee2dff01127998a14f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="setcontrolfp"></a>_set_controlfp

Kayan nokta denetim sözcüğü ayarlar.

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
Ayarlanacak yeni denetim sözcüğü bit maskesi.

## <a name="return-value"></a>Dönüş Değeri

Yok.

## <a name="remarks"></a>Açıklamalar

**_Set_controlfp** işlevi benzer **_control87**, ancak yalnızca kayan nokta denetim sözcüğü ayarlar *newControl*. Değerleri bitleri kayan nokta denetim durumu gösterir. Kayan nokta denetim durumu duyarlık, yuvarlama ve kayan nokta Matematiği paketindeki sonsuz modlarını değiştirmek programın sağlar. Ayrıca maskeleme veya kayan nokta özel durumlar kullanma maskesini kaldırın **_set_controlfp**. Daha fazla bilgi için bkz: [_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md).

Bu işlev ile derleme yapılırken kullanım dışıdır [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) çünkü ortak dil çalışma zamanı yalnızca varsayılan kayan nokta duyarlık destekler.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|Uyumluluk|
|-------------|---------------------|-------------------|
|**_set_controlfp**|\<float.h >|x86 yalnızca işlemci|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
