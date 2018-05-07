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
ms.openlocfilehash: a7266a2158c3e6ccd02ea82de22c6f90a8b6363d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1084"></a>Önemli hata C1084
Dosya türü dosyası okunamıyor: 'dosya': ileti  
  
 Bu hata genellikle derleyici tarafından yapılan başarısız iç sistem API çağrısı sonucudur. Ne zaman bu hata ile gösterilen ileti sıklıkta ya da oluşturulduğu [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) veya [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351.aspx).  
  
 Aşağıdaki adımları gerçekleştirmeden C1084 giderilmesine yardımcı olabilir:  
  
-   Belirtilen dosyanın var olduğundan emin olun.  
  
-   Belirtilen dosya erişmek için uygun izinleri ayarlandığından emin olun.  
  
-   Komut satırı sözdizimi aynılarını altında özetlenen kuralları olun [derleyici komut satırı sözdizimi](../../build/reference/compiler-command-line-syntax.md).  
  
-   Ortam değişkenleri emin olun **TMP** ve **TEMP** düzgün kümesi gibi bu ortam değişkenleri başvurmak için dizinler erişmek için uygun izinleriniz olduğundan. Tarafından başvurulan sürücüler de emin **TMP** ve **TEMP** ortam değişkenleri içeren bir yeterli boş alan miktarı.  
  
-   İleti "hatalı dosya numarası" diyorsa, belirtilen dosya ön planda arka planda derlenirken kapatma.  
  
 Yukarıdaki tanılama gerçekleştirdikten sonra temiz bir yapı gerçekleştirin.