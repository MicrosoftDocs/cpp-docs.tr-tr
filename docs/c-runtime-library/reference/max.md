---
title: __max | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5bc89f74bb98b8fb51dc652ab57c57d37a46d5a0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="max"></a>__max

İki değerden daha büyük döndürür önişlemci makrosu.

## <a name="syntax"></a>Sözdizimi

```C
#define __max(a,b) (((a) > (b)) ? (a) : (b))
```

### <a name="parameters"></a>Parametreler

*bir*, *b*<br/>
Karşılaştırılacak herhangi bir sayısal tür değerleri.

## <a name="return-value"></a>Dönüş Değeri

**__max** değişkenlerinin daha büyük döndürür.

## <a name="remarks"></a>Açıklamalar

**__Max** makrosu iki değeri karşılaştırır ve daha büyük bir değer döndürür. Bağımsız değişken veri türü, imzalı veya imzasız herhangi sayı olabilir. Bağımsız değişkenleri ve dönüş değeri aynı veri türünde olmalıdır.

Döndürülen bağımsız değişkeni, iki kez makrosu tarafından değerlendirilir. Bunu, aşağıdaki gibi değerlendirmesinde değerini değiştiren bir ifade bağımsız değişkeni ise, bu beklenmeyen sonuçlara yol açabilir `*p++`.

## <a name="requirements"></a>Gereksinimler

|Makrosu|Gerekli başlık|
|-------------|---------------------|
|**__max**|\<stdlib.h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için örneğin bkz [__min](min.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[__min](min.md)<br/>