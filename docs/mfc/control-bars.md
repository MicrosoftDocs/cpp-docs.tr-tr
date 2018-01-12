---
title: "Denetim çubukları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command bars [MFC], types of
- toolbars [MFC], control bars
- control bars [MFC]
- MFC, control bars
- control bars [MFC], types of
- CDialogBar class [MFC], control bars
- status bars [MFC], control bars
- CControlBar class [MFC], MFC control bars
- dialog bars [MFC], control bars
- CToolBar class [MFC], control bars
- CStatusBar class [MFC], control bars
ms.assetid: 31831910-3d23-4d70-9e71-03cc02f01ec4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3550043e5b85247d4188c830873099c6ea9831a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="control-bars"></a>Denetim Çubukları
"Denetim çubuğu" araç çubukları, durum çubukları ve iletişim kutusu çubukları genel adıdır. MFC sınıfları `CToolBar`, `CStatusBar`, `CDialogBar`, `COleResizeBar`, ve **CReBar** sınıfından türetilen [CControlBar](../mfc/reference/ccontrolbar-class.md), ortak işlevleri uygular.  
  
 Denetim çubukları ile kullanıcılar seçenekleri seçin, komutları yürütün veya program bilgilerini elde denetimlerinin satırları görüntülemek için windows ' dir. Denetim çubukları türleri araç çubukları, iletişim kutusu çubukları ve durum çubukları içerir.  
  
-   Sınıfında araç çubukları [CToolBar](../mfc/reference/ctoolbar-class.md)  
  
-   Durum çubuklarında sınıfı [CStatusBar](../mfc/reference/cstatusbar-class.md)  
  
-   Sınıfında iletişim kutusu çubukları [CDialogBar](../mfc/reference/cdialogbar-class.md)  
  
-   Sınıfında rebars [CReBar](../mfc/reference/crebar-class.md)  
  
> [!IMPORTANT]
>  MFC sürüm 4. 0'dan sonra araç çubukları, durum çubukları ve araç ipuçları için MFC belirli önceki uygulaması yerine comctl32.dll uygulanan sistem işlevleri kullanılarak uygulanır. MFC sürüm 6.0, içinde **CReBar**, hangi ayrıca comctl32.dll işlevi sarmalar eklendi.  
  
 Denetim çubuğu türlerine kısa tanıtımları izleyin. Daha fazla bilgi için aşağıdaki bağlantılara bakın.  
  
## <a name="control-bars"></a>Denetim Çubukları  
 Denetim çubukları hızlı tek adımlı komutu Eylemler sağlayarak bir programın kullanılabilirlik büyük ölçüde artırır. Sınıf `CControlBar` tüm araç çubukları, durum çubukları ve iletişim kutusu çubukları ortak işlevsellik sağlar. `CControlBar`denetim çubuğu kendi üst çerçeve penceresinde konumlandırma için işlevsellik sağlar. Denetim çubuğu genellikle bir üst çerçeve penceresinin alt pencere olduğundan, istemci görünüm veya MDI istemcisi çerçeve penceresi "eşdüzey" dir. Denetim çubuğu nesne kendi üst pencerenin istemci dikdörtgen hakkında bilgi kendisini konumlandırmak için kullanır. Ardından istemci görünümü ya da MDI istemcisi penceresinde istemci pencerenin geri kalanını doldurması üst öğenin kalan istemci Pencere dikdörtgeni değiştirir.  
  
> [!NOTE]
>  Denetim çubuğu düğmesinde yoksa, bir **KOMUTU** veya **UPDATE_COMMAND_UI** işleyici, framework otomatik olarak devre dışı bırakır düğmesi.  
  
## <a name="toolbars"></a>Araç Çubukları  
 Bir araç çubuğu komutları yürütmek eşlemli düğmelerinin bir satır görüntüler denetim çubuğu bulunur. Araç çubuğu düğmesine basarak menü öğesi seçme eşdeğerdir; Bu menü öğesi araç çubuğu düğmesi aynı Kimliğe varsa bir menü öğesine eşlenen aynı işleyici çağırır. Düğmeleri görünür ve pushbuttons, radyo düğmeleri ve onay kutularını hareket etmesi için yapılandırılabilir. Araç çubuğu genellikle bir çerçeve penceresinde üst kısmına hizalanır ancak bir MFC araç çubuğu "kendi üst penceresi veya float kendi kısa çerçeve penceresinde herhangi bir tarafına sabitleyebilirsiniz". Araç ayrıca "kaydırabilirsiniz" ve boyutunu değiştirmek ve fareyle sürükleyin. Kullanıcının fare araç çubuğunun düğmeleri üzerinde hareket ederken bir araç çubuğu araç ipuçları da görüntüleyebilirsiniz. Araç İpucu düğmenin amacı kısaca açıklayan küçük açılan bir penceredir.  
  
> [!NOTE]
>  MFC sürüm 4. 0'dan sonra sınıf [CToolBar](../mfc/reference/ctoolbar-class.md) Windows araç ortak denetimi kullanır. A `CToolBar` içeren bir [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md). Eski araç çubukları hala, ancak desteklenir. Makalesine bakın [araç çubukları](../mfc/mfc-toolbar-implementation.md).  
  
## <a name="status-bars"></a>Durum Çubukları  
 Durum çubuğu metin çıktısı bölmeleri ya da "göstergeleri." içeren bir denetim çubuğu olduğu Çıkış bölmeleri, ileti satırları ve durum göstergesi olarak yaygın olarak kullanılır. İleti satırı örnekleri seçilen menü veya araç çubuğu komutuna MFC Uygulama Sihirbazı tarafından oluşturulan varsayılan durum çubuğunun en soldaki bölmede kısaca açıklayan komut Yardım iletisi satırları içerir. Durum göstergesi örnekler kaydırma kilidi, NUM LOCK ve diğer anahtarları içerir. Durum çubukları genellikle bir çerçeve penceresinde altına hizalanır. Sınıfına bakın [CStatusBar](../mfc/reference/cstatusbar-class.md) ve sınıf [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md).  
  
## <a name="dialog-bars"></a>İletişim Kutusu Çubukları  
 Bir iletişim çubuğu kalıcı olmayan iletişim kutusu işlevselliğe sahip bir iletişim şablonunu kaynağını temel bir denetim çubuğu bulunur. İletişim kutusu çubukları, Windows, içerebilir özel ya da ActiveX denetimlerini. Bir iletişim kutusu olduğu gibi kullanıcı arasında denetimleri sekmesinde. İletişim kutusu çubukları üst, alt, sol veya sağ tarafındaki bir çerçeve penceresinde hizalanabilir ve bunlar da kendi çerçeve penceresinde kaydırılmış. Sınıfına bakın [CDialogBar](../mfc/reference/cdialogbar-class.md).  
  
## <a name="rebars"></a>Rebars  
 A [rebar](../mfc/using-crebarctrl.md) rebar denetimleri yerleştirme, düzeni, durumu ve kalıcılığı bilgilerini sağlayan bir denetim çubuğu. Bir rebar nesnesi alt öğe pencerelerini, Düzen kutuları, araç çubukları ve liste kutuları dahil genellikle diğer denetimler çeşitli içerebilir. Bir rebar nesnesi, alt öğe pencerelerini belirtilen bir bit eşlem görüntüleyebilirsiniz. Bu otomatik olarak veya el ile tıklatarak ya da Mandal çubuğunu sürükleyerek yeniden boyutlandırılabilir. Sınıfına bakın [CReBar](../mfc/reference/crebar-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
