---
description: 'Daha fazla bilgi edinin: Raise'
title: tetikle
ms.date: 4/2/2020
api_name:
- raise
- _o_raise
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- Raise
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.openlocfilehash: eb225e25ef0ff4e04f1ea8877a434c2af240cbfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274872"
---
# <a name="raise"></a>tetikle

Yürütülen programa bir sinyal gönderir.

> [!NOTE]
> Test veya hata ayıklama senaryoları dışında Microsoft Store uygulamasını kapatmak için bu yöntemi kullanmayın. Bir mağaza uygulamasını kapatmak için programlı veya Kullanıcı arabirimi yollarına [Microsoft Store ilkelerine](/legal/windows/agreements/store-policies)göre izin verilmez. Daha fazla bilgi için bkz. [UWP uygulama yaşam döngüsü](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Sözdizimi

```C
int raise(
   int sig
);
```

### <a name="parameters"></a>Parametreler

*za*<br/>
Ortaya çıkan sinyal.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **Raise** 0 döndürür. Aksi takdirde, sıfır dışında bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Raise** işlevi, çalıştırılan programa *SIG* gönderir. Önceki bir **sinyal** çağrısı *SIG* için bir sinyal işleme işlevi yüklemiştir **, bu** işlevi yürütür. Hiçbir işleyici işlevi yüklenmemişse, *SIG* sinyal değeri ile ilişkili varsayılan eylem aşağıdaki şekilde alınır.

|Sinyalinin|Anlamı|Varsayılan|
|------------|-------------|-------------|
|**SıGABRT**|Olağan dışı sonlandırma|Çağıran programı çıkış kodu 3 ile sonlandırır|
|**SıGFPE**|Kayan nokta hatası|Çağıran programı sonlandırır|
|**SıGıLL**|Geçersiz yönerge|Çağıran programı sonlandırır|
|**SıGıNT**|CTRL + C kesme|Çağıran programı sonlandırır|
|**SıGSEGV**|Geçersiz depolama erişimi|Çağıran programı sonlandırır|
|**SıGTERM**|Programa sonlandırma isteği gönderildi|Sinyali yoksayar|

Bağımsız değişken yukarıda belirtilen geçerli bir sinyal değilse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. İşlenmezse, işlev **errno** 'ya **EINVAL** olarak ayarlar ve sıfır dışında bir değer döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**tetikle**|\<signal.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[durdur](abort.md)<br/>
[sinyal](signal.md)<br/>
