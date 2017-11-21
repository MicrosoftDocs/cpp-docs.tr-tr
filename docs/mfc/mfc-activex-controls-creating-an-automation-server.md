---
title: "MFC ActiveX denetimleri: Otomasyon sunucusu oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 56b05c85212630b8e368817006098aeff2ceb832
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>MFC ActiveX Denetimleri: Otomasyon Sunucusu Oluşturma
MFC ActiveX denetimi programlı olarak başka bir uygulamada denetleyen katıştırma ve uygulamadan denetiminde yöntemleri çağırma amacıyla Otomasyon sunucusu olarak geliştirebilirsiniz. Böyle bir denetim bir ActiveX denetimi kapsayıcısı barındırılması kullanılabilir olacaktır.  
  
### <a name="to-create-a-control-as-an-automation-server"></a>Otomasyon sunucusu olarak bir denetim oluşturmak için  
  
1.  [Oluşturma](../mfc/reference/mfc-activex-control-wizard.md) denetimi.  
  
2.  [Yöntemleri eklemek](../mfc/mfc-activex-controls-methods.md).  
  
3.  Geçersiz kılma [IsInvokeAllowed](../mfc/reference/colecontrol-class.md#isinvokeallowed). Daha fazla bilgi için Bilgi Bankası makalesi Q146120 bakın.  
  
4.  Denetim oluşturun.  
  
### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>Otomasyon sunucusu yöntemlere programlı olarak erişmek için  
  
1.  Örneğin bir uygulama oluşturmak, bir [MFC exe](../mfc/reference/mfc-application-wizard.md).  
  
2.  Başında `InitInstance` işlev, aşağıdaki satırı ekleyin:  
  
     [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]  
  
3.  Sınıf Görünümü'nde, proje düğümüne sağ tıklayın ve seçin **typelib sınıfı ekleme** tür kitaplığı içeri aktarmak için.  
  
     Bu projeye .cpp ve dosya adı uzantıları .h dosyaları ekler.  
  
4.  Burada, çağrılacak bir veya daha fazla yöntemleri ActiveX denetiminde başlık dosyasında sınıfının, aşağıdaki satırı ekleyin: `#include filename.h`, burada, dosya adı Tür kitaplığı içeri aktardığınızda, oluşturulan üstbilgi dosyası adıdır.  
  
5.  ActiveX denetiminde yöntemine bir çağrı burada yapılacak işlevindeki denetimin sarmalayıcı sınıfın bir nesnesi oluşturan kodunu ekleyin ve ActiveX nesnesi oluşturun. Örneğin, aşağıdaki MFC kodu başlatır bir `CCirc` denetimi, resim yazısı özelliğini alır ve bir iletişim kutusunda Tamam düğmesine tıklandığında sonucu görüntüler:  
  
     [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]  
  
 Bir uygulamada kullandıktan sonra ActiveX denetimi yöntemleri eklemek, tür kitaplığı içeri aktardığınızda, oluşturulan dosyaları silerek uygulamada denetimi en son sürümünü kullanmaya başlayabilirsiniz. Ardından tür kitaplığı yeniden içeri aktarın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)

