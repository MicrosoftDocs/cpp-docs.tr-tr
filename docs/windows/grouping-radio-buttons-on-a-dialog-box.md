---
title: İletişim kutusundaki radyo düğmelerini gruplandırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.grouping
dev_langs:
- C++
helpviewer_keywords:
- member variables, adding to radio button groups
- variables, dialog box control member variables
- dialog box controls, grouping radio buttons
- grouping controls
- radio buttons, grouping on dialog boxes
ms.assetid: 3cc43f9e-56c8-4faa-9930-ce81733c69de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7712927a10fa34c5b6436aecd002c9621546638b
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571509"
---
# <a name="grouping-radio-buttons-on-a-dialog-box"></a>İletişim Kutusundaki Radyo Düğmelerini Gruplama
Radyo düğmeleri iletişim kutusuna eklediğinizde, bunları bir grup olarak grubundaki ilk düğme için Özellikler penceresindeki bir grubu özelliğini ayarlayarak değerlendirin. Denetim Kimliği bu radyo düğmesi için daha sonra yer [üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md), radyo düğmesi grubunu için bir üye değişkeni ekleme etmenize imkan sağlar.  
  
 İletişim kutusundaki radyo düğmelerini birden fazla grup olabilir ve her grup, aşağıdaki yordamı kullanarak eklenmelidir.  
  
### <a name="to-add-a-group-of-radio-buttons-to-a-dialog-box"></a>Bir iletişim kutusu için bir grup radyo düğmeleri eklemek için  
  
1.  Radyo düğmesi denetiminde seçme [araç penceresi](/visualstudio/ide/reference/toolbox) ve denetimi yerleştirmek istediğiniz iletişim kutusunda bir yeri tıklatın.  
  
2.  1. adım, ihtiyacınız kadar radyo düğmeleri eklemek için yineleyin. Radyo düğmesi grubunda sekme sırasının ardışık olduğundan emin olun (daha fazla bilgi için [, sekme sırasını denetimleri değiştirme](../windows/changing-the-tab-order-of-controls.md)).  
  
3.  İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window)ayarlayın **grubu** özelliği *ilk* radyo düğmesi için sekmesinde sırayla **True**.  
  
     Değiştirme **grubu** özelliğini **True** WS_GROUP stili kaynak betiği iletişim nesnesinin düğmenin girişi ekler ve bir kullanıcı yalnızca bir radyo düğmesi birer birer düğmesinde seçebilirsiniz, sağlar Grup (kullanıcı bir radyo düğmesine tıkladığında, gruptaki diğer temizlenir).  
  
    > [!NOTE]
    >  Yalnızca ilk radyo düğmesi grubunda olmalıdır **grubu** özelliğini **True**. Düğmesi grubunun parçası olmayan ek denetimleri varsa Ayarla **grubu** ilk denetiminin özelliği *grubun dışına olan* için **True** de. Sekme sırasını görüntülemek için CTRL + D tuşlarına basarak ilk denetim grubu dışında hızlı bir şekilde tespit edebilirsiniz.  
  
### <a name="to-add-a-member-variable-for-the-radio-button-group"></a>Radyo düğmesi grubunda için üye değişkeni eklemek için  
  
1.  Sekme sırasında ilk radyo düğmesi denetimini sağ tıklayın (baskın denetimi ve biriyle **grubu** özelliği True olarak ayarlayın).  
  
2.  Seçin **değişken Ekle** kısayol menüsünden.  
  
3.  İçinde [üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md)seçin **denetim değişkeni** onay kutusunu işaretleyin ve ardından **değer** radyo düğmesi.  
  
4.  İçinde **değişken adı** yeni bir üye değişkeni için bir ad yazın.  
  
5.  İçinde **değişken türü** liste kutusu, select **int** veya türü **int**.  
  
6.  Şimdi, kodunuzun hangi radyo düğmesini seçili görünmesi gerektiğini belirten değiştirebilirsiniz. Örneğin, m_radioBox1 = 0; ilk radyo düğmesi grubunda seçer.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimlerin düzenlenmesi](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [Denetimler](../mfc/controls-mfc.md)