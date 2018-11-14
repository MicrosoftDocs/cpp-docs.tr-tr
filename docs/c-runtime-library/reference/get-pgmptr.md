---
title: _get_pgmptr
ms.date: 11/04/2016
apiname:
- _get_pgmptr
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
- get_pgmptr
- _get_pgmptr
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
ms.openlocfilehash: 2d3959a69d85fca38e4d099d3365553f88fd015f
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51332094"
---
# <a name="getpgmptr"></a>_get_pgmptr

Geçerli değeri alır **_pgmptr** genel değişkeni.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_pgmptr(
   char **pValue
);
```

### <a name="parameters"></a>Parametreler

*pValue*<br/>
Geçerli değeri ile doldurulacak bir dizeye bir işaretçi **_pgmptr** değişkeni.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır döndürür; bir hata kodu. Varsa *pValue* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

## <a name="remarks"></a>Açıklamalar

Yalnızca çağrı **_get_pgmptr** programınızı dar giriş noktası varsa, ister **ana()** veya **WinMain()**. **_Pgmptr** genel değişkeni işlemle ilişkili yürütülebilir dosyanın tam yolunu içerir. Daha fazla bilgi için [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_pgmptr**|\<stdlib.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_get_wpgmptr](get-wpgmptr.md)<br/>
