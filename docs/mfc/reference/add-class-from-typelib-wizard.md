---
title: "Typelib sihirbazından sınıf ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.class.typelib
dev_langs:
- C++
helpviewer_keywords:
- Add Class from TypeLib Wizard [MFC]
- COM interfaces, adding classes
ms.assetid: 96152afd-9374-4649-a6ab-b0fa2a5592a3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4aad89b6f3227cac59b6429cc67975db3dad424
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="add-class-from-typelib-wizard"></a>Tür Kitaplığı Sihirbazından Sınıf Ekleme
Kullanılabilir tür kitaplığından bir MFC sınıfı eklemek için bu sihirbazı kullanın. Sihirbaz seçilen tür kitaplığından eklediğiniz her bir arabirim için bir sınıf oluşturur.  
  
 **Sınıf ekleme**  
 Sınıf oluşturulduğu tür kitaplığı konumunu belirtir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Kayıt defteri**|Tür kitaplığı sistemde kayıtlı değil. Kayıtlı tür kitaplıklarına içinde listelenen **kullanılabilir tür kitaplıklarının**.|  
|**Dosya**|Tür kitaplığı mutlaka sistemde kayıtlı değil ancak bir dosyada yer alan. Dosya konumu sağlamalısınız **konumu**.|  
  
 **Kullanılabilir tür kitaplıkları**  
 Şu anda sistemde kayıtlı tür kitaplıklarını listeler. Tür kitaplığı arabirimlerinden içinde görüntülemek için bu listeden seçin **arabirimleri** listesi.  
  
 "İçinde dağıtılmış COM: türü kitaplıkları ve dil tümleştirme" tür kitaplıklarının kaydetme hakkında daha fazla bilgi için MSDN Kitaplığı'nda bkz.  
  
 **Konum**  
 Tür kitaplığı konumunu belirtir. Tıklatırsanız **dosya** altında **sınıfı gelen eklemek**, tür kitaplığı içeren dosyanın konumunu sağlayabilir. Dosyasının konumuna göz atmak için üç nokta düğmesini tıklatın.  
  
 **Arabirimler**  
 Şu anda seçili tür kitaplığında arabirimleri listeler **kullanılabilir tür kitaplıklarının** listesi.  
  
|Aktarma düğmesi|Açıklama|  
|---------------------|-----------------|  
|**>**|Şu anda seçili arabirimi ekler **arabirimleri** listesi. Arabirim seçtiyseniz soluk.|  
|**>>**|Şu anda seçili Tür Kitaplığı'ndaki tüm arabirimleri ekler **kullanılabilir tür kitaplıklarının** listesi.|  
|**<**|Şu anda seçili sınıfı kaldırır **sınıflar** listesi. Hiçbir sınıf içinde seçiliyse soluk **sınıflar** listesi.|  
|**<\<**|Tüm sınıflarda kaldırır **sınıflar** listesi. Devre dışı ise **sınıflar** listesi boş.|  
  
 **Oluşturulan sınıflar**  
 Sınıf adları kullanarak eklediğiniz arabirimlerinden oluşturulacak belirtir  **>**  veya  **>>**  düğmesi. Her sınıf adı görüntüleme bir sınıf seçin ve ardından yukarı veya aşağı tuşlarını liste boyunca kaydırma için bu kutuyu tıklatabilirsiniz `Class` kutusunu ve dosya adı **dosya** tıkladığınızda, sihirbazın oluşturduğu kutusunu  **Son**. Bu kutuya bir kerede yalnızca bir sınıf seçebilirsiniz.  
  
 Bu listede seçerek ve tıklatarak bir sınıf kaldırabilirsiniz  **<** . Tüm sınıflar kaldırmak için oluşturulan sınıflar kutusunda bir sınıf seçin gerekmez; tıklayarak  **<<** , tüm sınıflarda kaldırmak **sınıflar** kutusu.  
  
 `Class`  
 Seçilen sınıfın adını belirtir **sınıflar** tıkladığınızda, sihirbaz ekler kutusunu **son**. Adı düzenleyebilirsiniz `Class` kutusu.  
  
 **Dosya**  
 Üst bilgi dosyasını yeni sınıfın adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adının dayanır **sınıflar**. Dosya adı tercih ettiğiniz bir konuma kaydedin veya varolan bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini tıklatın. Varolan bir dosyanın seçerseniz, sihirbaz bunu seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf bildirimi dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür kitaplığından MFC sınıfı](../../mfc/reference/adding-an-mfc-class-from-a-type-library.md)   
 [Otomasyon İstemcileri: Tür Kitaplıklarını Kullanma](../../mfc/automation-clients-using-type-libraries.md)

