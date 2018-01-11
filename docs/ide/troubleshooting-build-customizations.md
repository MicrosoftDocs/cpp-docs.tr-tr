---
title: "Derleme özelleştirmeleri sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- build events [C++], troubleshooting
- builds [C++], build events
- troubleshooting [C++], builds
- build steps [C++], troubleshooting
- events [C++], build
- builds [C++], troubleshooting
- custom build steps [C++], troubleshooting
ms.assetid: e4ceb177-fbee-4ed3-a7d7-80f0d78c1d07
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5fa3b2d3910a71d189f5177e13fbd91930e15ee8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="troubleshooting-build-customizations"></a>Derleme Özelleştirmeleri Sorunlarını Giderme
Özel derleme adımları veya beklediğiniz gibi olayları davranmakta olduğunu değil, yanlış neler olduğunu anlamak yapabileceğiniz birkaç şey vardır.  
  
-   Özel derleme adımları oluşturmak dosyaları çıkışları bildirme dosyaları eşleştiğinden emin olun.  
  
-   Özel derleme adımları girdiler herhangi bir dosya oluşturmak veya diğer bağımlılıklarını derleme adımları (özel veya diğer), bu dosyaları projenize eklendiğinden emin olun. Ve özel derleme adımı sonra bu dosyaları kullanmak araçları yürütme emin olun.  
  
-   Özel derleme adımı gerçekte yaptıklarını görüntülemek için add `@echo on` ilk komut olarak. Derleme adımlarını ve derleme olaylarını geçici .bat dosyaya yerleştirin ve proje yapılandırıldığında çalıştırın. Bu nedenle, yapı olaya denetlenirken hata ekleyebilir veya adım komutları derleme.  
  
-   Ne gerçekte yürütülen görmek için Ara dosya dizini derleme günlüğünde inceleyin. Yapı günlüğün adını ve yolunu belirtildiği **MSBuild** makrosu ifade **$(ıntdir)\\$(MSBuildProjectName) .log**.  
  
-   Birden çok varsayılan süre olan derleme günlüğünde bilgi toplamak için proje ayarlarınızı değiştirin. Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**. İçinde **seçenekleri** iletişim kutusu, tıklatın **projeler ve çözümler** düğümünü ve ardından **derleme ve çalıştırma** düğümü. Ardından **MSBuild proje derleme günlük dosyası ayrıntı** kutusunda, **ayrıntılı**.  
  
-   Kullanmakta olduğunuz adı veya dizin makroları değerlerin herhangi dosya doğrulayın. Makroları ayrı ayrı echo veya ekleyebileceğiniz `copy %0 command.bat` özel derleme adımı başlangıcına hangi kopyalar command.bat özel derleme adımının komutları genişletilmiş tüm makroları ile.  
  
-   Özel derleme adımları çalıştırın ve derleme olayları ayrı ayrı davranışlarını denetlemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](../ide/understanding-custom-build-steps-and-build-events.md)