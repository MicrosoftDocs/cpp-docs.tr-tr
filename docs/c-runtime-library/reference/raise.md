---
title: tetikle
ms.date: 01/02/2018
apiname:
- raise
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- Raise
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.openlocfilehash: 1354c76207d6cd59249f6c06df88ae23fe69b1e0
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927425"
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

**Raise** işlevi, çalıştırılan programa *SIG* gönderir. Önceki bir **sinyal** çağrısı *SIG*için bir sinyal işleme işlevi yüklemiştir **, bu** işlevi yürütür. Hiçbir işleyici işlevi yüklenmemişse, *SIG* sinyal değeri ile ilişkili varsayılan eylem aşağıdaki şekilde alınır.

|sinyalinin|Açıklama|Varsayılan|
|------------|-------------|-------------|
|**SIGABRT**|Olağan dışı sonlandırma|Çağıran programı çıkış kodu 3 ile sonlandırır|
|**SIGFPE**|Kayan nokta hatası|Çağıran programı sonlandırır|
|**SIGILL**|Geçersiz yönerge|Çağıran programı sonlandırır|
|**SIGINT**|CTRL + C kesme|Çağıran programı sonlandırır|
|**SIGSEGV**|Geçersiz depolama erişimi|Çağıran programı sonlandırır|
|**SIGTERM**|Programa sonlandırma isteği gönderildi|Sinyali yoksayar|

Bağımsız değişken yukarıda belirtilen geçerli bir sinyal değilse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. İşlenmezse, işlev **errno** 'ya **EINVAL** olarak ayarlar ve sıfır dışında bir değer döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**raise**|\<sinyal. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[signal](signal.md)<br/>
