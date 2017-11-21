---
title: "İletişim kutusundaki radyo düğmelerini gruplandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.dialog.grouping
dev_langs: C++
helpviewer_keywords:
- member variables, adding to radio button groups
- variables, dialog box control member variables
- dialog box controls, grouping radio buttons
- grouping controls
- radio buttons, grouping on dialog boxes
ms.assetid: 3cc43f9e-56c8-4faa-9930-ce81733c69de
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 40d1c75dfe70a5dcdf664f105f2872475219e294
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="grouping-radio-buttons-on-a-dialog-box"></a>İletişim Kutusundaki Radyo Düğmelerini Gruplama
Bir iletişim kutusu radyo düğmeleri eklediğinizde, bunları bir grup olarak Özellikleri penceresinde gruptaki ilk düğmesi için bir grup özelliği ayarlanarak kabul eder. Bu radyo düğmesi için bir denetim kimliği sonra görünür [üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md), radyo düğmesi grubunun üye değişkeni ekleme olanak sağlar.  
  
 Bir iletişim kutusundaki radyo düğmelerini birden fazla grup sahip olabilir ve her grup, aşağıdaki yordamı kullanarak eklenmelidir.  
  
### <a name="to-add-a-group-of-radio-buttons-to-a-dialog-box"></a>Bir iletişim kutusu için bir grup radyo düğmelerini eklemek için  
  
1.  Radyo düğmesi denetimini seçin [araç penceresi](/visualstudio/ide/reference/toolbox) ve iletişim kutusunda, denetimi yerleştirmek istediğiniz konumu tıklatın.  
  
2.  1. adım gereksinim duyduğunuz kadar çok radyo düğmeleri eklemek için yineleyin. Gruptaki radyo düğmeleri sekme sırası ardışık olduğundan emin olun (daha fazla bilgi için bkz: [, sekme sırasını denetimleri değiştirme](../windows/changing-the-tab-order-of-controls.md)).  
  
3.  İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window)ayarlayın **grup** özelliği *ilk* sekme sırası radyo düğmesinin **doğru**.  
  
     Değiştirme **grup** özelliğine **True** WS_GROUP stili bir kaynak betik iletişim nesnesinin düğmenin girişi ekler ve bir kullanıcı yalnızca bir radyo düğmesi düğmesi zamanında seçebilir, sağlar Grup (kullanıcı bir radyo düğmesine tıkladığında, gruptaki diğerleriyle silinir).  
  
    > [!NOTE]
    >  Yalnızca ilk radyo düğmesi grubunda olmalıdır **grup** özelliğini **doğru**. Düğmesi grubunun parçası olmayan ek denetimler varsa ayarlamak **grup** ilk denetim özelliği *dışında grubu olan* için **True** de. İlk denetimi grubu dışında sekme sırasını görüntülemek için CTRL + D tuşlarına basarak hızla tanımlayabilirsiniz.  
  
### <a name="to-add-a-member-variable-for-the-radio-button-group"></a>Radyo düğmesi grubunda için üye değişkeni eklemek için  
  
1.  Sekme sırasında ilk radyo düğmesi denetimini sağ tıklayın (baskın denetimi ve biriyle **grup** özelliği True olarak ayarlanan).  
  
2.  Seçin **değişken Ekle** kısayol menüsünden.  
  
3.  İçinde [üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md)seçin **denetim değişkeni** onay kutusunu işaretleyin ve ardından **değeri** radyo düğmesi.  
  
4.  İçinde **değişken adı** yeni üye değişkeni için bir ad yazın.  
  
5.  İçinde **değişken türü** liste kutusunda **int** veya türü **int**.  
  
6.  Artık hangi radyo düğmesinin seçili görünmelidir belirtmek için kodunuzu değiştirebilirsiniz. Örneğin, m_radioBox1 = 0; ilk radyo düğmesi grubunda seçer.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimlerin düzenlenmesi](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [Denetimleri](../mfc/controls-mfc.md)

