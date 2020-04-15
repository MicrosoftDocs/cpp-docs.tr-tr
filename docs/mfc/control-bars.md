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
ms.openlocfilehash: ceae20c89d9a6d3f4393f838b3594938107785f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353578"
---
# <a name="control-bars"></a>Denetim Çubukları

"Denetim çubuğu" araç çubukları, durum çubukları ve iletişim çubukları için genel addır. MFC `CToolBar`sınıfları `CDialogBar` `COleResizeBar`, `CStatusBar` `CReBar` , , , ve sınıf [CControlBar](../mfc/reference/ccontrolbar-class.md)türetilmiştir , hangi ortak işlevselliği uygular.

Denetim çubukları, kullanıcıların seçenekleri seçebileceği, komutları yürütebileceği veya program bilgilerini alabilecekleri denetim satırlarını görüntüleyen pencerelerdir. Denetim çubukları türleri araç çubuklarını, iletişim çubuklarını ve durum çubuklarını içerir.

- Araç çubukları, [ctoolbar](../mfc/reference/ctoolbar-class.md) sınıfında

- Durum çubukları, [CStatusBar](../mfc/reference/cstatusbar-class.md) sınıfında

- [CDialogBar](../mfc/reference/cdialogbar-class.md) sınıfında iletişim çubukları

- Rebars, [crebar](../mfc/reference/crebar-class.md) sınıfında

> [!IMPORTANT]
> MFC sürüm 4.0 itibariyle, araç çubukları, durum çubukları ve araç ipuçları, MFC'ye özgü önceki uygulama yerine *comctl32.dll'de* uygulanan sistem işlevselliği kullanılarak uygulanır. MFC sürüm 6.0, `CReBar`aynı zamanda comctl32.dll işlevselliğini sarar, eklendi.

Denetim çubuğu türlerine kısa girişler takip eder. Daha fazla bilgi için aşağıdaki bağlantılara bakın.

## <a name="control-bars"></a>Denetim Çubukları

Denetim çubukları, hızlı, tek adımlı komut eylemleri sağlayarak programın kullanılabilirliğini büyük ölçüde artırır. Sınıf, `CControlBar` tüm araç çubuklarının, durum çubuklarının ve iletişim çubuklarının ortak işlevselliğini sağlar. `CControlBar`denetim çubuğunu ana çerçeve penceresinde konumlandırma işlevini sağlar. Denetim çubuğu genellikle bir üst çerçeve penceresinin alt penceresi olduğundan, çerçeve penceresinin istemci görünümüne veya MDI istemcisine "kardeş" olur. Denetim çubuğu nesnesi, kendisini konumlandırmak için üst penceresinin istemci dikdörtgeni hakkındaki bilgileri kullanır. Ardından, istemci görünümünün veya MDI istemci penceresinin istemci penceresinin geri kalanını doldurması için üst öğenin kalan istemci penceresi dikdörtgenini değiştirir.

> [!NOTE]
> Denetim çubuğundaki bir düğmede **KOMUT** veya **UPDATE_COMMAND_UI** işleyicisi yoksa, çerçeve düğmeyi otomatik olarak devre dışı kılabilir.

## <a name="toolbars"></a>Araç Çubukları

Araç çubuğu, komutları gerçekleştiren bir sıra bitmapped düğmeleri görüntüleyen bir denetim çubuğudur. Araç çubuğu düğmesine basMak menü öğesi seçmeye eşdeğerdir; menü öğesi araç çubuğu düğmesiyle aynı kİmliğe sahipse, menü öğesine eşlenen aynı işleyiciyi çağırır. Düğmeler düğme, radyo düğmeleri veya onay kutuları gibi görünecek ve olacak şekilde yapılandırılabilir. Araç çubuğu genellikle çerçeve penceresinin üst tarafına hizalanır, ancak MFC araç çubuğu ana penceresinin herhangi bir tarafına "dock" yapabilir veya kendi mini çerçeve penceresinde yüzebilir. Bir araç çubuğu da "yüzebilir" ve boyutunu değiştirebilir ve bir fare ile sürükleyin. Kullanıcı fareyi araç çubuğunun düğmeleri üzerinde hareket ettikçe araç ipuçları da görüntülenebilir. Araç ipucu, düğmenin amacını kısaca açıklayan küçük bir açılır penceredir.

> [!NOTE]
> MFC sürüm 4.0 itibariyle, [cToolBar](../mfc/reference/ctoolbar-class.md) sınıfı Windows araç çubuğu ortak denetimini kullanır. A `CToolBar` bir [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)içerir. Ancak, eski araç çubukları hala desteklenir. Makaleye bakın [Araç Çubukları](../mfc/mfc-toolbar-implementation.md).

## <a name="status-bars"></a>Durum Çubukları

Durum çubuğu, metin çıktısı bölmeleri veya "göstergeler" içeren bir denetim çubuğudur. Çıktı bölmeleri genellikle ileti satırları ve durum göstergeleri olarak kullanılır. İleti satırı örnekleri, MFC Uygulama Sihirbazı tarafından oluşturulan varsayılan durum çubuğunun en sol bölmesinde seçili menüyü veya araç çubuğu komutunu kısaca açıklayan komut yardım iletisi satırlarını içerir. Durum göstergesi örnekleri scroll LOCK, NUM LOCK ve diğer tuşları içerir. Durum çubukları genellikle çerçeve penceresinin altına hizalanır. Bkz. [cStatusBar](../mfc/reference/cstatusbar-class.md) ve sınıf [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md).

## <a name="dialog-bars"></a>İletişim Kutusu Çubukları

İletişim çubuğu, modeless iletişim kutusu işlevselliği ile bir iletişim şablonu kaynağı dayalı bir denetim çubuğudur. İletişim çubukları Windows, özel veya ActiveX denetimleri içerebilir. Bir iletişim kutusunda olduğu gibi, kullanıcı denetimler arasında sekme olabilir. İletişim çubukları çerçeve penceresinin üst, alt, sol veya sağ tarafına hizalanabilir ve kendi çerçeve penceresinde de yüzdürülebilir. Bkz. sınıf [CDialogBar](../mfc/reference/cdialogbar-class.md).

## <a name="rebars"></a>Geri çubuklar

[Demir çubuğu,](../mfc/using-crebarctrl.md) demir denetimleri için yerleştirme, düzen, durum ve kalıcılık bilgilerini sağlayan bir denetim çubuğudur. Bir demir çubuğu nesnesi, düzenleme kutuları, araç çubukları ve liste kutuları da dahil olmak üzere genellikle diğer denetimler, çeşitli alt pencereler içerebilir. Bir çubuk nesnesi alt pencerelerini belirli bir bit eşlemi üzerinde görüntüleyebilir. Kavrayıcı çubuğunu tıklatarak veya sürükleyerek otomatik olarak veya el ile yeniden boyutlandırılabilir. Bkz. sınıf [CReBar](../mfc/reference/crebar-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı Arabirimi Elemanları](../mfc/user-interface-elements-mfc.md)
