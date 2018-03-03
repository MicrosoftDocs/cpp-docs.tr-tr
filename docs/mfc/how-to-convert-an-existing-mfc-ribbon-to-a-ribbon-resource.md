---
title: "Nasıl yapılır: varolan bir MFC şeridini Şerit kaynağına dönüştürme | Microsoft Docs"
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
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7cb0d5d80edd52a85834963d030e35eef96d718
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>Nasıl yapılır: Varolan Bir MFC Şeridini Şerit Kaynağına Dönüştürme
Şerit kaynakları görselleştirme, değiştirmek ve bakımını el ile kodlanmış Şerit kolaydır. Bu konuda, bir MFC projesine el ile kodlanmış bir Şerit Şerit kaynağına dönüştürme açıklar.  
  
 Örneğin, MFC Şerit sınıfları kullanan kodu sahip varolan bir MFC projesine olmalıdır [CMFCRibbonBar sınıfı](../mfc/reference/cmfcribbonbar-class.md).  
  
### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>Bir MFC şeridini Şerit kaynağına dönüştürme  
  
1.  Visual Studio'da, var olan bir MFC projesinde CMFCRibbonBar nesne burada başlatılmış kaynak dosyasını açın. Genellikle, mainfrm.cpp dosyasıdır. Şerit için başlatma koddan sonra aşağıdaki kodu ekleyin.  
  
 ```  
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");

 ```  
  
     Dosyayı kaydedin ve kapatın.  
  
2.  Derleme ve MFC uygulamasını çalıştırın ve ardından RibbonOutput.txt Not Defteri'nde açın ve içeriğini kopyalayın.  
  
3.  Visual Studio'da üzerinde **proje** menüsünde tıklatın **kaynak ekleme**. İçinde **kaynak ekleme** iletişim kutusunda **Şerit** ve ardından **yeni**.  
  
     Visual Studio Şerit kaynağı oluşturur ve Tasarım görünümünde açılır. Görüntülenen IDR_RIBBON1 Şerit kaynak kimliğidir **kaynak görünümü**. Şerit ribbon1.mfcribbon ms XML dosyasında tanımlanır.  
  
4.  Visual Studio'da ribbon1.mfcribbon ms açın, içeriğini silin ve ardından daha önce kopyaladığınız RibbonOutput.txt içeriğini yapıştırın. Kaydedin ve ribbon1.mfcribbon ms kapatın.  
  
5.  Yeniden CMFCRibbonBar nesne nerede başlatılır kaynak dosyasını açın (genellikle mainfrm.cpp) ve kod Şerit varolan çıkışı açıklama. Kılınmıştır koddan sonra aşağıdaki kodu ekleyin.  
  
 ```  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);

 ```  
  
6.  Projeyi derlemek ve programı çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)

