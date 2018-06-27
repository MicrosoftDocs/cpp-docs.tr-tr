---
title: Gösterme veya gizleme iletişim kutusu Düzenleyicisi araç | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog editor, showing or hiding toolbar
ms.assetid: 93c255e1-90eb-48b6-8602-450acda75bed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ad456d37252b40be72217e6cbc40a2a399bb34ef
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891600"
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
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimlerin düzenlenmesi](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [Nasıl yapılır: kaynak oluşturma](../windows/how-to-create-a-resource.md)   
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)

