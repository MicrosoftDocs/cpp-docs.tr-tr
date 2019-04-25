---
title: __max
ms.date: 04/05/2018
apiname:
- __max
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
- max
- __max
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
ms.openlocfilehash: 32e1207ea4bb030ac5303de32c0566f98e0596a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156875"
---
# <a name="max"></a>__max

İki değeri büyük döndürür önişlemci makrosu.

## <a name="syntax"></a>Sözdizimi

```C
#define __max(a,b) (((a) > (b)) ? (a) : (b))
```

### <a name="parameters"></a>Parametreler

*a*, *b*<br/>
Herhangi bir sayısal tür Karşılaştırılacak değerler.

## <a name="return-value"></a>Dönüş Değeri

**__max** büyük bağımsız değişkenlerinin döndürür.

## <a name="remarks"></a>Açıklamalar

**__Max** makrosu iki değeri karşılaştırır ve büyük bir değer döndürür. Bağımsız değişkenler, imzalı veya imzasız veri türü, bir sayı olabilir. Hem bağımsız değişkenler ve dönüş değeri, aynı veri türünde olmalıdır.

Döndürülen bağımsız değişkeni iki kez makro tarafından değerlendirilir. Bunu, aşağıdaki gibi değerlendirildiğinde değerini değiştiren bir ifade bağımsız değişken ise bu beklenmeyen sonuçlara neden olabilir `*p++`.

## <a name="requirements"></a>Gereksinimler

|Makrosu|Gerekli başlık|
|-------------|---------------------|
|**__max**|\<stdlib.h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için örneğin bakın [__min](min.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[__min](min.md)<br/>