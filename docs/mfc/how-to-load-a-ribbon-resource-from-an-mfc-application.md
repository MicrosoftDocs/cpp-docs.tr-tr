---
title: 'Nasıl yapılır: bir MFC uygulamasından Şerit kaynağı yükleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b014e1725ae6c5043c051242a74e29338c3ef2d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Nasıl yapılır: Bir MFC Uygulamasından Şerit Kaynağı Yükleme
Şerit kaynağı, uygulamanızda kullanmak için uygulamanın Şerit kaynağı yükleme için değiştirin.  
  
### <a name="to-load-a-ribbon-resource"></a>Şerit kaynağı yüklenemiyor  
  
1.  Bildirme `Ribbon Control` nesnesinde `CMainFrame` sınıfı.  
  
 ```  
    CMFCRibbonBar m_wndRibbonBar;   
 ```  
  
2.  İçinde `CMainFrame::OnCreate`oluşturun ve Şerit denetimi başlatılamıyor.  
  
 ```  
    if (!m_wndRibbonBar.Create (this))  
 {  
    return -1;  
 }  
 
    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))  
 {  
    return -1;  
 }  
 ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)

