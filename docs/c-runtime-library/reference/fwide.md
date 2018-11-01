---
title: fwide
ms.date: 11/04/2016
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
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
ms.openlocfilehash: d992ebc527744beeb4ef14175e3f10646a77a064
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557855"
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

*Stream*<br/>
İşaretçi **dosya** yapısı (yoksayıldı).

*Modu*<br/>
Yeni akış genişliğini: geniş karakter, bayt, negatif pozitif değiştirmeden bırakmak için sıfır. (Bu değer yoksayılır.)

## <a name="return-value"></a>Dönüş Değeri

Bu işlev şu anda yalnızca döndürür *modu*.

## <a name="remarks"></a>Açıklamalar

Bu işlev geçerli sürümü standardı ile uyumlu değildir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fwide**|\<wchar.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).