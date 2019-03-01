---
title: srand
ms.date: 1/02/2018
apiname:
- srand
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
- ntoskrnl.exe
apitype: DLLExport
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
ms.openlocfilehash: 6545d4eba6c17fd55bb2b8cf23fb0319d1c96bee
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57209827"
---
# <a name="srand"></a>srand

Tarafından kullanılan sözde rastgele sayı üretici için başlangıç çekirdek değerini ayarlar **rand** işlevi.

## <a name="syntax"></a>Sözdizimi

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Parametreler

*Çekirdek*<br/>
Sözde rastgele sayı üretimi için çekirdek

## <a name="remarks"></a>Açıklamalar

**Srand** işlevi, geçerli iş parçacığında bir sözde rastgele tamsayı dizisi oluşturmak için başlangıç noktasını ayarlar. Aynı sonuç dizisini oluşturmak için oluşturucu yeniden başlatmak için çağrı **srand** işlevini ve aynı *çekirdek* yeniden bağımsız değişken. İçin herhangi bir değer *çekirdek* Oluşturucu sözde rastgele dizi içinde farklı bir başlangıç noktası olarak ayarlar. **rand** oluşturulan sözde rastgele sayıları alır. Çağırma **rand** yapılan tüm çağrıların önce **srand** arama aynı dizi oluşturur **srand** ile *çekirdek* 1 olarak geçmesiyle.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**srand**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [rand](rand.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
