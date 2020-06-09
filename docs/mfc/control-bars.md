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
ms.openlocfilehash: a2d3683b744493bb5566456b9e1358c1ddc418d4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615971"
---
# <a name="control-bars"></a>Denetim Çubukları

"Denetim çubuğu", araç çubuklarının, durum çubuklarının ve iletişim çubuklarının genel adıdır. MFC sınıfları,,, `CToolBar` `CStatusBar` `CDialogBar` `COleResizeBar` ve `CReBar` kendi ortak işlevlerini uygulayan [CControlBar](reference/ccontrolbar-class.md)sınıfından türet.

Denetim çubukları, kullanıcıların seçenek belirleyip, komutları yürütebileceği veya program bilgilerini alabileceği denetim satırlarını görüntüleyen bir Windows. Denetim çubuğu türleri araç çubukları, İletişim çubukları ve durum çubuklarını içerir.

- Araç çubukları, [CToolBar](reference/ctoolbar-class.md) sınıfında

- Durum çubukları, [CStatusBar](reference/cstatusbar-class.md) sınıfı

- İletişim çubukları, [CDialogBar](reference/cdialogbar-class.md) sınıfı

- Rebar, sınıf [ekibi](reference/crebar-class.md)

> [!IMPORTANT]
> MFC sürüm 4,0, araç çubukları, durum çubukları ve araç ipuçları, MFC 'ye özgü önceki uygulama yerine *Comctl32. dll* ' de uygulanan sistem işlevleri kullanılarak uygulanır. MFC sürüm 6,0 ' de, `CReBar` Comctl32. dll işlevini de sarmalanmış.

Denetim çubuğu türlerine ilişkin kısa tanıtımları takip edin. Daha fazla bilgi için aşağıdaki bağlantılara bakın.

## <a name="control-bars"></a>Denetim Çubukları

Denetim çubukları, hızlı, tek adımlı komut eylemleri sağlayarak programın kullanılabilirliğini büyük ölçüde geliştirir. Sınıfı, `CControlBar` tüm araç çubuklarının, durum çubuklarının ve iletişim çubuklarının ortak işlevlerini sağlar. `CControlBar`Denetim çubuğunu üst çerçeve penceresinde konumlandırma işlevlerini sağlar. Bir denetim çubuğu genellikle üst çerçeve penceresinin alt bir pencere olduğundan, çerçeve penceresinin istemci görünümü veya MDI istemcisine bir "eşdüzey" olur. Bir denetim çubuğu nesnesi kendi üst penceresinin istemci dikdörtgeniyle ilgili bilgileri kullanarak kendisini konumlandırır. Daha sonra, istemci görünümü veya MDI istemcisi penceresinin istemci penceresinin geri kalanını doldurması için üst öğenin kalan istemci pencere dikdörtgenini değiştirir.

> [!NOTE]
> Denetim çubuğundaki bir düğmenin bir **komut** veya **UPDATE_COMMAND_UI** işleyicisi yoksa, çerçeve otomatik olarak düğmeyi devre dışı bırakır.

## <a name="toolbars"></a>Araç Çubukları

Araç çubuğu, komutları yürüten biteşlenmiş düğmelerin bir satırını görüntüleyen bir denetim çubuğudur. Bir araç çubuğu düğmesine basmak, bir menü öğesi seçmeye eşdeğerdir; menü öğesi araç çubuğu düğmesi ile aynı KIMLIĞE sahipse, bir menü öğesiyle eşlenmiş aynı işleyiciyi çağırır. Düğmeler görüntülenecek ve pushbutton, radyo düğmeleri veya onay kutuları olarak davranacak şekilde yapılandırılabilir. Bir araç çubuğu genellikle bir çerçeve penceresinin üst kısmına hizalanır, ancak MFC araç çubuğu kendi üst penceresinin herhangi bir tarafına "yuvalanabilir" veya kendi mini çerçeve penceresinde float. Bir araç çubuğu ayrıca "float" olabilir ve boyutunu değiştirebilir ve fareyle sürükleyebilirsiniz. Bir araç çubuğu, Kullanıcı fareyi araç çubuğu düğmelerinin üzerine taşırken araç ipuçlarını da gösterebilir. Araç ipucu, düğmenin amacını kısaca açıklayan küçük bir açılan pencere penceresidir.

> [!NOTE]
> MFC sürüm 4,0 itibariyle, sınıf [CToolBar](reference/ctoolbar-class.md) , Windows araç çubuğu ortak denetimini kullanır. Bir `CToolBar` [CToolBarCtrl](reference/ctoolbarctrl-class.md)içerir. Ancak, daha eski araç çubukları hala desteklenmektedir. Bkz. Makale [araç çubukları](mfc-toolbar-implementation.md).

## <a name="status-bars"></a>Durum Çubukları

Durum çubuğu, metin çıkış bölmelerini veya "göstergeleri" içeren bir denetim çubuğudur. Çıkış bölmeleri genellikle ileti satırları ve durum göstergeleri olarak kullanılır. İleti satırı örnekleri, MFC Uygulama Sihirbazı tarafından oluşturulan varsayılan durum çubuğunun en sol bölmesinde seçilen menü veya araç çubuğu komutunu kısaca açıklayan komut Yardım iletisi satırlarını içerir. Durum göstergesi örnekleri, SCROLL LOCK, NUM LOCK ve diğer anahtarları içerir. Durum çubukları genellikle bir çerçeve penceresinin altına hizalanır. Bkz. sınıf [CStatusBar](reference/cstatusbar-class.md) ve [CStatusBarCtrl](reference/cstatusbarctrl-class.md)sınıfı.

## <a name="dialog-bars"></a>İletişim Kutusu Çubukları

İletişim çubuğu, kalıcı olmayan iletişim kutusu işlevselliğiyle iletişim kutusu şablonu kaynağını temel alan bir denetim çubuğudur. İletişim çubukları Windows, özel veya ActiveX denetimleri içerebilir. İletişim kutusunda olduğu gibi, Kullanıcı denetimler arasında sekme oluşturabilir. İletişim çubukları, bir çerçeve penceresinin üst, alt, sol veya sağ tarafına hizalanabilir ve ayrıca kendi çerçeve penceresinde de kaydırılmış olabilir. Bkz. sınıf [CDialogBar](reference/cdialogbar-class.md).

## <a name="rebars"></a>Yeniden çubukları

[Rebar](using-crebarctrl.md) , Rebar denetimleri için yerleştirme, düzen, durum ve kalıcılık bilgileri sağlayan bir denetim çubuğudur. Bir Rebar nesnesi, düzenleme kutuları, araç çubukları ve liste kutuları dahil olmak üzere çeşitli alt Windows, genellikle diğer denetimleri içerebilir. Bir Rebar nesnesi, alt pencerelerini belirtilen bir bit eşlem üzerinde görüntüleyebilir. Bu, kavrayıcı çubuğunu tıklatarak veya sürükleyerek otomatik olarak veya el ile yeniden boyutlandırılabilir. Bkz. sınıf [ekibi çubuğu](reference/crebar-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](user-interface-elements-mfc.md)
