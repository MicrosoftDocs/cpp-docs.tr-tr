---
title: Proje derleme hatası PRJ0003 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0003
dev_langs:
- C++
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a44f272569741b1897caed1d1d64832d8b113eae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316442"
---
# <a name="project-build-error-prj0003"></a>Proje Derleme Hatası PRJ0003  
  
> Hata oluşturma '*komut satırı*'.  
  
*Komut satırı* komutu biçimlendirilmiş girişinde gelen **özellik sayfaları** iletişim kutusu bir hata kodunu döndürdü, ancak hiçbir bilgi görünür **çıkış** penceresi.  

Bu hata için olası nedenler şunlardır:  
  
-   Projenize ATL sunucusuna bağlıdır. Visual Studio 2008'den itibaren ATL Sunucu artık Visual Studio bir parçası olarak dahil değildir, ancak CodePlex bir paylaşılan kaynağı proje olarak yayımlanmıştır. ATL Sunucu kaynak kodu ve araçları yüklemek için Git [ATL Sunucu kitaplığının ve araçları](http://go.microsoft.com/fwlink/p/?linkid=81979).  
  
-   Sistem kaynaklarının yetersizliği. Bu sorunu gidermek için bazı uygulamaları kapatın.  
  
-   Yeterli güvenlik ayrıcalıkları. Yeterli ayrıcalıklara sahip olduğunuzu doğrulayın.  
  
-   Belirtilen yürütülebilir dosya yolları **VC ++ dizinleri** çalıştırmayı denediğiniz aracı yolu içermiyor. Bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md)  
  
-   Derleme görevleri dosyası projeleri için üzerinde çalıştırılacak bir komut eksik **komut satırı derleme** veya **komut satırı yeniden**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje Derleme Hataları ve Uyarıları (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)