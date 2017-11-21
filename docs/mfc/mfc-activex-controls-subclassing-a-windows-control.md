---
title: "MFC ActiveX denetimleri: bir Windows denetimini alt sınıf yapma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- precreatewindow
- IsSubclassed
dev_langs: C++
helpviewer_keywords:
- OnDraw method, MFC ActiveX controls
- subclassing
- DoSuperclassPaint method [MFC]
- subclassing Windows controls
- subclassing, Windows controls
- reflected messages, in ActiveX controls
- PreCreateWindow method, overriding
- MFC ActiveX controls [MFC], subclassed controls
- MFC ActiveX controls [MFC], creating
- IsSubclassed method [MFC]
ms.assetid: 3236d4de-401f-49b7-918d-c84559ecc426
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5532a5ea76bbdde619829548c01c2d057f3cbc28
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC ActiveX Denetimleri: Bir Windows Denetimini Alt Sınıf Yapma
Bu makalede bir ActiveX denetimi oluşturmak için ortak bir Windows denetimini alt sınıf yapma işlemi açıklanmaktadır. Mevcut bir Windows sınıflara denetim bir ActiveX denetimini geliştirmek için bir hızlı yoludur. Yeni Denetim boyama ve fare tıklamalarına yanıt gibi altsınıflanmış Windows denetimi yeteneklerini sahip olur. MFC ActiveX denetimleri örnek [düğmesini](../visual-cpp-samples.md) bir Windows denetimini alt sınıf yapma, bir örnek verilmiştir.  
  
 Bir Windows denetimini alt sınıf için aşağıdaki görevleri tamamlayın:  
  
-   [COleControl IsSubclassedControl ve PreCreateWindow üye işlevlerini geçersiz kılma](#_core_overriding_issubclassedcontrol_and_precreatewindow)  
  
-   [OnDraw üye işlevi değiştirin](#_core_modifying_the_ondraw_member_function)  
  
-   [Denetime yansıtılan tüm ActiveX denetim iletileri (OCM) işleme](#_core_handling_reflected_window_messages)  
  
    > [!NOTE]
    >  Denetim kullanarak sınıflandırma seçerseniz bu iş çoğunu sizin için ActiveX Denetim Sihirbazı tarafından yapılır **üst pencere sınıfı seçin** aşağı açılan listede **denetim ayarlarını** sayfası.  
  
 Bilgi Bankası makalesi Q243454 daha fazla bilgi için bir denetim sınıflara bakın.  
  
##  <a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a>IsSubclassedControl ve PreCreateWindow geçersiz kılma  
 Geçersiz kılmak için `PreCreateWindow` ve `IsSubclassedControl`, kodu aşağıdaki satırları ekleyin `protected` denetim sınıf bildirimi bölümünü:  
  
 [!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]  
  
 Denetim uygulama dosyasında (. CPP) iki geçersiz kılınan işlevler uygulamak için kod aşağıdaki satırları ekleyin:  
  
 [!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]  
  
 Bu örnekte, Windows Denetim düğmesini bildirimi belirtilen `PreCreateWindow`. Ancak, tüm standart Windows denetimleri sınıflandırma. Standart Windows denetimleri hakkında daha fazla bilgi için bkz: [denetimleri](../mfc/controls-mfc.md).  
  
 Bir Windows denetimini alt sınıf yapma, belirli pencere stili belirtmek isteyebilirsiniz (**WS_**) veya genişletilmiş pencere stili (**WS_EX_**) denetimin penceresi oluşturmada kullanılacak bayrakları. Bu parametreler için değerler ayarlayabileceğiniz `PreCreateWindow` değiştirerek üye işlevi **cs.style** ve **cs.dwExStyle** yapısı alanları. Bu alanların değişiklikler yapılan kullanarak bir `OR` sınıfı tarafından ayarlanan varsayılan bayrakları korumak için işlemi `COleControl`. Örneğin, DÜĞME denetimi denetimini alt sınıf yapma ve denetimi bir onay kutusu olarak görünmesini istiyorsanız uygulamasına aşağıdaki kod satırını ekleyin `CSampleCtrl::PreCreateWindow`, return deyiminin önce:  
  
 [!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]  
  
 Bu işlem ekler **BS_CHECKBOX** stil bayrak varsayılan stil bayrağı bırakarak (**WS_CHILD**) sınıfının `COleControl` kalır.  
  
##  <a name="_core_modifying_the_ondraw_member_function"></a>OnDraw üye fonksiyonu değiştirme  
 Karşılık gelen Windows denetimi aynı görünüme tutmak için altsınıflanmış denetiminizi istiyorsanız `OnDraw` üye işlevi denetimi için sadece bir çağrı içermelidir `DoSuperclassPaint` aşağıdaki örnekteki gibi üye fonksiyonu:  
  
 [!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]  
  
 `DoSuperclassPaint` Tarafından uygulanan üye işlevi `COleControl`, Windows denetiminin pencere yordamı sınırlayıcı dikdörtgenini içinde belirtilen aygıt bağlamında denetimi çizmek için kullanır. Bile etkin olmadığı zaman bu denetimi görünür hale getirir.  
  
> [!NOTE]
>  `DoSuperclassPaint` Üye işlevi yalnızca bir cihaz bağlamı olarak geçirilecek izin denetim türleri ile çalışır **wParam** , bir `WM_PAINT` ileti. Bu standart Windows denetimlerin gibi içerir **SCROLLBAR** ve **düğmesini**ve tüm ortak denetimleri. Bu davranış desteklemeyen denetimleri için etkin olmayan denetimi düzgün görüntülemek için kendi kodunuzu vermeniz gerekir.  
  
##  <a name="_core_handling_reflected_window_messages"></a>Yansımış pencere iletileri işleme  
 Windows denetimleri, genellikle kendi üst penceresine belirli pencere iletileri gönderir. Gibi bunlardan bazıları iletileri **WM_COMMAND**, kullanıcı tarafından bir eylem bildirim sağlar. Diğerleri gibi `WM_CTLCOLOR`, üst penceresinden bilgi almak için kullanılır. ActiveX denetimi genellikle diğer yöntemlerle üst pencere ile iletişim kurar. Bildirimleri (olay bildirimleri gönderme) olaylarını tetikleme tarafından bildirilir ve denetimi kapsayıcısı hakkında bilgi kapsayıcının ortam özelliklerine erişme tarafından alınır. Bu iletişim teknikler olmadığı için denetim tarafından gönderilen tüm pencere iletileri işlemek için ActiveX denetimi kapsayıcıları beklenmez.  
  
 Kapsayıcı altsınıflanmış Windows Denetim tarafından gönderilen pencere iletileri almasını önlemek için `COleControl` denetimin üst öğe olarak hizmet vermek için fazladan bir pencere oluşturur. Alt sınıfların Windows denetlemek ve aynı boyut ve konum denetimi penceresi sahip yalnızca bir ActiveX denetimi için bir "reflector," olarak adlandırılan bu ek pencere oluşturulur. Reflector penceresi belirli pencere iletileri durdurur ve bunları denetime geri gönderir. Alt pencere yordamı, denetimi bu yansımış iletiler işleyebilir ve bir ActiveX denetimi (örneğin, bir olay tetikleme) için uygun eylemleri gerçekleştirerek. Bkz: [yansımış pencere iletisi kimlikleri](../mfc/reflected-window-message-ids.md) ilerlemesinden windows listesi için iletileri ve bunların karşılık gelen yansımış iletileri.  
  
 ActiveX denetimi kapsayıcısı gereksinimini ileti yansıması kendisini gerçekleştirmek için tasarlanmış olabilir `COleControl` reflector penceresi ve çalışma zamanında altsınıflanmış Windows denetimi için ek yükü azaltarak oluşturmak için. `COleControl`MessageReflect ortam özelliği değerini denetleyerek kapsayıcıyı bu yeteneği destekleyip desteklemediğini algılar **doğru**.  
  
 Yansımış pencere iletisi işlemek için Denetim İleti eşlemesi için bir giriş ekleyin ve bir işleyici işlevi uygulamak. Yansımış iletiler iletileri Windows tarafından tanımlanan standart kümesinin bir parçası olmadığından, bu tür ileti işleyicileri ekleme sınıf görünümü desteklemez. Ancak, bir işleyici el ile eklemek zor değildir.  
  
 Eklemek için bir ileti işleyicisini yansımış pencere iletisi için el ile aşağıdakileri yapın:  
  
-   Control sınıfı. H dosyasına bir işleyici işlevi bildirin. İşlev dönüş türü olmalıdır **LRESULT** ve türleriyle iki parametre **WPARAM** ve **LPARAM**sırasıyla. Örneğin:  
  
     [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]  
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]  
  
-   Control sınıfı. CPP dosya, ekleme bir `ON_MESSAGE` ileti eşlemesi girişe. Bu girdi parametrelerinin İleti tanımlayıcısı ve işleyici işlevin adı olması gerekir. Örneğin:  
  
     [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]  
  
-   De. CPP dosya uygulamak **OnOcmCommand** yansıtılan iletiyi işlemek için üye işlevi. **WParam** ve **lParam** parametre özgün pencere iletisi aynı değildir.  
  
 MFC ActiveX denetimleri örneğe bakın iletileri işlenir nasıl bir örnek yansıtılan, [düğmesini](../visual-cpp-samples.md). Bunu gösteren bir **OnOcmCommand** algılar işleyici **BN_CLICKED** bildirim kodu ve tetikleme tarafından yanıt (gönderen) Click olayını.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)

