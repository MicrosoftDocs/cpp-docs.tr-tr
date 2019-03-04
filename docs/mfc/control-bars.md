---
title: Denetim Çubukları
ms.date: 11/04/2016
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
ms.openlocfilehash: 4b75d9a96f091d0424592f34bdb1ed7ce76c2372
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283585"
---
# <a name="control-bars"></a>Denetim Çubukları

"Denetim çubuğu" iletişim kutusu çubukları araç çubuklarını ve durum çubukları için genel addır. MFC sınıfları `CToolBar`, `CStatusBar`, `CDialogBar`, `COleResizeBar`, ve `CReBar` sınıfından türetilir [CControlBar](../mfc/reference/ccontrolbar-class.md), ortak işlevlerini uygular.

Denetim çubukları, kullanıcılar seçeneklerini belirleyin, komutları yürütün veya program bilgileri elde denetimlerin satırları görüntülemek için windows ' dir. Denetim çubukları türleri, araç çubukları, iletişim kutusu çubukları ve durum çubuklarını içerir.

- Araç çubukları, sınıf [CToolBar](../mfc/reference/ctoolbar-class.md)

- Durum çubuklarında sınıfı [CStatusBar](../mfc/reference/cstatusbar-class.md)

- Sınıfında iletişim kutusu çubukları [CDialogBar](../mfc/reference/cdialogbar-class.md)

- Sınıfında rebars [CReBar](../mfc/reference/crebar-class.md)

> [!IMPORTANT]
>  İtibariyle MFC sürüm 4.0, araç çubukları, durum çubukları ve araç ipuçları uygulanan sistem işlevleri kullanarak uygulanan *comctl32.dll* önceki uygulaması belirli MFC için yerine. MFC sürüm 6.0, içinde `CReBar`, eklenen, ayrıca comctl32.dll işlevi sarmalar.

Denetim çubuğu türlerine kısa tanıtımları izleyin. Daha fazla bilgi için aşağıdaki bağlantılara bakın.

## <a name="control-bars"></a>Denetim Çubukları

Denetim çubukları hızlı, tek adımlı komut işlemleri sağlayarak programın kullanılabilirlik büyük ölçüde artırır. Sınıf `CControlBar` tüm araç çubukları, durum çubukları ve iletişim kutusu çubukları ortak işlevselliği sağlar. `CControlBar` denetim çubuğu, üst çerçeve penceresinde konumlandırma için işlevsellik sağlar. Denetim çubuğu genellikle bir ana çerçeve penceresinin alt pencere olduğundan, istemci görüntülemek veya MDI çerçeve penceresinin istemci "alt" dir. Bir denetim çubuğuna nesnesinin kendisi konumlandırmak için kendi ana pencerenin istemci dikdörtgeni hakkında bilgi kullanır. Rest istemcisi pencerenin istemci görünümü veya MSI istemci penceresi doldurması ardından üst öğenin kalan istemci Pencere dikdörtgeni değiştirir.

> [!NOTE]
>  Denetim çubuğu üzerindeki bir düğme yoksa bir **komut** veya **UPDATE_COMMAND_UI** işleyicisi, çerçeve otomatik olarak devre dışı bırakır düğmesi.

## <a name="toolbars"></a>Araç Çubukları

Denetim çubuğu komutları yürütmek bit eşlemli düğmeler satırının görüntüleyen bir araç çubuğudur. Bir araç çubuğu düğmesini seçerek bir menü öğesi için eşdeğerdir; Bu menü öğesi araç çubuğu düğmesi olarak aynı kimliği bulunuyorsa bir menü öğesine eşlenen aynı işleyiciyi çağırır. Düğmeler, görünür ve pushbuttons, radyo düğmeleri ve onay kutularını davranır şekilde yapılandırılabilir. Araç için bir çerçeve penceresinin üst genellikle hizalanır ancak bir MFC araç çubuğu "kendi üst penceresine veya float kendi Mini çerçeve penceresindeki tüm tarafına sabitleyebilirsiniz". Araç ayrıca "kaydırabilirsiniz" ve boyutunu değiştirmek ve fareyle sürükleyin. Kullanıcı araç çubuğunun düğme üzerinde fareyi hareket ettirdikçe bir araç çubuğu araç ipuçları da görüntüleyebilirsiniz. Bir araç ipucu düğmenin amaçlı kısaca açıklayan küçük açılan bir penceredir.

> [!NOTE]
>  MFC sürüm 4.0 itibariyle sınıfı [CToolBar](../mfc/reference/ctoolbar-class.md) Windows araç çubuğu ortak denetim kullanır. A `CToolBar` içeren bir [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md). Eski araç çubukları, ancak desteklenmektedir. Makaleye göz atın [araç çubukları](../mfc/mfc-toolbar-implementation.md).

## <a name="status-bars"></a>Durum Çubukları

Durum çubuğu olan metin çıkış bölmeleri veya "göstergeler" içeren bir denetim çubuğu Çıkış bölmeleri, ileti satırları ve durum göstergesi olarak sık kullanılan bloblardır. Seçili bir menü veya araç çubuğu komutuna MFC Uygulama Sihirbazı tarafından oluşturulan varsayılan durum çubuğu en soldaki bölmede kısaca açıklayan komut yardım iletisini satırları ileti satır örneklerindendir. Durum göstergesi SCROLL LOCK, NUM LOCK ve diğer anahtarlar verilebilir. Durum çubukları, genellikle bir çerçeve penceresinin alt kısmına hizalanır. Sınıfına bakın [CStatusBar](../mfc/reference/cstatusbar-class.md) ve sınıf [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md).

## <a name="dialog-bars"></a>İletişim Kutusu Çubukları

Bir iletişim çubuğu modsuz iletişim kutusu işlevselliğini bir iletişim şablonunu kaynağını, temel bir denetim çubuğu bulunur. İletişim kutusu çubukları, Windows, içerebilir özel ya da ActiveX denetimleri. Bir iletişim kutusu olduğu gibi kullanıcı denetimleri arasında sekme ile ilerleyebilirsiniz. İletişim kutusu çubukları üst, alt, sol veya sağ tarafındaki bir çerçeve penceresinin hizalanabilir ve onlar da kendi çerçeve penceresinde kaydırıldı. Sınıfına bakın [CDialogBar](../mfc/reference/cdialogbar-class.md).

## <a name="rebars"></a>Rebars

A [çubuk barınağı](../mfc/using-crebarctrl.md) çubuk barınağı denetimleri için Düzen, durum ve Kalıcılık yerleştirme bilgileri sağlayan denetim çubuğu. Bir rebar nesnesi çeşitli alt pencereleri düzenleme kutuları, araç çubukları ve liste kutuları gibi genellikle diğer denetimleri içerebilir. Bir rebar nesneyi kendi alt pencereleri belirtilen bir bit eşlem görüntüleyebilirsiniz. Bu otomatik olarak veya el ile tıklayarak veya kavrayıcı çubuğunu sürüklerken yeniden boyutlandırılabilir. Sınıfına bakın [CReBar](../mfc/reference/crebar-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
