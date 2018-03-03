---
title: "Yatay kaydırma çubuğunun genişliğini ayarlama | Microsoft Docs"
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
- list controls, scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars, displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars, width
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7aeabed9eaa164a0c19fd6b425f36e68059a548d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setting-the-width-of-a-horizontal-scroll-bar"></a>Yatay Kaydırma Çubuğunun Genişliğini Ayarlama
MFC sınıfları kullanarak iletişim kutusuna yatay kaydırma çubuğu içeren bir liste kutusu eklediğinizde, kaydırma çubuğu uygulamanızda otomatik olarak görünmez.  
  
### <a name="to-make-the-scroll-bar-appear"></a>Kaydırma çubuğu görünmesi yapma  
  
1.  Geniş öğesi için en büyük genişliği aranarak [CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) kodunuzda.  
  
     Bu değer kümesi kaydırma çubuğu görünmez, hatta liste kutusunda öğeleri kutudan daha geniş olduğunda.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 Gereksinimler  
  
 MFC  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [Denetimler](../mfc/controls-mfc.md)

