---
title: tetikle
ms.date: 1/02/2018
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
ms.openlocfilehash: 68d1cc653b955e607648e4d30562d2b77e3520e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638119"
---
# <a name="raise"></a>tetikle

Çalışan programa bir sinyal gönderir.

> [!NOTE]
> Bu yöntem, test veya hata ayıklama senaryoları dışında bir Microsoft Store uygulamasını kapatmak için kullanmayın. Bir Store uygulamasını kapatmak için programlama veya UI yollarına göre izin verilmez [Microsoft Store ilkeleri](/legal/windows/agreements/store-policies). Daha fazla bilgi için [UWP uygulama yaşam döngüsü](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Sözdizimi

```C
int raise(
   int sig
);
```

### <a name="parameters"></a>Parametreler

*Sig*<br/>
Oluşturulacak sinyal.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **yükseltmek** 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Yükseltmek** işlev gönderir *sig* yürüten programa. Önceki bir çağrı, **sinyal** için bir sinyal işleme işlevi yüklediği *sig*, **yükseltmek** bu işlevi yürütür. Herhangi işleyici işlevi yüklenmemişse, sinyal değeri ile ilişkilendirmiş varsayılan eylem *sig* , şekilde alınır.

|Sinyal|Açıklama|Varsayılan|
|------------|-------------|-------------|
|**SIGABRT**|Olağan dışı sonlandırma|Çağıran programı çıkış kodu 3 ile sonlandırır|
|**SIGFPE**|Kayan nokta hatası|Çağırma programını sonlandırır|
|**SIGILL**|Geçersiz yönerge|Çağırma programını sonlandırır|
|**SIGINT**|CTRL + C kesme|Çağırma programını sonlandırır|
|**SIGSEGV**|Geçersiz depo erişimi|Çağırma programını sonlandırır|
|**SIGTERM**|Programa gönderilen sonlandırma isteği|Sinyali yok sayıyor|

Bağımsız değişken yukarıda belirtildiği gibi geçerli bir sinyal değilse, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). İşlenmezse, işlev ayarlar **errno** için **EINVAL** ve sıfır olmayan bir değer döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**raise**|\<Signal.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[signal](signal.md)<br/>
