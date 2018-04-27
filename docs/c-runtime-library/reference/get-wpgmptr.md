---
title: _get_wpgmptr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _get_wpgmptr
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
- get_wpgmptr
- _get_wpgmptr
dev_langs:
- C++
helpviewer_keywords:
- _wpgmptr global variable
- get_wpgmptr function
- wpgmptr global variable
- _get_wpgmptr function
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23ebeed5b6710a7c8032f75b8677b09f8f96c84a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="getwpgmptr"></a>_get_wpgmptr

Geçerli değerini alır **_wpgmptr** genel değişkeni.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_wpgmptr( 
   wchar_t **pValue 
);
```

### <a name="parameters"></a>Parametreler

*pValue*<br/>
Geçerli değeri ile doldurulması için bir dize için bir işaretçi **_wpgmptr** değişkeni.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır döndürür; hatasında bir hata kodu. Varsa *pValue* olan **NULL**, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

## <a name="remarks"></a>Açıklamalar

Yalnızca çağrısı **_get_wpgmptr** programınızın geniş giriş noktası varsa, ister **wmain()** veya **wWinMain()**. **_Wpgmptr** genel değişkeni işlem olarak bir joker karakter dizesi ile ilişkili yürütülebilir dosyanın tam yolunu içerir. Daha fazla bilgi için bkz: [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_wpgmptr**|\<stdlib.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_get_pgmptr](get-pgmptr.md)<br/>
