---
title: 'MFC ActiveX denetimleri: Özel özellikler ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc3aa3f7aa8b6f4abf28c12a11f75540f59238e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352431"
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC ActiveX Denetimleri: Özel Özellikler Ekleme
Özel özellikler farklı stok özelliklerinden özel özellikler tarafından zaten uygulanmaz, `COleControl` sınıfı. Özel bir özellik, belirli bir durumu veya bir ActiveX denetimine denetimi kullanarak Programcı görünümünü göstermek için kullanılır.  
  
 Bu makalede, Özellik Ekleme Sihirbazı'nı kullanarak ActiveX denetimi için bir özel özellik eklemeyi açıklar ve sonuçta elde edilen bir kod değişikliği açıklar. Konular şunlardır:  
  
-   [Bir özel özellik eklemek için Özellik Ekleme Sihirbazı'nı kullanma](#_core_using_classwizard_to_add_a_custom_property)  
  
-   [Özel özellikler için özellik Sihirbazı değişiklikleri Ekle](#_core_classwizard_changes_for_custom_properties)  
  
 Özel özellikler gelen uygulama dört çeşitleri: üye değişkeni, üye değişken bildirimi, Get/Set yöntemleri ve Parameterized ile.  
  
-   Üye değişkeni uygulama  
  
     Bu uygulama bir üye değişkeni control sınıfı olarak özelliğin durumunu temsil eder. Özellik değeri değiştiğinde bilmek önemli olmadığında üye değişkeni uygulaması kullanın. Üç tür, bu uygulama, en az bir özellik için destek kodu oluşturur. Üye değişkeni uygulaması için gönderme eşleme girişi makro [dısp_property](../mfc/reference/dispatch-maps.md#disp_property).  
  
-   Üye değişkeni bildirim uygulaması  
  
     Bu uygulama bir üye değişkenine ve Özellik Ekleme Sihirbazı tarafından oluşturulan bir bildirim işlevi oluşur. Bildirim işlevi özellik değeri değiştikten sonra otomatik olarak çerçevesi tarafından çağrılır. Bir özellik değeri değiştikten sonra bildirim almak gerektiğinde üye değişken bildirimi uygulamasıyla kullanın. Bir işlev çağrısı gerektirdiğinden bu uygulama daha uzun sürer. Bu uygulama için gönderme eşleme girişi makro [dısp_property_notıfy](../mfc/reference/dispatch-maps.md#disp_property_notify).  
  
-   Get/Set yöntemleri uygulama  
  
     Bu uygulama control sınıfı içindeki üye işlevleri çiftinden oluşur. Denetimin kullanıcı özelliği değiştirilmesi istediğinde Get/Set yöntemleri uygulama denetimin kullanıcı özelliğinin geçerli değeri istediğinde işlevi ve kümesi üye işlevi otomatik olarak Get üye çağırır. Gerektiğinde çalışma zamanı sırasında bir özelliğin değerini hesaplamak için gerçek özellik değiştirmeden önce denetimin kullanıcı tarafından geçirilen bir değeri doğrulamak veya bir ya da yazma-salt okunur özellik türü uygulamak, bu uygulamayı kullanın. Bu uygulama için gönderme eşleme girişi makro [dısp_property_ex](../mfc/reference/dispatch-maps.md#disp_property_ex). Aşağıdaki bölümde [Özellik Ekleme Sihirbazı'nı kullanarak bir özel özellik eklemek](#_core_using_classwizard_to_add_a_custom_property), bu uygulama göstermek için CircleOffset özel özelliğini kullanır.  
  
-   Parametreli uygulama  
  
     Parametreli uygulama Özellik Ekleme Sihirbazı tarafından desteklenir. (Bazen özellik dizisi denir) parametreli özellik değerleri kümesi tek bir denetim özelliği üzerinden erişmek için kullanılabilir. Bu uygulama için gönderme eşleme girişi makro `DISP_PROPERTY_PARAM`. Böyle bir uygulama ile ilgili daha fazla bilgi için bkz: [parametreli özellik uygulama](../mfc/mfc-activex-controls-advanced-topics.md) makalede ActiveX denetimleri: Gelişmiş Konular.  
  
##  <a name="_core_using_classwizard_to_add_a_custom_property"></a> Kullanarak bir özel özellik eklemek için özellik Sihirbazı Ekle  
 Aşağıdaki yordamda özel bir özellik Get/Set yöntemleri uygulama kullanan CircleOffset ekleme gösterilmektedir. CircleOffset özel özellik denetimin kullanıcının denetimin sınırlayıcı dikdörtgenini Merkezi'nden daire uzaklığı izin verir. Get/Set yöntemleri dışında uygulaması ile özel özellikler ekleme yordamı çok benzer.  
  
 Bu yordamı, istediğiniz diğer özel özelliklerini eklemek için de kullanılabilir. CircleOffset özellik adı ve parametreleri için özel özellik adınızı değiştirin.  
  
#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak CircleOffset özel özellik eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde denetiminizin kitaplığı düğümünü genişletin.  
  
3.  Arabirim (kitaplık düğümünün İkinci düğüm) denetlemek için kısayol menüsünü açmak için düğümü.  
  
4.  Kısayol menüsünden tıklatın **Ekle** ve ardından **Özellik Ekle**.  
  
     Bu açılır [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md).  
  
5.  İçinde **özellik adı** kutusuna `CircleOffset`.  
  
6.  İçin **uygulama türü**, tıklatın **Get/Set yöntemleri**.  
  
7.  İçinde **özellik türü** kutusunda **kısa**.  
  
8.  Alma ve ayarlama işlevleri için benzersiz adlar yazın veya varsayılan adı kabul edin.  
  
9. **Son**'a tıklayın.  
  
##  <a name="_core_classwizard_changes_for_custom_properties"></a> Özellik Sihirbazı değişiklikleri için özel özellikler ekleme  
 Özellik Ekleme Sihirbazı'nı CircleOffset özel özellik eklediğinizde, üstbilgiye değişiklikleri yapar (. Y) ve uygulama (. Denetim sınıfı CPP) dosyaları.  
  
 Aşağıdaki satırları eklenir. H adlı iki işlevleri bildirme dosyaya `GetCircleOffset` ve `SetCircleOffset`:  
  
 [!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]  
  
 Aşağıdaki satırı, denetimin eklenir. IDL dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]  
  
 Bu satırı CircleOffset özelliği yöntemin konumundan Özellik Ekleme Sihirbazı'ndaki yöntemler ve özellikler listesinde yapılan belirli bir kimlik numarası atar.  
  
 Ayrıca, aşağıdaki satırı gönderme eşlemesine eklenen (içinde. Denetim sınıfı CPP dosyası) denetimin iki işleyici işlevleri CircleOffset özelliğini eşleştirmek için:  
  
 [!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]  
  
 Son olarak, uygulamaları `GetCircleOffset` ve `SetCircleOffset` işlevleri, denetimin sonuna eklenir. CPP dosyası. Çoğu durumda, Get işlevi özelliğinin değeri döndürecek şekilde değiştirir. Set işlevi genellikle önce veya sonra özellik değişikliklerini yürütülmesi gereken kod içerir.  
  
 [!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]  
  
 Özellik Ekleme Sihirbazı'nı otomatik olarak bir çağrı çok eklediği Not [SetModifiedFlag](../mfc/reference/colecontrol-class.md#setmodifiedflag), kümesi işlevinin gövdesini için. Bu işlev çağırma denetimi değiştirilmiş olarak işaretler. Bir denetim değiştirilirse kapsayıcı kaydedildiğinde yeni durumuna kaydedilir. Bu işlev, denetimin kalıcı durumunu, bir parçası olarak kaydedilmiş bir özellik değeri değiştiğinde çağrılmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX denetimleri: yöntemler](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
