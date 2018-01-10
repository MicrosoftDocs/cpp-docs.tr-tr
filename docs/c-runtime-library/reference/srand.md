---
title: srand | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: srand
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords: srand
dev_langs: C++
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 205dcb2ba7d61dff1286fd926e3f10cf2a162e9a
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="srand"></a>srand

Tarafından kullanılan geçici rastgele sayı üreticisinin için başlangıç çekirdek değeri ayarlar `rand` işlevi.

## <a name="syntax"></a>Sözdizimi

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Parametreler

*Çekirdek*  
Sözde rastgele sayı üretimi için çekirdek

## <a name="remarks"></a>Açıklamalar

`srand` işlevi, geçerli iş parçacığında bir sözde rastgele tamsayı dizisi oluşturmak için başlangıç noktasını ayarlar. Sonuçların aynı dizisini oluşturmak için oluşturucunun yeniden başlatmak için arama `srand` işlev ve aynı *çekirdek* yeniden bağımsız değişkeni. Başka bir değer için *çekirdek* oluşturucunun geçici rastgele sırayla farklı bir başlangıç noktası olarak ayarlar. `rand`, oluşturulan sözde rastgele sayıları alır. Çağırma `rand` herhangi çağrıdan önce `srand` arama aynı sırada oluşturur `srand` ile *çekirdek* 1 olarak geçirildi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`srand`|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.

## <a name="example"></a>Örnek

Örneğin bkz [rand](../../c-runtime-library/reference/rand.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)  
[rand](../../c-runtime-library/reference/rand.md)  
