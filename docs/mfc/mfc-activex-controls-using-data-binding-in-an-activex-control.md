---
title: 'MFC ActiveX denetimleri: ActiveX denetiminde veri bağlama işlemini kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- bindable
- requestedit
- defaultbind
- displaybind
- dispid
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], data binding
- data binding [MFC], MFC ActiveX controls
- data-bound controls [MFC], MFC ActiveX controls
- controls [MFC], data binding
- bound controls [MFC], MFC ActiveX
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab5195cc2381e515688182ad73452b07afd06b98
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353279"
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetiminde Veri Bağlama İşlemini Kullanma
ActiveX denetimleri daha güçlü kullanımlarını bir veritabanında belirli bir alanla bağlamak için denetimin özelliğini sağlayan veri bağlama biridir. Bir kullanıcı bu bağlı özellik verilerde değişiklik yaptığında denetim veritabanı ve kayıt alanını güncelleştirilmesi istekleri bildirir. Veritabanı ardından Denetim başarı veya hata isteğin bildirir.  
  
 Bu makalede göreviniz denetim tarafında yer almaktadır. Veri bağlama etkileşimleri veritabanı ile uygulama denetimi kapsayıcısı sorumluluğundadır. Kapsayıcı içinde veritabanı etkileşimlerini yönetme bu belgenin kapsamında değildir. Veri bağlama denetimi nasıl hazırlamanız bu makalenin geri kalanında açıklanmıştır.  
  
 ![Bir veri kavramsal diyagramı&#45;bağlı denetim](../mfc/media/vc374v1.gif "vc374v1")  
Veri bağlama denetimi kavramsal diyagramı  
  
 `COleControl` Sınıfı, veri uygulamak için kolay bir işlem bağlama olun iki üye işlevleri sağlar. İlk işlev [BoundPropertyRequestEdit](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit), özellik değeri değiştirme izni istemek için kullanılır. [BoundPropertyChanged](../mfc/reference/colecontrol-class.md#boundpropertychanged), ikinci işlev, özellik değeri başarıyla değiştirildikten sonra çağrılır.  
  
 Bu makalede aşağıdaki konuları içerir:  
  
-   [Bağlanabilir stok özellik oluşturma](#vchowcreatingbindablestockproperty)  
  
-   [Bağlanabilir Get/Set yöntemi oluşturma](#vchowcreatingbindablegetsetmethod)  
  
##  <a name="vchowcreatingbindablestockproperty"></a> Bağlanabilir stok özellik oluşturma  
 İsteyeceksiniz daha büyük bir olasılıkla olmasına rağmen bir veriye bağlı stok özellik oluşturmak mümkün bir [bağlanabilirse get/set yöntemi](#vchowcreatingbindablegetsetmethod).  
  
> [!NOTE]
>  Stok özellikleri sahip **bağlanabilirse** ve **requestedit** varsayılan öznitelikleri.  
  
#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak bağlanabilir stok özellik eklemek için  
  
1.  Proje kullanmaya başlamak [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md).  
  
2.  Denetlemek için arabirim düğümünü sağ tıklatın.  
  
     Bu kısayol menüsünü açar.  
  
3.  Kısayol menüsünden tıklatın **Ekle** ve ardından **Özellik Ekle**.  
  
4.  Girişlerden biri seçin **özellik adı** aşağı açılan liste. Örneğin, seçebileceğiniz **metin**.  
  
     Çünkü **metin** stok özellik **bağlanabilir** ve **requestedit** öznitelikleri zaten denetlenir.  
  
5.  Aşağıdaki onay kutularından seçin **IDL öznitelikleri** sekmesi: **displaybind** ve **defaultbind** projenin özellik tanımını öznitelikler eklemek için. IDL dosyası. Bu öznitelikler denetimi kullanıcıya görünen yapabilir ve stok özellik varsayılan bağlanabilirse özelliği.  
  
 Bu noktada, denetiminiz bir veri kaynağından görüntüleyebilirsiniz, ancak kullanıcı veri alanlarını güncelleştirme mümkün olmayacaktır. Ayrıca verileri güncelleştirmek, değişiklik yapabilmek için denetiminizi istiyorsanız `OnOcmCommand` [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) işlevi aşağıdaki gibi aramak için:  
  
 [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]  
  
 Şimdi denetimi kaydedeceksiniz proje oluşturabilirsiniz. Bir iletişim kutusu denetimi eklediğinizde **veri alanı** ve **veri kaynağı** özellikler eklendi ve artık bir veri kaynağı ve Denetimde görüntülenecek alan seçebilirsiniz.  
  
##  <a name="vchowcreatingbindablegetsetmethod"></a> Bağlanabilir Get/Set yöntemi oluşturma  
 Bir veri yöntemi get/set bağlama ek olarak, ayrıca oluşturabileceğiniz bir [bağlanabilirse stok özellik](#vchowcreatingbindablestockproperty).  
  
> [!NOTE]
>  Bu yordamı, bir Windows denetimini alt proje bir ActiveX denetimi olduğunu varsayar.  
  
#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak bağlanabilir get/set yöntemi eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Üzerinde **denetim ayarlarını** sayfasında, bir alt kümesi için denetimi için pencere sınıfı seçin. Örneğin, bir düzenleme denetimini alt sınıf isteyebilirsiniz.  
  
3.  Denetiminizin proje yükleyin.  
  
4.  Denetlemek için arabirim düğümünü sağ tıklatın.  
  
     Bu kısayol menüsünü açar.  
  
5.  Kısayol menüsünden tıklatın **Ekle** ve ardından **Özellik Ekle**.  
  
6.  Özellik adı yazın **özellik adı** kutusu. Kullanım `MyProp` Bu örnek için.  
  
7.  Bir veri türünden seçin **özellik türü** aşağı açılan liste kutusu. Kullanım **kısa** Bu örnek için.  
  
8.  İçin **uygulama türü**, tıklatın **Get/Set yöntemleri**.  
  
9. IDL öznitelikleri sekmesinden aşağıdaki onay kutularını seçin: **bağlanabilirse**, **requestedit**, **displaybind**, ve **defaultbind** eklemek için Projenin özellik tanımını öznitelikleri. IDL dosyası. Bu öznitelikler denetimi kullanıcıya görünen yapabilir ve stok özellik varsayılan bağlanabilirse özelliği.  
  
10. **Son**'a tıklayın.  
  
11. Gövdesini değiştirmek `SetMyProp` aşağıdaki kodu içeren işlev:  
  
     [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]  
  
12. Geçirilen parametre `BoundPropertyChanged` ve `BoundPropertyRequestEdit` işlevleri id() özniteliği için bir özellik için geçirilen parametre özelliği DISPID;. IDL dosyası.  
  
13. Değiştirme [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) aşağıdaki kodu içerecek şekilde işlev:  
  
     [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]  
  
14. Değiştirme `OnDraw` aşağıdaki kodu içeren işlev:  
  
     [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]  
  
15. Üye değişkenleri aşağıdaki tanımları (oluşturucular) üstbilgi dosyası denetim sınıfınıza üstbilgi dosyası ortak bölümüne ekleyin:  
  
     [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]  
  
16. Son satırına aşağıdaki satırı olun `DoPropExchange` işlevi:  
  
     [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]  
  
17. Değiştirme `OnResetState` aşağıdaki kodu içeren işlev:  
  
     [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]  
  
18. Değiştirme `GetMyProp` aşağıdaki kodu içeren işlev:  
  
     [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]  
  
 Şimdi denetimi kaydedeceksiniz proje oluşturabilirsiniz. Bir iletişim kutusu denetimi eklediğinizde **veri alanı** ve **veri kaynağı** özellikler eklendi ve artık bir veri kaynağı ve Denetimde görüntülenecek alan seçebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)   

