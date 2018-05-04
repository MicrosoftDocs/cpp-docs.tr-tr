---
title: Yardımcı işlevini anlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54ed331022c29ecc47d61bbcccbfac82000cb235
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="understanding-the-helper-function"></a>Yardımcı İşlevini Anlama
Bağlayıcı tarafından desteklenen Gecikmeli Yükleme Yardımcısı işlevi ne gerçekte DLL çalışma zamanında yükler ' dir. Kendi işlevi yazma ve Delayimp.lib içinde sağlanan yardımcı işlevini kullanmak yerine, programa bağlayarak davranışını özelleştirmek için yardımcı işlevini değiştirebilirsiniz. Bir yardımcı işlevini tüm Gecikmeli yüklenen DLL'ler işlevi görür.  
  
 DLL veya içeri aktarmalar adlarına göre özel işleme yapmak istiyorsanız, kendi yardımcı işlevini sürümü sağlayabilirsiniz.  
  
 Yardımcı işlevini aşağıdaki eylemleri gerçekleştirir:  
  
-   Bu önceden yüklenip yüklenmediğini görmek için kitaplığa depolanmış tanıtıcı denetler  
  
-   Çağrıları **LoadLibrary** DLL yüklenmesini denemek için  
  
-   Çağrıları **GetProcAddress** yordamı adresi alınıyor denemek için  
  
-   Şimdi yüklenen giriş noktası çağırmak için dönüştürücü döndürür gecikme içeri aktarmak için yükleme  
  
 Yardımcı işlevini geri bildirim kanca programınızdaki için her aşağıdaki eylemleri sonra çağırabilirsiniz:  
  
-   Yardımcı işlevini başladığında  
  
-   Hemen önce **LoadLibrary** yardımcı işlev çağrılır  
  
-   Hemen önce **GetProcAddress** yardımcı işlev çağrılır  
  
-   Varsa çağrısı **LoadLibrary** Yardımcısı işlevinde başarısız oldu  
  
-   Varsa çağrısı **GetProcAddress** Yardımcısı işlevinde başarısız oldu  
  
-   Sonra yardımcı işlevi yapılır işleme  
  
 Bunların her biri bağlama noktaları normal bir şekilde geri dönmek için gecikme alma yük dönüştürücü dışında Yardımcısı yordamında işlenmesini değiştirecek bir değeri geri dönebilirsiniz.  
  
 Varsayılan yardımcı kod Delayhlp.cpp ve Delayimp.h (vc\include içinde) bulunabilir ve içinde Delayimp.lib (vc\lib içinde) derlenir. Kendi yardımcı işlevinizi yazma sürece bu kitaplık, derlemeleri dahil etmeniz gerekir.  
  
 Aşağıdaki konular yardımcı işlevini açıklar:  
  
-   [Visual C++ 6.0 Sonrasındaki Gecikmeli Yükleme Yardımcısı İşlevi DLL Değişiklikleri](../../build/reference/changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)  
  
-   [Çağırma Kuralları, Parametreler ve Dönüş Türü](../../build/reference/calling-conventions-parameters-and-return-type.md)  
  
-   [Yapı ve Sabit Tanımları](../../build/reference/structure-and-constant-definitions.md)  
  
-   [Gereken Değerleri Hesaplama](../../build/reference/calculating-necessary-values.md)  
  
-   [Gecikmeli Yüklenen DLL'i Kaldırma](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)