---
title: ActiveX denetim kapsayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73496f892cc55ef59b2d84228ae9ae0416d3e8a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338981"
---
# <a name="activex-control-containers"></a>ActiveX Denetim Kapsayıcıları
ActiveX denetimi kapsayıcısı tam olarak ActiveX denetimlerini destekleyen bir kapsayıcı ve bunları kendi windows ya da iletişim kutuları dahil edebilirsiniz. ActiveX denetimi birçok geliştirme projelerinde kullanabileceğiniz bir yeniden kullanılabilir yazılım öğedir. Denetimler veritabanlarına erişim, veri izlemek ve uygulamalarınızı içindeki çeşitli seçimleri yapmak, uygulamanızın kullanıcı izin verir. ActiveX denetimleri hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md).  
  
 Denetimi kapsayıcıları genellikle iki projede biçimlerde:  
  
-   İletişim kutuları ve iletişim kutusunda bir ActiveX denetimini yerde kullanıldığı iletişim benzeri windows form görünümleri gibi.  
  
-   Burada bir ActiveX denetimi, bir uygulamada Windows, araç çubuğundaki ya da kullanıcı penceresinde başka bir konuma kullanılır.  
  
 ActiveX denetimi kapsayıcısı denetimi yoluyla etkileşime açığa [yöntemleri](../mfc/mfc-activex-controls-methods.md) ve [özellikleri](../mfc/mfc-activex-controls-properties.md). Bu yöntem ve erişilebildiğini ve denetim kapsayıcı tarafından değiştirilmiş, özellikleri, ActiveX denetimi kapsayıcısı projesinde sarmalayıcı sınıfı aracılığıyla erişilir. Katıştırılmış ActiveX denetimi da kapsayıcıyla (gönderen) tetikleme etkileşim kurabilen [olayları](../mfc/mfc-activex-controls-events.md) bir eylem oluştu kapsayıcı bildirir. Denetimi kapsayıcısı veya bu bildirimler yapması seçebilirsiniz.  
  
 Ek makaleleri bir ActiveX denetimi kapsayıcısı projesine Visual C++ ile oluşturulmuş ActiveX denetimi kapsayıcıları temel uygulamasını sorunları oluşturmasına birkaç konuları ele alınmıştır:  
  
-   [MFC ActiveX Denetimi Kapsayıcısı Oluşturma](../mfc/reference/creating-an-mfc-activex-control-container.md)  
  
-   [ActiveX Denetimleri için Kapsayıcılar](../mfc/containers-for-activex-controls.md)  
  
-   [ActiveX Denetimi Kapsayıcıları: ActiveX Denetimi Kapsamasını El İle Etkinleştirme](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)  
  
-   [ActiveX Denetim Kapsayıcıları: Bir Denetim Kapsayıcısı Uygulamasına Denetim Ekleme](../mfc/inserting-a-control-into-a-control-container-application.md)  
  
-   [ActiveX Denetim Kapsayıcıları: Bir Üye Değişkenine ActiveX Denetimi Bağlama](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)  
  
-   [ActiveX denetim kapsayıcıları: ActiveX işleme olayları denetleme](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)  
  
-   [ActiveX Denetim Kapsayıcıları: Denetim Özelliklerini Görüntüleme ve Değiştirme](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)  
  
-   [ActiveX Denetim Kapsayıcıları: Bir ActiveX Denetim Kapsayıcısındaki ActiveX Denetimlerini Programlama](../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
-   [ActiveX Denetim Kapsayıcıları: İletişim Kutusu Dışındaki Kapsayıcılarda Denetimleri Kullanma](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)  
  
 Bir iletişim kutusuna ActiveX denetimlerini kullanma hakkında daha fazla bilgi için bkz: [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) Konular.  
  
 Visual C++ ve MFC ActiveX denetim sınıfları kullanarak ActiveX denetimleri geliştirme ayrıntılarını açıklayan makaleleri bir listesi için bkz: [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md). Makaleleri işlevsel kategorilere göre gruplandırılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

