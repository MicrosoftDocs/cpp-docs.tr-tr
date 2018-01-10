---
title: "Etkin belge kapsayıcı uygulaması oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- active document containers [MFC], creating
- MFC COM, active document containment
- applications [MFC], active document container
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 077d15837ed857ac983c3c9f9d4e7853b45aeee5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-active-document-container-application"></a>Etkin Belge Kapsayıcı Uygulaması Oluşturma
Etkin belge kapsayıcı uygulaması oluşturmak için basit ve en önerilen yol, MFC Uygulama Sihirbazı'nı kullanarak bir MFC EXE kapsayıcı uygulama oluşturmak için ardından etkin belge kapsaması destekleyecek şekilde değiştirin.  
  
#### <a name="to-create-an-active-document-container-application"></a>Etkin belge kapsayıcı uygulaması oluşturmak için  
  
1.  Gelen **dosya** menüsünde tıklatın **proje**gelen **yeni** alt.  
  
2.  Sol bölmeden tıklatın **Visual C++** proje türü.  
  
3.  Seçin **MFC uygulaması** sağ bölmesinde.  
  
4.  Proje adı `MyProj`, tıklatın **Tamam**.  
  
5.  Seçin **bileşik belge desteği** sayfası.  
  
6.  Seçin **kapsayıcı** veya **kapsayıcı/tam sunucu** seçeneği.  
  
7.  Seçin **etkin belge kapsayıcısı** onay kutusu.  
  
8.  **Son**'a tıklayın.  
  
9. MFC Uygulama Sihirbazı'nı uygulama ürettikten sonra Çözüm Gezgini kullanarak aşağıdaki dosyaları açın:  
  
    -   MyProjview.cpp  
  
10. MyProjview.cpp içinde aşağıdaki değişiklikleri yapın:  
  
    -   İçinde `CMyProjView::OnPreparePrinting`, işlevi içeriğini aşağıdaki kodla değiştirin:  
  
         [!code-cpp[NVC_MFCDocView#56](../mfc/codesnippet/cpp/creating-an-active-document-container-application_1.cpp)]  
  
     `OnPreparePrinting`yazdırma desteği sağlar. Bu kod değiştirir `DoPreparePrinting`, varsayılan yazdırma hazırlık olduğu.  
  
     Etkin belge kapsaması geliştirilmiş yazdırma düzeni sağlar:  
  
    -   Etkin belgeyi ile ilk çağırabilirsiniz kendi `IPrint` arabirim ve kendisini yazdırmak için söyleyin. Bu, kapsayıcı vardı yazıcı üzerine kapsanan öğesinin bir görüntü oluşturmak önceki OLE kapsama farklıdır `CDC` nesnesi.  
  
    -   Başarısız olursa, kendisi aracılığıyla yazdırmak için kapsanan öğesi söyleyin kendi `IOleCommandTarget` arabirimi  
  
    -   Başarısız olursa, öğenin kendi işleme olun.  
  
     Statik üye işlevleri `COleDocObjectItem::OnPrint` ve `COleDocObjectItem::OnPreparePrinting`, önceki kod içinde uygulandığı şekilde bu geliştirilmiş yazdırma düzeni tanıtıcı.  
  
11. Herhangi bir uygulaması eklemek ve uygulama oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin Belge Kapsaması](../mfc/active-document-containment.md)

