---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b38a3430274b2324e345be30ce9e38f0c2749fa3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338259"
---
# <a name="raise"></a>tetikle

Yürütme programına bir sinyal gönderir.

> [!NOTE]
> Test veya hata ayıklama senaryoları dışında bir Microsoft Mağazası uygulamasını kapatmak için bu yöntemi kullanmayın. Bir Mağaza uygulamasını kapatmanın programlı veya uI yollarına [Microsoft Mağazası ilkelerine](/legal/windows/agreements/store-policies)göre izin verilmez. Daha fazla bilgi için [UWP uygulama yaşam döngüsüne](/windows/uwp/launch-resume/app-lifecycle)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int raise(
   int sig
);
```

### <a name="parameters"></a>Parametreler

*Sıg*<br/>
Sinyal yükseltilecek.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, 0 döndürür **yükseltin.** Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Yükseltme** işlevi *yürütme* programına sig gönderir. **Sinyalönceki** bir arama *sig*için bir sinyal işleme işlevi yüklü ise, **yükseltmek** bu işlevi yürütür. İşleyici işlevi yüklenmemişse, aşağıdaki gibi sinyal değeri *sig* ile ilişkili varsayılan eylem alınır.

|Sinyal|Anlamı|Varsayılan|
|------------|-------------|-------------|
|**SIGABRT**|Anormal sonlandırma|Çıkış kodu 3 ile arama programını sonlandırır|
|**SIGFPE**|Kayan nokta hatası|Arama programını sonlandırır|
|**SIGILL**|Yasadışı talimat|Arama programını sonlandırır|
|**SIGINT**|CTRL+C kesme|Arama programını sonlandırır|
|**SIGSEGV**|Yasadışı depolama erişimi|Arama programını sonlandırır|
|**SIGTERM**|Programa gönderilen sonlandırma isteği|Sinyali yok sayar|

Bağımsız değişken yukarıda belirtildiği gibi geçerli bir sinyal değilse, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. İşlenmezse, işlev **errno'yu** **EINVAL** olarak ayarlar ve sıfır olmayan bir değer döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Yükseltmek**|\<signal.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[Iptal](abort.md)<br/>
[sinyal](signal.md)<br/>
