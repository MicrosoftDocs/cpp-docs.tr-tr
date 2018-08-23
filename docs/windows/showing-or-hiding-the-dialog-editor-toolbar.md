---
title: Gösterme veya gizleme iletişim kutusu araç çubuğunu | Microsoft Docs
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
ms.openlocfilehash: f1aa9e84e1f03f0299d25ec43b91c93531179ab6
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599418"
---
# <a name="showing-or-hiding-the-dialog-editor-toolbar"></a>İletişim Kutusu Araç Çubuğunu Gösterme veya Gizleme

Açtığınızda **iletişim** Düzenleyicisi **iletişim kutusu Düzenleyicisi** araç otomatik olarak çözümünüzü üst kısmında görünür.

### <a name="dialog-editor-toolbar"></a>İletişim kutusu Düzenleyicisi araç çubuğu

|Simge|Açıklama|Simge|Açıklama|
|----------|-------------|----------|-------------|
|![Test iletişim kutusu düğmesini](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|Test iletişim kutusu|![Alanı arasında düğme](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|Arasında|
|![Hizalama sola düğmesi](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|Sola Hizala|![Alanı aşağı düğmesi](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|Aşağı|
|![Hizalama hakları düğmesi](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|Sağa Hizala|![Yapma aynı genişliği düğmesi](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|Aynı genişliğe Getir|
|![Hizalama kırpın düğmesi](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|Üste hizalama|![Yapma aynı yükseklikte düğmesi](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|Aynı yüksekliğe Getir|
|![Hizalama alta düğmesi](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|Alta Hizala|![Yapma aynı boyutu düğmesi](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|Aynı Boyuta Getir|
|![Dikey Orta düğmesi](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Dikey|![İki durumlu kılavuz düğmesi](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|Kılavuzu Aç/Kapat|
|![Yatay Orta düğmesi](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|Yatay|![Geçiş kılavuzlarını düğmesi](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|Rehberi Aç/Kapat|

**İletişim kutusu Düzenleyicisi** araç çubuğu düğmeleri düzenleme iletişim kutusunda, örneğin boyutu ve hizalama denetim düzeni için içerir. **İletişim kutusu Düzenleyicisi** araç çubuğu düğmeleri üzerinde komutları karşılık **biçimi** menüsü. Ayrıntılar için bkz [iletişim kutusu Düzenleyicisi için hızlandırma tuşları](../windows/accelerator-keys-for-the-dialog-editor.md).

Uygulamasındayken **iletişim** Düzenleyicisi görüntülenmesini geçiş yapabileceğiniz **iletişim kutusu Düzenleyicisi** kullanılabilir araç çubukları ve windows listesinden seçerek araç çubuğu.

### <a name="to-show-or-hide-the-dialog-editor-toolbar"></a>İletişim kutusu Düzenleyicisi araç çubuğunu gizlemek veya göstermek için

1. Üzerinde **görünümü** menüsünü tıklatın **araç çubukları** ardından **iletişim kutusu Düzenleyicisi** alt.

   > [!NOTE]
   > **İletişim kutusu Düzenleyicisi** bir iletişim kutusu kaynağı iletişim kutusu Düzenleyicisi'nde açtığınız zaman, araç varsayılan olarak görüntülenir; ancak, araç açıkça kapatırsanız, bir iletişim kutusu kaynağına sonraki açışınızda çağırma gerekecektir.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimlerin Düzenlenmesi](../windows/arrangement-of-controls-on-dialog-boxes.md)  
[Nasıl yapılır: Kaynak Oluşturma](../windows/how-to-create-a-resource.md)  
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)  
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)