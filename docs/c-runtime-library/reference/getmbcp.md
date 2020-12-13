---
description: 'Hakkında daha fazla bilgi edinin: _getmbcp'
title: _getmbcp
ms.date: 4/2/2020
api_name:
- _getmbcp
- _o__getmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getmbcp
- getmbcp
helpviewer_keywords:
- code pages, determining current
- _getmbcp function
- getmbcp function
ms.assetid: 2db202d4-5c3d-4871-a0b8-ceb0b79ee7bb
ms.openlocfilehash: a4b249d4cee94e5dc0755e72158aed2ffcee7efb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332877"
---
# <a name="_getmbcp"></a>_getmbcp

Geçerli kod sayfasını alır.

## <a name="syntax"></a>Syntax

```C
int _getmbcp( void );
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli çok baytlı kod sayfasını döndürür. 0 dönüş değeri, tek bir bayt kod sayfasının kullanımda olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getmbcp**|\<mbctype.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_setmbcp](setmbcp.md)<br/>
