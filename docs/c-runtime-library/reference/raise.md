---
title: Yükseltme | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1bc3f52b97159a9caba6f80b4798d9588ec341d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685914"
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
