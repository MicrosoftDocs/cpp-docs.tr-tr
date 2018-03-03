---
title: "ActiveX denetim kapsayıcıları: İletişim kutusu dışındaki kapsayıcılarda denetimleri kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c380d0a525c2f026054ebae1812450c4d4634c1e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>ActiveX Denetim Kapsayıcıları: İletişim Kutusu Dışındaki Kapsayıcılarda Denetimleri Kullanma
Bazı bir SDI gibi uygulamaları veya MDI uygulama uygulama penceresinde bir denetim eklemek istersiniz. **Oluşturma** Visual C++ tarafından eklenen sarmalayıcı sınıfının üye işlevini oluşturabilirsiniz denetim örneği dinamik olarak bir iletişim kutusu gerek kalmadan.  
  
 **Oluşturma** üye işlevi aşağıdaki parametreleri vardır:  
  
 `lpszWindowName`  
 (Varsa) denetimin metin veya resim yazısı özelliğini görüntülenecek metni için bir işaretçi.  
  
 `dwStyle`  
 Windows stilleri. Tam bir listesi için bkz: [CWnd::CreateControl](../mfc/reference/cwnd-class.md#createcontrol).  
  
 `rect`  
 Denetimin boyutunu ve konumunu belirtir.  
  
 `pParentWnd`  
 Denetimin ana penceresinde, genellikle belirten bir `CDialog`. Değil olmalıdır **NULL**.  
  
 `nID`  
 Denetim Kimliği belirtir ve kapsayıcı tarafından denetimine başvurmak için kullanılabilir.  
  
 Dinamik olarak bir ActiveX denetimi oluşturmak için bu işlevi kullanarak bir örnek bir SDI uygulama form görünümünde olacaktır. Daha sonra denetimi örneği oluşturabilirsiniz `WM_CREATE` uygulamanın işleyici.  
  
 Bu örnek için `CMyView` ana görünüm sınıfı `CCirc` sarmalayıcı sınıfı ve CIRC. H ise üstbilgi (. H) sarmalayıcı sınıfı dosyası.  
  
 Bu özellik uygulama dört adımlı bir işlemdir.  
  
### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>Dinamik olarak bir iletişim kutusu dışındaki penceresinde bir ActiveX denetimi oluşturulamıyor  
  
1.  CIRC. Ekle CMYVIEW H. H, hemen önce `CMyView` sınıf tanımı:  
  
     [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]  
  
2.  Üye değişkeni ekleme (türünde `CCirc`) korumalı bölümüne `CMyView` sınıf tanımının CMYVIEW içinde bulunur. Y:  
  
     [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]  
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]  
  
3.  Ekleme bir `WM_CREATE` sınıfı için ileti işleyicisi `CMyView`.  
  
4.  İşleyici işlevindeki `CMyView::OnCreate`, denetimin çağırmaya `Create` kullanarak işlev **bu** işaretçi üst pencere olarak:  
  
     [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]  
  
5.  Projeyi yeniden oluşturun. Uygulamanın görünümü oluşturulduğunda Dai denetim dinamik olarak oluşturulur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

