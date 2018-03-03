---
title: "Olay işleyici (Visual C++) ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9a5380bf335a13bbf7b2f54840c9d1160187167
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-event-handler-visual-c"></a>Olay İşleyici Ekleme (Visual C++)
Kaynak Düzenleyicisi'nden yeni bir olay işleyicisi ekleyebilir, veya bir iletişim kutusu denetimi kullanmak için mevcut olay işleyicisi, düzenleme [olay işleyici Sihirbazı](../ide/event-handler-wizard.md).  
  
 İletişim kutusunu kullanarak uygulama sınıfı bir olayı ekleyebilirsiniz [Özellikler penceresini](/visualstudio/ide/reference/properties-window). İletişim kutusu sınıf dışında bir sınıfa olay eklemek istiyorsanız, olay işleyici Sihirbazı'nı kullanın.  
  
### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>Bir iletişim kutusu denetimi için bir olay işleyicisi eklemek için  
  
1.  İletişim kutusu kaynağı çift [kaynak görünümü](../windows/resource-view-window.md) denetiminde içeren iletişim kutusu kaynağı açmaya [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md).  
  
2.  Bildirim olayını işlemek istediğiniz denetimi sağ tıklatın.  
  
3.  Kısayol menüsünde **olay işleyicisi ekleme** olay işleyici Sihirbazı'nı görüntülemek için.  
  
4.  Olayda seçin **ileti türü** seçili sınıfı eklemek için kutusunu **sınıf listesi** kutusu.  
  
5.  Varsayılan adı kabul **işlevi işleyicisi adı** kutusu veya tercih ettiğiniz adını sağlayın.  
  
6.  Tıklatın **ekleme ve düzenleme** olay işleyicisi projeye ekleyin ve uygun olay işleyici kod eklemek için yeni işlev, metin düzenleyici açın.  
  
     Seçilen ileti türü seçilen sınıf için bir olay işleyicisi zaten varsa, **ekleme ve düzenleme** kullanılamıyor ve **düzenleme kod** kullanılabilir. Tıklatın **düzenleme kod** varolan işlevinin en Metin Düzenleyicisi'ni açın.  
  
 Alternatif olarak, olay işleyicilerini ekleyebilirsiniz [Özellikler penceresini](/visualstudio/ide/reference/properties-window). Bkz: [iletişim kutusu denetimleri için olay işleyicileri ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)   
 [Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)   
 [Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Sınıf yapısında gezinme](../ide/navigating-the-class-structure-visual-cpp.md)