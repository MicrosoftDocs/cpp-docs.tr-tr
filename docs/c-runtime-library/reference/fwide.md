---
description: 'Daha fazla bilgi edinin: fwide'
title: fwide
ms.date: 11/04/2016
api_name:
- fwide
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fwide
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
ms.openlocfilehash: 5cc49bb92421ac8899df9850c110a519d32b1d1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273754"
---
# <a name="fwide"></a>fwide

Meyen.

## <a name="syntax"></a>Sözdizimi

```C
int fwide(
   FILE *stream,
   int mode;
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi (yoksayıldı).

*modundaysa*<br/>
Akışın yeni genişliği: geniş karakter pozitif, bayt için negatif, değiştirilmeden bırakmak için sıfır. (Bu değer yok sayılır.)

## <a name="return-value"></a>Dönüş Değeri

Bu işlev şu anda yalnızca *modunu* döndürüyor.

## <a name="remarks"></a>Açıklamalar

Bu işlevin geçerli sürümü, standarda uymuyor.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fwide**|\<wchar.h>|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).
