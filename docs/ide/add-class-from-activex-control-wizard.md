---
title: "ActiveX denetimi sihirbazından sınıf ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.class.axcontrol
dev_langs: C++
helpviewer_keywords:
- ActiveX Control Wizard
- Add Class from ActiveX Control Wizard [C++]
ms.assetid: 668d801c-5fb6-4176-9191-5c38995a4713
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e2b3b1d2b15db47eea8ebc10b2a73cafba5d6952
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="add-class-from-activex-control-wizard"></a>ActiveX Denetimi Sihirbazından Sınıf Ekleme
Kullanılabilir ActiveX denetiminden bir MFC sınıfı eklemek için bu sihirbazı kullanın. Sihirbaz seçili ActiveX denetiminden eklediğiniz her bir arabirim için bir sınıf oluşturur.  
  
 **Sınıf ekleme**  
 Sınıf oluşturulduğu tür kitaplığı konumunu belirtir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Kayıt defteri**|Tür kitaplığı sistemde kayıtlı değil. Kayıtlı tür kitaplıklarına içinde listelenen **kullanılabilir ActiveX denetimleri**.|  
|**Dosya**|Tür kitaplığı mutlaka sistemde kayıtlı değil ancak bir dosyada yer alan. Dosya konumu sağlamalısınız **konumu**.|  
  
 **Kullanılabilir ActiveX denetimleri**  
 Şu anda sistemde kayıtlı ActiveX denetimlerini belirtir. ActiveX denetimi arabirimlerinden içinde görüntülemek için bu listeden seçin **arabirimleri** listesi. Bkz: [MFC ActiveX denetimleri: ActiveX denetimlerini dağıtma](../mfc/mfc-activex-controls-distributing-activex-controls.md) ActiveX denetimlerini kaydetme hakkında daha fazla bilgi.  
  
 Tıklatırsanız **dosya** altında **sınıfı gelen eklemek**, bu kutu değişikliği için kullanılamıyor.  
  
 **Konum**  
 ActiveX denetimi konumunu belirtir. Tıklatırsanız **dosya** altında **sınıfı gelen eklemek**, tür kitaplığı içeren dosyanın konumunu sağlayabilir. Dosyasının konumuna göz atmak için üç nokta düğmesini tıklatın.  
  
 Tıklatırsanız **kayıt defteri** altında **sınıfı gelen eklemek**, bu kutu değişikliği için kullanılamıyor.  
  
 **Arabirimler**  
 Şu anda seçili ActiveX denetiminde arabirimler belirtir **kullanılabilir ActiveX denetimleri** veya belirtilen dosya türü kitaplığında **konumu**.  
  
|Aktarma düğmesi|Açıklama|  
|---------------------|-----------------|  
|**>**|Şu anda seçili arabirimi ekler **arabirimleri** listesi. Arabirim seçilirse kullanılabilir.|  
|**>>**|Şu anda seçili ActiveX denetimindeki tüm arabirimleri ekler **kullanılabilir ActiveX denetimleri** veya belirtilen dosya türü kitaplığında **konumu**.|  
|**<**|Şu anda seçili sınıfı kaldırır **sınıflar** listesi. Hiçbir sınıf içinde seçilirse kullanılabilir **sınıflar** listesi.|  
|**<\<**|Tüm sınıflarda kaldırır **sınıflar** listesi. Kullanılamayan IF **sınıflar** listesi boş.|  
  
 **Oluşturulan sınıflar**  
 Sınıf adları kullanarak eklediğiniz arabirimlerinden oluşturulacak belirtir  **>**  veya  **>>**  düğmesi. Her sınıf adı görüntüleme bir sınıf seçin ve ardından yukarı veya aşağı tuşlarını liste boyunca kaydırma için bu kutuyu tıklatabilirsiniz `Class` kutusunu ve dosya adı **.h dosyası** tıkladığınızda, sihirbazın oluşturduğu kutusunu  **Son**. Bu kutuya bir kerede yalnızca bir sınıf seçebilirsiniz.  
  
 Bu listede seçerek ve tıklatarak bir sınıf kaldırabilirsiniz  **<** . Bir sınıf seçin gerekmez **sınıflar** kutusunu tüm sınıflar kaldırmak için; tıklayarak  **<<** , tüm sınıflarda kaldırmak **sınıflar** bir kutu.  
  
 `Class`  
 Seçilen sınıfın adını belirtir **sınıflar** tıkladığınızda, sihirbaz ekler kutusunu **son**. Adı düzenleyebilirsiniz `Class` kutusu.  
  
 **.h dosyası**  
 Yeni nesne sınıfı için üstbilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adının dayanır **sınıflar**. Dosya adı tercih ettiğiniz bir konuma kaydedin veya varolan bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini tıklatın. Varolan bir dosyanın seçerseniz, sihirbaz bunu seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf bildirimi dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
 **.cpp dosyası**  
 Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adının dayanır **sınıflar**. Dosya adı seçiminizi konuma kaydetmek için üç nokta düğmesini tıklatın. Tıklattığınız kadar dosya seçili konuma kaydedilmez **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf uygulamasını dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActiveX denetiminden sınıf ekleme](../ide/adding-a-class-from-an-activex-control-visual-cpp.md)   
 [Otomasyon İstemcileri: Tür Kitaplıklarını Kullanma](../mfc/automation-clients-using-type-libraries.md)