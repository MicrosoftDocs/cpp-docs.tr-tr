---
description: 'Hakkında daha fazla bilgi edinin: __max'
title: __max
ms.date: 04/05/2018
api_name:
- __max
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
- max
- __max
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
ms.openlocfilehash: 709bbb7aee48e65fdd3feb21eb1984135faae2f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299662"
---
# <a name="__max"></a>__max

İki değerden daha büyük bir değer döndüren bir önişlemci makrosu.

## <a name="syntax"></a>Sözdizimi

```C
#define __max(a,b) (((a) > (b)) ? (a) : (b))
```

### <a name="parameters"></a>Parametreler

*a*, *b*<br/>
Karşılaştırılacak herhangi bir sayısal tür değeri.

## <a name="return-value"></a>Dönüş Değeri

**__max** bağımsız değişkenlerinden daha büyük bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**__Max** makro iki değeri karşılaştırır ve daha büyük bir değeri döndürür. Bağımsız değişkenler, imzalanmış veya imzasız herhangi bir sayısal veri türü olabilir. Bağımsız değişkenlerin ve dönüş değerinin her ikisi de aynı veri türünde olmalıdır.

Döndürülen bağımsız değişken makro tarafından iki kez değerlendirilir. Bağımsız değişken, değerlendiriliyorsa değeri değiştiren bir ifadesiyse, bu beklenmeyen sonuçlara yol açabilir `*p++` .

## <a name="requirements"></a>Gereksinimler

|Makroya|Gerekli başlık|
|-------------|---------------------|
|**__max**|\<stdlib.h>|

## <a name="example"></a>Örnek

Daha fazla bilgi için bkz. [__min](min.md)örneği.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[__min](min.md)<br/>
