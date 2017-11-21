---
title: "Proje derleme hatası PRJ0003 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0003
dev_langs: C++
helpviewer_keywords: PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f06779fb8f2d5265d93cc4376b42669b978c4e5a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-error-prj0003"></a>Proje Derleme Hatası PRJ0003  
  
> Hata oluşturma '*komut satırı*'.  
  
*Komut satırı* komutu biçimlendirilmiş girişinde gelen **özellik sayfaları** iletişim kutusu bir hata kodunu döndürdü, ancak hiçbir bilgi görünür **çıkış** penceresi.  

Bu hata için olası nedenler şunlardır:  
  
-   Projenize ATL sunucusuna bağlıdır. Visual Studio 2008'den itibaren ATL Sunucu artık Visual Studio bir parçası olarak dahil değildir, ancak CodePlex bir paylaşılan kaynağı proje olarak yayımlanmıştır. ATL Sunucu kaynak kodu ve araçları yüklemek için Git [ATL Sunucu kitaplığının ve araçları](http://go.microsoft.com/fwlink/?LinkID=81979).  
  
-   Sistem kaynaklarının yetersizliği. Bu sorunu gidermek için bazı uygulamaları kapatın.  
  
-   Yeterli güvenlik ayrıcalıkları. Yeterli ayrıcalıklara sahip olduğunuzu doğrulayın.  
  
-   Belirtilen yürütülebilir dosya yolları **VC ++ dizinleri** çalıştırmayı denediğiniz aracı yolu içermiyor. Bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md)  
  
-   Derleme görevleri dosyası projeleri için üzerinde çalıştırılacak bir komut eksik **komut satırı derleme** veya **komut satırı yeniden**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje derleme hataları ve Uyarıları (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)