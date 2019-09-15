---
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
ms.openlocfilehash: dac82ecd1c96d1edf9175a29797d93c65bc19c99
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952745"
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

**__max** , bağımsız değişkenlerinin büyük bir bölümünü döndürür.

## <a name="remarks"></a>Açıklamalar

**__Max** makrosu iki değeri karşılaştırır ve daha büyük bir değeri döndürür. Bağımsız değişkenler, imzalanmış veya imzasız herhangi bir sayısal veri türü olabilir. Bağımsız değişkenlerin ve dönüş değerinin her ikisi de aynı veri türünde olmalıdır.

Döndürülen bağımsız değişken makro tarafından iki kez değerlendirilir. Bağımsız değişken, değerlendiriliyorsa değeri değiştiren bir ifadesiyse, `*p++`bu beklenmeyen sonuçlara yol açabilir.

## <a name="requirements"></a>Gereksinimler

|Makrosu|Gerekli başlık|
|-------------|---------------------|
|**__max**|\<Stdlib. h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için bkz. [__min](min.md)örneği.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[__min](min.md)<br/>