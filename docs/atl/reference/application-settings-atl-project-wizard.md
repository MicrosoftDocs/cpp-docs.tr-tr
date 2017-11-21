---
title: "Uygulama ayarları, ATL Proje Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.appwiz.atl.com.appset
dev_langs: C++
helpviewer_keywords: ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 312c2b879f19e670d9737bfa530e0cc2a35bfe58
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="application-settings-atl-project-wizard"></a>Uygulama ayarları, ATL Proje Sihirbazı
Kullanım **uygulama ayarları** tasarlamak ve yeni bir ATL projesine temel özellikleri eklemek için ATL Proje Sihirbazı sayfasında.  
  
## <a name="server-type"></a>Sunucu türü  
 Üç sunucu türlerinden birini seçin:  
  
 **Dinamik bağlantı kitaplığı (DLL)**  
 Bir işlem sunucusu oluşturmak için seçin.  
  
 **Yürütülebilir (EXE)**  
 Yerel bir işlem dışı sunucusu oluşturmak için seçin. Bu seçenek, MFC veya COM + 1.0 için destek izin vermiyor. Proxy/stub kodunu birleştirme için izin vermiyor.  
  
 **Hizmet (EXE)**  
 Windows başladığında arka planda çalışan bir Windows uygulaması oluşturmak için seçin. Bu seçenek MFC veya COM + 1.0 için destek izin verme veya birleştirme proxy/stub kodu için izin vermez.  
  
## <a name="additional-options"></a>Ek Seçenekler  
  
> [!NOTE]
>  Tüm ek seçenekler yalnızca DLL projeleri için kullanılabilir.  
  
 **Proxy/stub kodunu birleştirme izin ver**  
 Seçin **izin proxy/stub kodunu birleştirme** arabirimleri hazırlama gerektiğinde kolaylık onay kutusu. Bu seçenek MIDL oluşturulan proxy ve saplama kod aynı yürütülebilir dosya sunucusu olarak geçirir.  
  
 **MFC desteği**  
 Nesnenizin MFC desteği içerdiğini belirtmek için bu seçeneği seçin. Bu seçenek, projenizin MFC kitaplıkları bağlar tüm sınıfları ve içerdikleri işlevleri erişebilirsiniz.  
  
 **Destek COM + 1.0**  
 COM + 1.0 bileşenleri desteklemek için proje oluşturma ayarlarını değiştirmek için seçin. Kitaplıkları standart listesine ek olarak, sihirbaz COM + 1.0 bileşen özgü kitaplığı comsvcs.lib ekler.  
  
 Ayrıca, mtxex.dll, uygulama başlatıldığında konak sisteminde yüklenen gecikme olur.  
  
-   **Bileşen Kaydedicisi Destek** ATL projeniz COM + 1.0 bileşenleri için destek içeriyorsa, bu seçenek belirleyebilirsiniz. Bileşen Kaydedicisi bileşenleri listesini elde etmek, bileşenlerin kaydı veya bileşenleri (ayrı ayrı veya tümünü bir defada) kaydını kaldırma, COM + 1.0 nesne sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md)   
 [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)   
 [Varsayılan ATL Proje yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)

