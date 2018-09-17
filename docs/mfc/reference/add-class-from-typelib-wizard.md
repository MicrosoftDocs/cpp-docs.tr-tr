---
title: Typelib sihirbazından sınıf ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.class.typelib
dev_langs:
- C++
helpviewer_keywords:
- Add Class from TypeLib Wizard [MFC]
- COM interfaces, adding classes
ms.assetid: 96152afd-9374-4649-a6ab-b0fa2a5592a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bba9025e8a7529a2809c18eef8bd61ce7f620c0e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725003"
---
# <a name="add-class-from-typelib-wizard"></a>Tür Kitaplığı Sihirbazından Sınıf Ekleme
Bir kullanılabilir tür kitaplığından bir MFC sınıfı eklemek için bu sihirbazı kullanın. Sihirbaz, seçilen tür kitaplığından eklediğiniz her arabirim için bir sınıf oluşturur.  
  
- **Şuradan Sınıf Ekle**

   Tür kitaplığının sınıf oluşturulduğu konumu belirtir.  
  
   |Seçenek|Açıklama|  
   |------------|-----------------|  
   |**Kayıt defteri**|Tür kitaplığını sistemde kayıtlı. Kayıtlı bir tür kitaplığı içinde listelenen **kullanılabilir tür kitaplıklarını**.|  
   |**Dosya**|Tür kitaplığını mutlaka sistemde kayıtlı değil ancak bir dosyada yer alır. Dosya konumunda sağlamalısınız **konumu**.|  
  
- **Kullanılabilir tür kitaplıkları**

   Şu anda sistemde kayıtlı tür kitaplıkları listeler. Bu listeden arabirimlerinden içinde görüntülemek için bir tür kitaplığını seçin **arabirimleri** listesi.  
  
   "İçinde dağıtılmış COM: tür kitaplıklarını ve dil tümleştirme" tür kitaplıklarını kaydetme hakkında daha fazla bilgi için MSDN Kitaplığı'nda bkz.  
  
- **Konum**

   Tür kitaplığının konumu belirtir. Tıklarsanız **dosya** altında **sınıfı gelen ekleme**, tür kitaplığı içeren dosyanın konumunu sağlayabilir. Dosyasının konumuna göz atmak için üç nokta düğmesine tıklayın.  
  
- **Arabirimler**

   Tür kitaplığı şu anda seçili arabirimlerde listeler **kullanılabilir tür kitaplıklarını** listesi.  
  
   |Aktarım düğmesi|Açıklama|  
   |---------------------|-----------------|  
   |**>**|Şu anda seçili arabirimi ekler **arabirimleri** listesi. Herhangi bir arabirim seçtiyseniz soluk.|  
   |**>>**|Şu anda seçili tür kitaplığındaki tüm arabirimleri ekler **kullanılabilir tür kitaplıklarını** listesi.|  
   |**\<**|Şu anda seçili sınıfını kaldırır **sınıfları oluşturulan** listesi. Hiçbir sınıf içinde seçilirse soluk **sınıfları oluşturulan** listesi.|  
   |**\<\<**|Tüm sınıfları kaldırır **sınıfları oluşturulan** listesi. Soluk bir IF **sınıfları oluşturulan** listesi boş.|  
  
- **Oluşturulan sınıflar**

   Sınıf adları kullanılarak eklenen arabirimlerinden oluşturulacak belirtir **>** veya **>>** düğmesi. Bir sınıf seçin ve ardından yukarı veya aşağı tuşlarını kullanarak, listede gezinmek için bu kutuyu her sınıf adını görüntüleme tıklayabilirsiniz **sınıfı** kutusu ve dosya adı **dosya** kutusu sihirbaz ne zaman oluşturur, tıklayın **son**. Bu kutuya bir kerede yalnızca bir sınıf seçebilirsiniz.  
  
   Bu listede seçerek ve tıklatarak bir sınıf kaldırabilirsiniz **<**. Tüm sınıflar kaldırmak için oluşturulan sınıflar kutusunda bir sınıf seçin gerekmez; tıklayarak **<<**, içindeki tüm sınıflar Kaldır **sınıfları oluşturulan** kutusu.  
  
- **Sınıfı**

   Seçilen sınıfın adını belirtir **sınıfları oluşturulan** tıkladığınızda sihirbaz ekler kutusu **son**. Adlarında düzenleyebileceğiniz **sınıfı** kutusu.  
  
- **Dosya**

   Yeni bir sınıf için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **sınıfları oluşturulan**. Dosya adı, tercih ettiğiniz bir konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesine tıklayın. Var olan bir dosya seçerseniz, sihirbaz, seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.  
  
   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf bildirimi dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür kitaplığından MFC sınıfı](../../mfc/reference/adding-an-mfc-class-from-a-type-library.md)   
 [Otomasyon İstemcileri: Tür Kitaplıklarını Kullanma](../../mfc/automation-clients-using-type-libraries.md)

