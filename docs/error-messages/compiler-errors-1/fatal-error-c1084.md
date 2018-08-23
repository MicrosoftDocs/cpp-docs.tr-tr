---
title: Önemli hata C1084 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1084
dev_langs:
- C++
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df584fd95921594562cf4c1fb912986343b30c4c
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42466091"
---
# <a name="fatal-error-c1084"></a>Önemli hata C1084
Dosya türü dosyası okunamıyor: 'file': ileti  
  
 Bu hata genellikle derleyici tarafından yapılan başarısız iç sistem API çağrısı sonucudur. Ne zaman bu hata ile gösterilen iletiyi sıklıkta ya da oluşturulduğu [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) veya [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage).  
  
 Aşağıdaki adımları gerçekleştirmek, C1084 gidermenize yardımcı olabilir:  
  
-   Belirtilen dosyanın var olduğundan emin olun.  
  
-   Belirtilen dosya erişmek için uygun izinleri ayarlayın sağlayın.  
  
-   Komut satırı sözdizimi aynılarını altında açıklanan kurallara için olun [derleyici komut satırı sözdizimi](../../build/reference/compiler-command-line-syntax.md).  
  
-   Ortam değişkenlerini emin olun **TMP** ve **TEMP** düzgün kümesi yanı sıra, bu ortam değişkenlerine başvurmak için dizinleri erişmek için uygun izinleri olan. Tarafından başvurulan sürücüler de emin **TMP** ve **TEMP** ortam değişkenlerini içeren bir yeterli boş alan miktarı.  
  
-   İleti "hatalı dosya numarası" derse, belirtilen dosya ön planda arka planda derlenirken kapatma.  
  
 Yukarıdaki tanılamalar gerçekleştirdikten sonra bir temiz yapı gerçekleştirin.