---
title: "Gösterme veya gizleme iletişim kutusu Düzenleyicisi araç | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog editor, showing or hiding toolbar
ms.assetid: 93c255e1-90eb-48b6-8602-450acda75bed
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e794cb6e24e86aa83fe7ea5b36f700c9dc9893f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="showing-or-hiding-the-dialog-editor-toolbar"></a>İletişim Kutusu Araç Çubuğunu Gösterme veya Gizleme
İletişim kutusu Düzenleyicisi'ni açtığınızda, iletişim kutusu Düzenleyicisi araç otomatik olarak çözümünüzü üstünde görünür.  
  
### <a name="dialog-editor-toolbar"></a>İletişim kutusu Düzenleyicisi araç çubuğu  
  
|Simge|Açıklama|Simge|Açıklama|  
|----------|-------------|----------|-------------|  
|![Test iletişim kutusu düğmesini](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|Test iletişim kutusu|![Alanı arasında düğmesi](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|Arasında|  
|![Sola düğmesi Hizala](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|Sola hizalayın|![Alanı aşağı düğmesi](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|Aşağı|  
|![Hakları düğmesi Hizala](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|Sağa Hizala|![Yapma aynı genişliği düğmesi](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|Aynı genişliğe olun|  
|![Dows masaüstleri düğmesi Hizala](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|Üste hizalama|![Yapma aynı yükseklik düğmesi](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|Aynı yükseklikte yapma|  
|![Düğme Alta Hizala](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|Alta Hizala|![Yapma aynı boyutta düğmesi](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|Aynı boyuta getirme|  
|![Merkezi dikey düğmesini](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Dikey|![İki durumlu kılavuz düğme](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|Kılavuzu Aç/Kapat|  
|![Merkezi yatay düğmesini](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|Yatay|![Geçiş kılavuzlarını düğmesi](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|Geçiş kılavuzları|  
  
 İletişim kutusu Düzenleyicisi araç çubuğu denetimleri iletişim kutusunda, örneğin boyutu ve hizalama düzenini düzenleme için düğmeler içerir. İletişim kutusu Düzenleyicisi araç çubuğu düğmeleri biçimi menüsündeki komutlar karşılık gelir. Ayrıntılar için bkz [kısayol tuşları için iletişim kutusu Düzenleyicisi](../windows/accelerator-keys-for-the-dialog-editor.md).  
  
 İletişim kutusu Düzenleyicisi'nde olduğunda kullanılabilir araç çubukları ve windows listeden seçerek iletişim kutusu Düzenleyicisi araç çubuğu görünümünü geçiş yapabilirsiniz.  
  
### <a name="to-show-or-hide-the-dialog-editor-toolbar"></a>Göster veya gizle iletişim kutusu Düzenleyicisi araç için  
  
1.  Üzerinde **Görünüm** menüsünü tıklatın **araç çubukları** ardından **iletişim kutusu Düzenleyicisi** menüden.  
  
    > [!NOTE]
    >  İletişim kutusu Düzenleyicisi iletişim kutusu kaynağı iletişim kutusu Düzenleyicisi araç varsayılan olarak görüntülenir; Ancak, araç açıkça kapatırsanız, bir iletişim kutusu kaynağı bir sonraki açışınızda çağırma gerekir.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimlerin düzenlenmesi](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [Nasıl yapılır: kaynak oluşturma](../windows/how-to-create-a-resource.md)   
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [İletişim kutusu Düzenleyicisi](../windows/dialog-editor.md)

