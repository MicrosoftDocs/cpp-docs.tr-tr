---
title: fwide | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fwide
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
- fwide
dev_langs:
- C++
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd52c450e2eb34c40d44d00a76550c401abcb6c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fwide"></a>fwide

Uygulanmayan.

## <a name="syntax"></a>Sözdizimi

```C
int fwide(
   FILE *stream,
   int mode;
);
```

### <a name="parameters"></a>Parametreler

*Akış*<br/>
İşaretçi **dosya** yapısı (yoksayıldı).

*Modu*<br/>
Akış yeni genişliğini: bırakmak için sıfır geniş karakter, bayt, negatif için pozitif bir farklılık göstermez. (Bu değer yoksayılır.)

## <a name="return-value"></a>Dönüş Değeri

Bu işlev, şu anda yalnızca döndürür *modu*.

## <a name="remarks"></a>Açıklamalar

Bu işlev geçerli sürümü standart ile uyumlu değil.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fwide**|\<wchar.h >|

Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).