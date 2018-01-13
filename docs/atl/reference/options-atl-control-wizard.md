---
title: "ATL Denetim Sihirbazı, seçenekleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.control.options
dev_langs: C++
helpviewer_keywords: ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 60cc90ca5d5c374c223f9fe350d1a6a7357329ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="options-atl-control-wizard"></a>Seçenekler, ATL Denetim Sihirbazı
"Arama sonuçları" Özet buraya ekleyin.  
  
 Oluşturmakta olduğunuz denetim türünü ve içerdiği arabirimi desteği düzeyini tanımlamak için sihirbazın bu sayfayı kullanın.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Denetim türü**  
 Oluşturmak istediğiniz denetim türü.  
  
-   **Standart denetim: bir ActiveX denetimi.**  
  
-   **Bileşik Denetim**: (bir iletişim kutusu benzer) içeren bir ActiveX denetimi diğer ActiveX denetimleri veya Windows denetimleri. Bileşik Denetim aşağıdakileri içerir:  
  
    -   Bileşik Denetim uygulayan iletişim kutusu için bir şablon.  
  
    -   Bir özel kaynak, kayıt defteri çağrıldığında bileşik denetim otomatik olarak kaydeder.  
  
    -   Bileşik Denetim uygulayan bir C++ sınıf.  
  
    -   Bileşik denetim tarafından kullanıma sunulan bir COM arabirimi.  
  
    -   Bileşik Denetim içeren bir HTML test sayfası.  
  
     Varsayılan olarak, bu denetim ayarlar [CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) doğru şekilde, bu pencereli denetim olduğunu belirtmek için. Bir havuz harita uygular. Daha fazla bilgi için bkz: [DHTML denetimi için destek](../../atl/atl-support-for-dhtml-controls.md).  
  
-   **DHTML denetimi**: bir ATL DHTML denetimi HTML kullanarak kullanıcı arabirimi belirtir. DHTML UI sınıfı COM eşlemesi içerir. Varsayılan olarak, bu denetim ayarlar [CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) doğru şekilde, bu pencereli denetim olduğunu belirtmek için.  
  
     Daha fazla bilgi için bkz: [DHTML denetimi proje öğelerini tanımlama](../../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
 **En az denetim**  
 Çoğu kapsayıcıları tarafından kesinlikle gerekli arabirimleri destekler. Ayarlayabileceğiniz **en az denetim** herhangi bir denetim türü için: en az bir standart denetim, en az bir bileşik denetim veya en az bir DHTML denetimi oluşturabilirsiniz.  
  
 **Toplama**  
 Oluşturmakta olduğunuz Denetim toplama desteği ekler. Daha fazla bilgi için bkz: [toplama](../../atl/aggregation.md).  
  
-   **Evet**: kümelenebilir bir denetim oluşturun.  
  
-   **Hayır**: toplanamaz bir denetim oluşturun.  
  
-   **Yalnızca**: yalnızca toplama oluşturulabilir bir denetim oluşturun.  
  
 **İş parçacığı modeli**  
 İş parçacığı modelini denetimi tarafından kullanılan belirtir.  
  
-   **Tek**: denetimi yalnızca birincil COM iş parçacığı içinde çalışır.  
  
-   **Grup**: denetim herhangi tek iş parçacığı grubu oluşturulabilir. Varsayılan.  
  
 **Arabirimi**  
 Bu denetim kapsayıcıya kullanıma sunan arabirim türü.  
  
-   **Çift**: özellikler ve yöntemler yoluyla kullanıma sunan bir arabirim oluşturur `IDispatch` ve VTBL aracılığıyla doğrudan.  
  
-   **Özel**: bir VTBL aracılığıyla doğrudan yöntemleri gösteren bir arabirim oluşturur.  
  
     Seçerseniz **özel**, denetimin belirtebilirsiniz sonra **otomasyon uyumlu**. Seçerseniz **otomasyon uyumlu**, sihirbaz ekler sonra [oleautomation](../../windows/oleautomation.md) IDL arabiriminde özniteliğini ve arabirim oleaut32.dll içinde Evrensel sıralayıcı tarafından sıralanabilir. Bkz: [hazırlama ayrıntıları](http://msdn.microsoft.com/library/windows/desktop/ms692621) daha fazla bilgi için Windows SDK'sındaki.  
  
     Ayrıca, seçerseniz **otomasyon uyumlu**, denetimdeki tüm yöntemleri için tüm parametreleri olmalıdır **değişken** uyumlu.  
  
 **Destek**  
 Ek çeşitli destek denetimi için ayarlar.  
  
-   **Bağlantı noktaları**: sağlar, nesne için bağlantı noktaları, nesnenin sınıf türetin yaparak [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) ve kaynak arabirimi kullanıma sunmak etkinleştirilebilir.  
  
-   **Lisanslı**: denetlemek için destek ekler [lisans](http://msdn.microsoft.com/library/windows/desktop/ms690543). Lisanslı Denetimler, yalnızca istemci makinede doğru lisans varsa barındırılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Denetimi Sihirbazı](../../atl/reference/atl-control-wizard.md)

