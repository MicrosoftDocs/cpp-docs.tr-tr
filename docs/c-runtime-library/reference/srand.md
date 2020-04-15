---
title: srand
ms.date: 4/2/2020
api_name:
- srand
- _o_srand
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
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- srand
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
ms.openlocfilehash: a8d018d429b2a484f88b7c1e0679f1f799983910
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355495"
---
# <a name="srand"></a>srand

**Rand** fonksiyonu tarafından kullanılan psödorandom sayı üreteci için başlangıç tohum değerini ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Parametreler

*Tohum*<br/>
Sözde rastgele sayı üretimi için çekirdek

## <a name="remarks"></a>Açıklamalar

**Kum** işlevi, geçerli iş parçacığında bir dizi psödorastgele tamsayı oluşturmak için başlangıç noktasını ayarlar. Aynı sonuç dizisini oluşturmak için jeneratörü yeniden başlatmayı sağlamak **için, kum** işlevini arayın ve aynı *tohum* bağımsız değişkenini yeniden kullanın. *Tohum* için başka bir değer pseudorandom dizisinde farklı bir başlangıç noktasına jeneratör ayarlar. **rand** oluşturulan pseudorandom numaraları alır. **Rand'ı** herhangi bir çağrıdan önce **aramak,** 1 olarak geçirilen *tohumlu* **kum** çağırma yla aynı sırayı oluşturur.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**srand**|\<stdlib.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[rand](rand.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Rand](rand.md)<br/>
