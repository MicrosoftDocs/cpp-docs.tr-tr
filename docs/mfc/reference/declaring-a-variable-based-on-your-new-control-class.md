---
title: Yeni Denetim sınıfınıza dayalı değişken bildirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.classes.control.variable
dev_langs:
- C++
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 677006d441c940f478b3d23744d1057667307e1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Yeni Denetim Sınıfınıza Dayalı Değişken Bildirme
MFC denetim sınıfı oluşturduktan sonra dayalı bir değişken bildirebilirsiniz. Yeni değişken için bir bağlam sağlamak için iletişim kutusu Düzenleyicisi'ni açın ve yeniden kullanılabilir denetiminizi kullanmak istediğiniz iletişim kutusu düzenleyin. Ayrıca, iletişim kutusu zaten kendisiyle ilişkilendirilmiş bir sınıf olmalıdır. İletişim kutusu düzenleyicisini kullanma hakkında daha fazla bilgi için bkz: [iletişim kutusu Düzenleyicisi](../../windows/dialog-editor.md).  
  
### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Yeniden kullanılabilir sınıfınıza dayalı değişken bildirme  
  
1.  İletişim kutusu düzenlerken, yeni denetiminizin temel sınıf olarak aynı türde bir denetim iletişim kutusu denetimleri araç çubuğuna sürükleyin.  
  
2.  Fare işaretçisini bırakılan denetime yerleştirin.  
  
3.  CTRL tuşunu basılı tutarken denetimi çift tıklatın.  
  
     [Üye değişkeni ekleme](../../ide/add-member-variable-wizard.md) iletişim kutusu görüntülenir.  
  
4.  İçinde **erişim** kutusunda, doğru erişimi denetlemek için seçin.  
  
5.  Tıklatın **denetim değişkeni** onay kutusu.  
  
6.  İçinde **değişken adı** bir ad yazın.  
  
7.  Altında **kategori**, tıklatın **denetim**.  
  
8.  İçinde **denetim kimliği** listesinde, eklediğiniz denetimi seçin. **Değişken türü** listesi doğru değişken türünü görüntülemesi gereken ve **denetim türü** kutusu doğru denetim türü görüntülenmelidir.  
  
9. İçinde **açıklama** kutusunda, kodunuzda görünmesini istediğiniz herhangi bir yorum ekleyin.  
  
10. **Tamam**'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletileri işlevlere eşleme](../../mfc/reference/mapping-messages-to-functions.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)   
 [Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)   
 [Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
