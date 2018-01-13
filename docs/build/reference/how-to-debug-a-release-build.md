---
title: "Nasıl yapılır: yayın derlemesinde hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 31113d9a5935536ac10b22c7b5f5af27b0d29970
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-debug-a-release-build"></a>Nasıl yapılır: Yayın Derlemesinde Hata Ayıklama
Yayın derlemesi uygulamanın ayıklayabilirsiniz.  
  
### <a name="to-debug-a-release-build"></a>Yayın derlemesi hatalarını ayıklamak için  
  
1.  Açık **özellik sayfaları** projesi için iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** düğümü. Ayarlama **hata ayıklama bilgileri biçimi** için [C7 uyumlu (/ Z7)](../../build/reference/z7-zi-zi-debug-information-format.md) veya **Program veritabanı (/Zi)**.  
  
3.  Genişletme **bağlayıcı** tıklatıp **genel** düğümü. Ayarlama **artımlı bağlantılandırma etkinleştirmek** için [yok (/ ARTIMLI: Hayır)](../../build/reference/incremental-link-incrementally.md).  
  
4.  Seçin **hata ayıklama** düğümü. Ayarlama **hata ayıklama bilgileri üret** için [Evet (/ DEBUG)](../../build/reference/debug-generate-debug-info.md).  
  
5.  Seçin **en iyi duruma getirme** düğümü. Ayarlama **başvuruları** için [/OPT:REF](../../build/reference/opt-optimizations.md) ve **comdat'ı Katlama etkinleştirmek** için [/OPT:ICF](../../build/reference/opt-optimizations.md).  
  
6.  Yayın derleme uygulamanız şimdi ayıklayabilirsiniz. Hatanın oluştuğu bulana kadar bir sorun, adım kodu (veya kullanım sadece zamanında hata ayıklama) aracılığıyla bulmak ve parametreleri yanlış veya kod belirlemek için.  
  
     Bir uygulama bir hata ayıklama derlemesi çalışır ancak bir yayın derlemesi başarısız olursa, derleyici iyileştirmelerini birini kaynak kodunu üründe gösterme. Dosya ve soruna neden olan en iyi duruma getirme bulana kadar sorunu ayırt etmek için her kaynak kodu dosyasının seçili en iyi duruma getirme devre dışı bırakın. (İşlemi hızlandırmak için dosyaları iki gruba ayırın, bir grup en iyi duruma getirilmesi devre dışı bırakmak ve bir grup, bir sorunu bulduğunuzda sorun dosya yalıtmak kadar bölme devam edebilirsiniz.)  
  
     Kullanabileceğiniz [eş yordamlarla/RTC](../../build/reference/rtc-run-time-error-checks.md) bu tür hataların hata ayıklama derlemelerinde kullanıma dener.  
  
     Daha fazla bilgi için bkz: [kodunuzu en iyi duruma getirme](../../build/reference/optimizing-your-code.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yayın Derlemesi Sorunlarını Giderme](../../build/reference/fixing-release-build-problems.md)