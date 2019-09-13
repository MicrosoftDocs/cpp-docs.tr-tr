---
title: srand
ms.date: 01/02/2018
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
ms.openlocfilehash: d74ae4cbec5a76df48bb2b56acab7329e6cf8aa5
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927413"
---
# <a name="srand"></a>srand

**S_SAYI_ÜRET** işlevi tarafından kullanılan pseudportadom sayı oluşturucusunun başlangıç çekirdek değerini ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Parametreler

*çekirdek*<br/>
Sözde rastgele sayı üretimi için çekirdek

## <a name="remarks"></a>Açıklamalar

**Srand** işlevi, geçerli iş parçacığında bir dizi pseudportadom tamsayısı oluşturmak için başlangıç noktasını ayarlar. Aynı sonuç dizisini oluşturmak üzere oluşturucuyu yeniden başlatmak için, **srand** işlevini çağırın ve aynı *çekirdek* bağımsız değişkenini tekrar kullanın. *Çekirdek* için diğer herhangi bir değer, oluşturucuyu pseudportaıdom dizisindeki farklı bir başlangıç noktasına ayarlar. **S_SAYI_ÜRET** , oluşturulan pseudportaıdom numaralarını alır. Hiçbir **srcall** 'tan önce **S_SAYI_ÜRET** çağrısı yapın ve *çekirdek* ile, 1 olarak **geçirilmiş ile aynı** diziyi oluşturur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**srand**|\<Stdlib. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[S_SAYI_ÜRET](rand.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
