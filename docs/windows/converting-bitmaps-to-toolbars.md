---
title: "Bit eşlemleri araç çubuklarına dönüştürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- bitmaps [C++], converting to toolbars
- Toolbar editor, converting bitmaps
- toolbars [C++], converting bitmaps
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 43eda0c6bd875b9fd82ee97d346e3f5d89584795
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="converting-bitmaps-to-toolbars"></a>Bit Eşlemleri Araç Çubuklarına Dönüştürme
Bir bit eşlem dönüştürerek yeni bir araç çubuğu oluşturabilirsiniz. Bit eşlem grafikten bir araç çubuğu düğmesi görüntülerde dönüştürür. Genellikle bit eşlem her düğme için bir görüntü ile tek bir bit eşlem üzerindeki birkaç düğmesi görüntülerini içerir. Görüntüleri herhangi bir boyutta olabilir; 16 piksel genişliğinde ve resmin yüksekliğini varsayılandır. Düğme resimlerini boyutunu belirtebilirsiniz [yeni araç çubuğu kaynağı iletişim kutusu](../windows/new-toolbar-resource-dialog-box.md) araç çubuğu Düzenleyicisi'nden seçtiğinizde **görüntü** sırada görüntü düzenleyicisinde menüsü.  
  
### <a name="to-convert-bitmaps-to-a-toolbar"></a>Bit eşlemleri araç çubuğuna dönüştürmek için  
  
1.  Varolan bir bit eşlem kaynağında açmak [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md). (Bit eşlem .rc dosyanızda değilse, .rc dosyaya sağ tıklayın, seçin **alma** kısayol menüsünden .rc dosyasına eklemek istediğiniz bit eşlem gidin ve ardından **açık**.)  
  
2.  Gelen **görüntü** menüsünde seçin **araç çubuğu Düzenleyicisi**.  
  
     [Yeni araç çubuğu kaynağı iletişim kutusu](../windows/new-toolbar-resource-dialog-box.md) görüntülenir. Genişlik ve yükseklik bit eşlem eşleşecek şekilde simgesi görüntülerinin değiştirebilirsiniz. Araç çubuğu görüntüsünü sonra araç çubuğu Düzenleyicisi'nde görüntülenir.  
  
3.  Dönüştürme işlemini tamamlamak için komut değiştirme **kimliği** düğmesini kullanarak, [Özellikler penceresini](/visualstudio/ide/reference/properties-window). Yeni yazın **kimliği** veya bir **kimliği** aşağı açılan listeden.  
  
    > [!TIP]
    >  Özellikler penceresini başlık çubuğunda Raptiye düğmesi içerir. Bu düğmeye tıkladığınızda etkinleştirir veya penceresi otomatik gizle devre dışı bırakır. Özellikler penceresini sabit kalması hızla tüm araç çubuğu düğmesi özellikleri, tek tek özellik windows yeniden gerek kalmadan geçiş yapmak için Otomatik Gizle kapatın.  
  
 Kullanarak yeni araç çubuğundaki düğmeler komut kimliklerini değiştirebilirsiniz [Özellikler penceresini](/visualstudio/ide/reference/properties-window). Yeni araç çubuğu düzenleme hakkında daha fazla bilgi için bkz: [oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri](../windows/creating-moving-and-editing-toolbar-buttons.md).  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Gereksinimler  
  
 MFC ya da ATL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeni araç çubukları oluşturma](../windows/creating-new-toolbars.md)   
 [Araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md)

