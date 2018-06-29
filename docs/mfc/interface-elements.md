---
title: Arabirim öğeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- architecture [MFC], MFC Feature Pack
- MFC Feature Pack, architecture
ms.assetid: eead6827-9602-40a3-8038-8986e8207385
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1906505e75273cc62a0eac55e6ed1a9686a3b76f
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078450"
---
# <a name="interface-elements"></a>Arabirim Öğeleri
Bu belge, Visual Studio 2008 SP1'de sunulan arabirimi öğelerini açıklar ve ayrıca kitaplığı önceki sürümünün farklılıkları açıklar.  
  
 Aşağıdaki çizimde yeni arabirim öğeleri kullanılarak oluşturulan bir uygulamayı gösterir.  
  
 ![MFC özellik paketi örnek uygulama](../mfc/media/mfc_featurepack.png "mfc_featurepack")  
  
## <a name="window-docking"></a>Yerleştirme penceresi  
 Pencere işlevselliği yerleştirme benzeyen, yerleştirme penceresi [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] grafik kullanıcı arabirimini kullanır.  
  
## <a name="control-bars-are-now-panes"></a>Denetim çubukları şimdi bölmeleri olan  
 Denetim çubukları şimdi bölmeleri bilinir ve türetilmiş [CBasePane sınıfı](../mfc/reference/cbasepane-class.md). Denetim çubukları temel sınıfını MFC önceki sürümlerinde olduğu `CControlBar`.  
  
 Uygulama ana çerçeve penceresi genellikle tarafından temsil edilen [CFrameWndEx sınıfı](../mfc/reference/cframewndex-class.md) veya [CMDIFrameWndEx sınıfı](../mfc/reference/cmdiframewndex-class.md). Ana çerçeve adlı *site yerleştirme*. Bölmeleri üst üç türden biri olabilir: yerleştirme site, bir stok çubuğu veya bir kısa çerçeve penceresi.  
  
 Bölmeleri iki tür vardır: yeniden boyutlandırılabilir olmayan ve yeniden boyutlandırılabilir. Durum çubukları ve araç çubukları gibi yeniden boyutlandırılabilir bölmeleri ayırıcılar veya kaydırıcıları kullanarak yeniden boyutlandırılabilir. Yeniden boyutlandırılabilir bölmeleri kapsayıcıları (bir bölme bir ayırıcı aralarında oluşturma başka bir bölme yerleştirilmiş) oluşturabilir. Ancak, yeniden boyutlandırılabilir bölmeleri (çubukları sabitlemek için yerleşik) eklenemiyor.  
  
 Uygulamanızı yeniden boyutlandırılabilir olmayan bölmeleri kullanıyorsa, onlardan türetilen [CPane sınıfı](../mfc/reference/cpane-class.md).  Uygulamanızı yeniden boyutlandırılabilir bölmeleri kullanıyorsa, onlardan türetilen [CDockablePane sınıfı](../mfc/reference/cdockablepane-class.md)  
  
## <a name="dock-site"></a>Yerleştirme Site  
 Yerleştirme site (veya ana çerçeve penceresi) tüm bölmeleri ve uygulamanın kısa çerçeve pencerelerinde sahip olur. Yerleştirme site içeren bir [CDockingManager](../mfc/reference/cdockingmanager-class.md) üyesi. Bu üye yerleştirme siteye ait tüm bölmeleri listesini tutar. Böylece yerleştirme site dış kenarlarında oluşturulan bölmeleri listenin başlangıcında yerleştirilmiş liste sıralanır. Framework yerleştirme site yeniden çizer, bu liste döngüler ve geçerli sınırlayıcı dikdörtgenini yerleştirme sitenin dahil etmek için her bölme düzenini ayarlar. Çağırabilirsiniz `AdjustDockingLayout` veya `RecalcLayout` ne zaman yerleştirme düzeni ayarlamak sahip ve yerleştirme Yöneticisi bu çağrıyı framework yönlendirir.  
  
## <a name="dock-bars"></a>Yerleştirme çubukları  
 Her ana çerçeve penceresi yerleştirebilirsiniz *çubukları yerleştirme* kenarlıkları boyunca. Bir yuva çubuğu ait bölmesidir bir [CDockSite sınıfı](../mfc/reference/cdocksite-class.md). Yerleştirme çubukları türetilmiş nesneleri kabul edebileceği [CPane](../mfc/reference/cpane-class.md), araç çubukları gibi. Ana çerçeve penceresi başlatıldığında yerleştirme çubukları oluşturmak için arama `EnableDocking`. Otomatik Gizle çubuklarını etkinleştirmek için arama `EnableAutoHideBars`. `EnableAutoHideBars` oluşturur [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md) nesneleri ve her yerleştirme çubuğunun yanında yerleştirir.  
  
 Her yerleştirme çubuğu yerleştirme satırlara ayrılmıştır. Yerleştirme satırları temsil ettiği [CDockingPanesRow sınıfı](../mfc/reference/cdockingpanesrow-class.md). Her yerleştirme satır araç çubukları listesini içerir. Bir kullanıcı bir araç çubuğu docks veya aynı yerleştirme çubuğu içindeki başka bir tek satırdan araç giderse, framework yeni bir satır oluşturur ve yerleştirme çubuğu buna göre yeniden boyutlandırır veya var olan bir satır üzerinde araç yerleştirir.  
  
## <a name="mini-frame-windows"></a>Kısa çerçeve pencereleri  
 Kayan bölmesinde bir kısa çerçeve penceresinde bulunur. Kısa çerçeve pencereleri iki sınıfları tarafından temsil edilen: [CMDITabInfo sınıfı](../mfc/reference/cmditabinfo-class.md) (hangi yalnızca bir bölme içerebilir) ve [CMultiPaneFrameWnd sınıfı](../mfc/reference/cmultipaneframewnd-class.md) (hangi birkaç bölmeleri içerebilir). Bir bölme kodunuzda float çağrısı [CBasePane::FloatPane](../mfc/reference/cbasepane-class.md#floatpane). Bir bölme gezinen sonra framework bir kısa çerçeve penceresi otomatik olarak oluşturur ve bu kısa çerçeve penceresi kayan bölmesinde 's üst olur. Kayan bölmesinde noktaları, kendi üst framework sıfırlar ve kayan bölmesinde bir yerleştirme çubuğu (için araç çubukları) veya bir yerleştirme sitesi (yeniden boyutlandırılabilir bölmeleri) olur.  
  
## <a name="pane-dividers"></a>Bölmesinde Bölücü  
 (Ayrıca kaydırıcılar veya ayırıcılar adlı) bölmesinde Bölücü temsil ettiği [CPaneDivider sınıfı](../mfc/reference/cpanedivider-class.md). Bir kullanıcı bir bölme docks framework bölmesinde Bölücü, bölmenin yerleştirme sitede veya başka bir bölme yerleşik olduğunda bağımsız olarak oluşturur. Bir bölme yerleştirme siteye noktalarını bölmesinde ayırıcı denir *bölmesinde ayırıcı varsayılan*. Varsayılan bölmesinde ayırıcı yerleştirme sitedeki tüm takma bölmeleri düzenini sorumludur. Yerleştirme Yöneticisi'ni varsayılan bölmesinde Bölücü listesini ve bölmeleri listesini tutar. Yerleştirme yöneticileri tüm takma bölmeleri düzeni için sorumludur.  
  
## <a name="containers"></a>Kapsayıcılar  
 Birbirine yerleştirildiğinde tüm yeniden boyutlandırılabilir bölmeleri kapsayıcılarında saklanır. Kapsayıcıları temsil ettiği [CPaneContainer sınıfı](../mfc/reference/cpanecontainer-class.md). Her kapsayıcısı, sol ve sağ bölümleri arasında sol bölmede, sağ bölmede, sol alt kapsayıcısı, sağ alt kapsayıcısı ve Bölümlendirici işaretçiler içerir. (*Sol* ve *sağ* fiziksel kenarlara başvurmadığından ancak bunun yerine bir ağaç yapısı dalları tanımlayın.) Bu şekilde biz bölmeleri ve ayırıcılar ağacının oluşturun ve bu nedenle birlikte yeniden boyutlandırılabilir bölmeleri, karmaşık düzenleri elde etmek. `CPaneContainer` Sınıfı kapsayıcıları ağacının korur; aynı zamanda bölmeleri ve bu ağacında bulunan kaydırıcılar iki listelerini tutar. Bölmesinde kapsayıcı yöneticileri, genellikle varsayılan kaydırıcılar ve birden çok bölmeleri taşımak kısa çerçeve pencereleri katıştırılır.  
  
## <a name="auto-hide-control-bars"></a>Otomatik olarak gizle denetim çubukları  
 Varsayılan olarak, her `CDockablePane` otomatik gizleme özelliğini destekler. Bir kullanıcı, resim yazısını PIN düğmesine tıkladığında `CDockablePane`, framework bölmesinde otomatik olarak gizle moduna geçer. Öğesini işlemek için çerçevesini oluşturur bir [CMFCAutoHideBar sınıfı](../mfc/reference/cmfcautohidebar-class.md) ve [CMFCAutoHideButton sınıfı](../mfc/reference/cmfcautohidebutton-class.md) ile ilişkili `CMFCAutoHideBar` nesnesi. Framework'te yeni koyar `CMFCAutoHideBar` üzerinde [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md). Framework de iliştirir `CMFCAutoHideButton` araç. [CDockingManager sınıfı](../mfc/reference/cdockingmanager-class.md) tutar `CDockablePane`.  
  
## <a name="tabbed-control-bars-and-outlook-bars"></a>Sekmeli denetim çubukları ve Outlook Çubukları  
 [CMFCBaseTabCtrl sınıfı](../mfc/reference/cmfcbasetabctrl-class.md) çıkarılabilir sekmelerle sekmeli bir pencere temel işlevlerini uygular. Kullanılacak bir `CMFCBaseTabCtrl` nesnesini, başlatma bir [CBaseTabbedPane sınıfı](../mfc/reference/cbasetabbedpane-class.md) uygulamanızda. `CBaseTabbedPane` türetilmiş `CDockablePane` ve bir işaretçi tutar bir `CMFCBaseTabCtrl` nesnesi. `CBaseTabbedPane` Yerleştirme ve sekmeli denetim çubukları yeniden boyutlandırmak kullanıcıların sağlar. Kullanım [CDockablePane::AttachToTabWnd](../mfc/reference/cdockablepane-class.md#attachtotabwnd) yerleşik ve sekmeli denetim çubukları dinamik olarak oluşturulacak.  
  
 Outlook Çubuğu denetimi de sekmeli çubuklarında dayalıdır. [CMFCOutlookBar sınıfı](../mfc/reference/cmfcoutlookbar-class.md) türetildiği `CBaseTabbedPane`. Outlook Çubuğu kullanma hakkında daha fazla bilgi için bkz: [CMFCOutlookBar sınıfı](../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../mfc/mfc-concepts.md)

