---
title: "ActiveX denetim kapsayıcıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e564ee0c9d8ec47db68c49db1dfcbdc86b393e02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="activex-control-containers"></a>ActiveX Denetim Kapsayıcıları
ActiveX denetimi kapsayıcısı tam olarak ActiveX denetimlerini destekleyen bir kapsayıcı ve bunları kendi windows ya da iletişim kutuları dahil edebilirsiniz. ActiveX denetimi birçok geliştirme projelerinde kullanabileceğiniz bir yeniden kullanılabilir yazılım öğedir. Denetimler veritabanlarına erişim, veri izlemek ve uygulamalarınızı içindeki çeşitli seçimleri yapmak, uygulamanızın kullanıcı izin verir. ActiveX denetimleri hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md).  
  
 Denetimi kapsayıcıları genellikle iki projede biçimlerde:  
  
-   İletişim kutuları ve iletişim kutusunda bir ActiveX denetimini yerde kullanıldığı iletişim benzeri windows form görünümleri gibi.  
  
-   Burada bir ActiveX denetimi, bir uygulamada Windows, araç çubuğundaki ya da kullanıcı penceresinde başka bir konuma kullanılır.  
  
 ActiveX denetimi kapsayıcısı denetimi yoluyla etkileşime açığa [yöntemleri](../mfc/mfc-activex-controls-methods.md) ve [özellikleri](../mfc/mfc-activex-controls-properties.md). Bu yöntem ve erişilebildiğini ve denetim kapsayıcı tarafından değiştirilmiş, özellikleri, ActiveX denetimi kapsayıcısı projesinde sarmalayıcı sınıfı aracılığıyla erişilir. Katıştırılmış ActiveX denetimi da kapsayıcıyla (gönderen) tetikleme etkileşim kurabilen [olayları](../mfc/mfc-activex-controls-events.md) bir eylem oluştu kapsayıcı bildirir. Denetimi kapsayıcısı veya bu bildirimler yapması seçebilirsiniz.  
  
 Ek makaleleri bir ActiveX denetimi kapsayıcısı projesine Visual C++ ile oluşturulmuş ActiveX denetimi kapsayıcıları temel uygulamasını sorunları oluşturmasına birkaç konuları ele alınmıştır:  
  
-   [MFC ActiveX denetimi kapsayıcısı oluşturma](../mfc/reference/creating-an-mfc-activex-control-container.md)  
  
-   [ActiveX denetimleri için kapsayıcılar](../mfc/containers-for-activex-controls.md)  
  
-   [ActiveX denetim kapsayıcıları: ActiveX denetimi kapsamasını el ile etkinleştirme](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)  
  
-   [ActiveX denetim kapsayıcıları: bir denetim kapsayıcısı uygulamasına denetim ekleme](../mfc/inserting-a-control-into-a-control-container-application.md)  
  
-   [ActiveX denetim kapsayıcıları: bir üye değişkenine ActiveX denetimi bağlama](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)  
  
-   [ActiveX denetim kapsayıcıları: ActiveX işleme olayları denetleme](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)  
  
-   [ActiveX denetim kapsayıcıları: Görüntüleme ve denetim özelliklerini değiştirme](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)  
  
-   [ActiveX denetim kapsayıcıları: Bir ActiveX denetim kapsayıcısındaki ActiveX denetimlerini programlama](../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
-   [ActiveX denetim kapsayıcıları: İletişim kutusu dışındaki kapsayıcılarda denetimleri kullanma](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)  
  
 Bir iletişim kutusuna ActiveX denetimlerini kullanma hakkında daha fazla bilgi için bkz: [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) Konular.  
  
 Visual C++ ve MFC ActiveX denetim sınıfları kullanarak ActiveX denetimleri geliştirme ayrıntılarını açıklayan makaleleri bir listesi için bkz: [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md). Makaleleri işlevsel kategorilere göre gruplandırılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)

