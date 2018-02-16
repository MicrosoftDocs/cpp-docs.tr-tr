---
title: "Yükselt | Microsoft Docs"
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5a116bfab72222bcf3ee3357c77759960f838cb9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="raise"></a>tetikle

Yürütülen programın bir sinyal gönderir.

> [!NOTE]
> Bu yöntem, test etme veya senaryoları hata ayıklama bir Microsoft Store uygulamasını, kapatmak için kullanmayın. Bir mağaza uygulamasını kapatmak için programlı veya UI yolu göre verilmez [Microsoft Store ilkeleri](http://go.microsoft.com/fwlink/?LinkId=865936). Daha fazla bilgi için bkz: [UWP uygulama yaşam döngüsü](http://go.microsoft.com/fwlink/p/?LinkId=865934).

## <a name="syntax"></a>Sözdizimi

```C
int raise(
   int sig
);
```

### <a name="parameters"></a>Parametreler

*sig*  
Çıkarılmasına sinyal.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **yükseltmek** 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Yükseltmek** işlev gönderir *SIG* yürütülen program. Önceki çağrı varsa **sinyal** için sinyal işleme işlevi yüklediği *SIG*, **yükseltmek** bu işlev yürütür. Varsayılan eylem hiçbir işleyici işlevi yüklediyseniz sinyal değeriyle ilişkili *SIG* , şu şekilde gerçekleştirilir.

|Sinyal|Açıklama|Varsayılan|
|------------|-------------|-------------|
|`SIGABRT`|Olağan dışı sonlandırma|Çağıran program 3 çıkış koduyla sona erer|
|`SIGFPE`|Kayan nokta hatası|Çağıran program sonlandırır|
|`SIGILL`|Geçersiz yönergesi|Çağıran program sonlandırır|
|`SIGINT`|CTRL + C kesme|Çağıran program sonlandırır|
|`SIGSEGV`|Geçersiz depolama erişim|Çağıran program sonlandırır|
|`SIGTERM`|Programa gönderilen sonlandırma isteği|Sinyal yoksayar|

Bağımsız değişkeni geçerli bir sinyal yukarıda belirtildiği gibi değilse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). İşlenmemiş varsa, işlev ayarlar `errno` için `EINVAL` ve sıfır olmayan bir değer döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**raise**|\<Signal.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)  
[abort](../../c-runtime-library/reference/abort.md)  
[signal](../../c-runtime-library/reference/signal.md)  
