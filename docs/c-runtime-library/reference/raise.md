---
title: "Yükselt | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: raise
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
f1_keywords: Raise
dev_langs: C++
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.assetid: a3ccd3ad-f68f-4a7b-a005-c3ebfb217e8b
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 703f82f5c91cfecd65cb7ca7cf875729d9967f62
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="raise"></a>tetikle
Yürütülen programın bir sinyal gönderir.  
  
> [!NOTE]
>  Kapatmak için bu yöntemi kullanma bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamayı test etme veya senaryoları hata ayıklama dışındaki. Kapatmak için programlı veya UI yolu bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulama bölüm 3.6 göre verilmez [Windows 8 uygulama sertifika gereksinimleri](http://go.microsoft.com/fwlink/?LinkId=262889). Daha fazla bilgi için bkz: [uygulama yaşam döngüsü (Windows mağazası uygulamaları)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int raise(  
int sig   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *SIG*  
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
|**Yükselt**|\<Signal.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [Sinyal](../../c-runtime-library/reference/signal.md)