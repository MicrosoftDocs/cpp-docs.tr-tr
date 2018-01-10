---
title: "Araç çubuğu araç ipuçları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tool tips [MFC], activating
- CBRS_TOOLTIPS constant [MFC]
- tool tips [MFC], adding text
- updates [MFC]
- CBRS_FLYBY constant [MFC]
- tool tips [MFC]
- updating status bar messages
- updates, status bar messages
- status bars [MFC], tool tips
- flyby status bar updates
ms.assetid: d1696305-b604-4fad-9f09-638878371412
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 248c975c51a2f44f6c9b17094d6b05082a9016a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="toolbar-tool-tips"></a>Araç Çubuğu Araç İpuçları
Araç ipuçları fare bir süre için düğme üzerine getirdiğinizde, araç düğmenin amacı kısa açıklamaları sunan küçük açılır pencereleri ' dir. Uygulama Sihirbazı ile bir araç olan bir uygulama oluşturduğunuzda, sizin için araç ipucu desteği sağlanır. Bu makalede, Uygulama Sihirbazı'nı ve uygulamanız için araç ipucu desteği ekleme tarafından oluşturulan her iki araç ipucu desteği açıklanmaktadır.  
  
 Bu makalede yer almaktadır:  
  
-   [Araç ipuçlarını etkinleştirme](#_core_activating_tool_tips)  
  
-   [Flyby durum çubuğu güncelleştirmeleri](#_core_fly_by_status_bar_updates)  
  
##  <a name="_core_activating_tool_tips"></a>Araç ipuçlarını etkinleştirme  
 Araç ipuçları, uygulamanızda etkinleştirmek için iki şey yapmanız gerekir:  
  
-   Ekleme `CBRS_TOOLTIPS` diğer stilleri stiline (gibi **WS_CHILD**, **ws_vısıble**ve diğer **CBRS_** stilleri) olarak geçirilen `dwStyle` parametresi[ CToolBar::Create](../mfc/reference/ctoolbar-class.md#create) işlevi veya [SetBarStyle](../mfc/reference/ccontrolbar-class.md#setbarstyle).  
  
-   Aşağıdaki yordamda açıklandığı gibi araç komutu için bir komut satırı istemi içeren dize kaynağı için yeni satır karakteri ('\n') tarafından ayrılmış araç ipucu metnini ekleyin. Dize kaynağını araç çubuğu düğmesi Kimliğini paylaşır.  
  
#### <a name="to-add-the-tool-tip-text"></a>Araç İpucu metni eklemek için  
  
1.  Araç çubuğu araç çubuğu düzenleyicisinde düzenlerken açmak **araç çubuğu düğmesi özellikleri** verilen düğmesi penceresi.  
  
2.  İçinde **komut istemi** kutusunda, o düğmesi için araç ipucu görünmesini istediğiniz metni belirtin.  
  
> [!NOTE]
>  Araç çubuğu düzenleyicisinde düğme özelliği zorunda kalındı önceki yordamı değiştirir olarak metin ayarı açın ve dize kaynağını düzenleyin.  
  
 Denetim çubuğu araç ipuçları etkin ile üzerine yerleştirilen alt denetimleri varsa, aşağıdaki ölçütleri karşılaması sürece denetim çubuğu denetim çubuğunda her alt denetim için araç ipucu görüntülenir:  
  
-   Denetimin kimliği 1 değil-  
  
-   Dize tablosu girişi kaynak dosyasında alt denetim olarak aynı Kimliğe sahip bir araç ipucu dize vardır.  
  
##  <a name="_core_fly_by_status_bar_updates"></a>Flyby durum çubuğu güncelleştirmeleri  
 Araç ipuçları için ilgili bir "flyby" durum güncelleştirme çubuğunda özelliğidir. Düğme etkinleştirildiğinde, varsayılan olarak, yalnızca belirli araç çubuğu düğmesi durum çubuğunda ileti açıklar. Ekleyerek `CBRS_FLYBY` geçirilen stilleri listesine `CToolBar::Create`, fare imlecini araç çubuğu düğmesi etkinleştirmeden geçtiğinde güncelleştirilmiş bu iletiler olabilir.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [MFC araç çubuğu uygulaması (çubuklarında genel bakış bilgileri)](../mfc/mfc-toolbar-implementation.md)  
  
-   [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları  
  
-   [Araç çubuğu denetimiyle çalışma](../mfc/working-with-the-toolbar-control.md)  
  
-   [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)

