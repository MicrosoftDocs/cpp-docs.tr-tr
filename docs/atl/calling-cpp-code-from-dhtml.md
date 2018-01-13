---
title: DHTML arama C++ kodunu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e2d0da431249ef886ceca1e2b7f6cbfc99418dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="calling-c-code-from-dhtml"></a>DHTML C++ kodu çağırma
DHTML denetimi Test kapsayıcısı veya Internet Explorer gibi bir kapsayıcıda barındırılabilir. Bkz: [test özellikleri ve olayları Test kapsayıcısı ile](../mfc/testing-properties-and-events-with-test-container.md) Test kapsayıcısı erişim hakkında bilgi için.  
  
 Denetimi barındırma kapsayıcı normal denetimi arabirimleri kullanarak denetimi ile iletişim kurar. DHTML "C++ kodunuzu ve HTML kaynağınız ile iletişim kurmak için kullanıcı Arabirimi" ile biten gönderme arabirimini kullanır. İçinde [ATL DHTML denetimi değiştirme](../atl/modifying-the-atl-dhtml-control.md), bu farklı arabirimleri tarafından çağrılacak yöntemler ekleme alıştırma yapabilirsiniz.  
  
 DHTML C++ kodu çağırma bir örnek görmek için [DHTML denetimi oluşturma](../atl/creating-an-atl-dhtml-control.md) ATL Denetim Sihirbazı'nı kullanarak ve üstbilgi dosyası ve HTML dosyası kodu inceleyin.  
  
## <a name="declaring-webbrowser-methods-in-the-header-file"></a>Üst bilgi dosyasını WebBrowser yöntemleri bildirme  
 DHTML UI C++ yöntemleri çağırmak için denetiminizin UI arabirim yöntemleri eklemeniz gerekir. Örneğin, C++ yöntemi ATL Denetim Sihirbazı tarafından oluşturulan üst bilgi dosyasını içeren `OnClick`, sihirbaz tarafından oluşturulan denetim UI arabiriminin üyesi olduğu.  
  
 İncelemek `OnClick` denetimin .h dosyasında:  
  
 [!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]  
  
 İlk parametre `pdispBody`, gövde nesnesinin dağıtma arabirimi bir işaretçidir. İkinci parametre `varColor`, denetimine uygulamak için rengi tanımlar.  
  
## <a name="calling-c-code-in-the-html-file"></a>HTML dosyasında C++ kodu çağırma  
 Üstbilgi dosyası WebBrowser yöntemlerinde bildirdikten sonra yöntemleri HTML dosyasından çağırabilirsiniz. HTML dosyasındaki ATL Denetim Sihirbazı'nı üç Windows gönderme yöntemlerini ekler dikkat edin: üç `OnClick` denetim arka plan rengini değiştirmek için iletileri gönderme yöntemleri.  
  
 HTML dosyasındaki yöntemlerden birini inceleyin:  
  
 `<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`  
  
 Yukarıdaki penceresi dış yöntem, HTML kodunda `OnClick`, düğmesi etiketi bir parçası olarak adlandırılır. Yöntemi iki parametreye sahiptir: `theBody`, HTML belgenin gövdesi başvuruyor ve `"red"`, düğmesine tıklandığında denetimin arka plan rengi kırmızı değiştirilecek gösterir. `Red` Etiketi aşağıdaki olduğu düğmenin etiketi.  
  
 Bkz: [ATL DHTML denetimi değiştirme](../atl/modifying-the-atl-dhtml-control.md) kendi yöntemleri sağlama hakkında daha fazla bilgi için. Bkz: [DHTML denetimi proje öğelerini tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md) HTML dosyası hakkında daha fazla bilgi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DHTML denetimi için destek](../atl/atl-support-for-dhtml-controls.md)

