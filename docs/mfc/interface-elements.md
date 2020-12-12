---
description: 'Daha fazla bilgi edinin: arabirim öğeleri'
title: Arabirim Öğeleri
ms.date: 11/19/2018
helpviewer_keywords:
- architecture [MFC], MFC Feature Pack
- MFC Feature Pack, architecture
ms.assetid: eead6827-9602-40a3-8038-8986e8207385
ms.openlocfilehash: a0aa762455f6bfe97d371244682c66dbd141a761
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228059"
---
# <a name="interface-elements"></a>Arabirim Öğeleri

Bu belge, Visual Studio 2008 SP1 'de tanıtılan arabirim öğelerini açıklar ve ayrıca kitaplığın önceki sürümüyle farkları açıklar.

Aşağıdaki çizimde, yeni arabirim öğeleri kullanılarak oluşturulan bir uygulama gösterilmektedir.

![MFC özellik paketi örnek uygulaması](../mfc/media/mfc_featurepack.png "MFC özellik paketi örnek uygulaması")

## <a name="window-docking"></a>Pencere yerleştirme

Pencere yerleştirme işlevselliği, Visual Studio Grafik Kullanıcı arabiriminin kullandığı pencere yerleştirme işlevine benzer.

## <a name="control-bars-are-now-panes"></a>Denetim çubukları artık Bölmelerdir

Denetim çubukları artık bölmeler olarak bilinir ve [CBasePane sınıfından](reference/cbasepane-class.md)türetilir. MFC 'nin önceki sürümlerinde denetim çubuklarının temel sınıfı idi `CControlBar` .

Uygulama ana çerçevesi penceresi genellikle [CFrameWndEx sınıfı](reference/cframewndex-class.md) veya [CMDIFrameWndEx sınıfı](reference/cmdiframewndex-class.md)tarafından temsil edilir. Ana çerçeveye *Dock sitesi* denir. Bölmeler üç tür üst türden birine sahip olabilir: bir dock sitesi, Dock çubuğu veya bir mini çerçeve penceresi.

İki tür bölme vardır: yeniden boyutlandırılabilir ve yeniden boyutlandırılabilir. Durum çubukları ve araç çubukları gibi yeniden boyutlandırılabilir bölmeler, bölümlendiricileri veya kaydırıcıları kullanarak yeniden boyutlandırılabilir. Yeniden boyutlandırılabilir bölmeler kapsayıcı oluşturabilir (bir bölme başka bir bölmeye yerleştirilebilir, aralarında bir bölme oluşturulabilir). Ancak, yeniden boyutlandırılabilir bölmeler, yerleştirme çubuklarına iliştirilemez (sabitlenemez).

Uygulamanız yeniden boyutlandırılabilir bölmeler kullanıyorsa [CPane sınıfından](reference/cpane-class.md)türetirsiniz.  Uygulamanız yeniden boyutlandırılabilir bölmeler kullanıyorsa [CDockablePane sınıfından](reference/cdockablepane-class.md) türet

## <a name="dock-site"></a>Siteyi yerleştir

Dock sitesi (veya ana çerçeve penceresi), bir uygulamadaki tüm bölmelere ve mini çerçeve pencerelere sahip olur. Dock sitesi bir [CDockingManager](reference/cdockingmanager-class.md) üyesi içeriyor. Bu üye, Dock sitesine ait olan tüm bölmelerin bir listesini tutar. Liste, dock sitesinin dış kenarlarındaki oluşturulan bölmelerin listenin başlangıcında konumlandırılması için sıralanır. Framework dock sitesini yeniden çizer, bu liste üzerinde döngü yapar ve her bölmenin yerleşimini dock sitesinin geçerli sınırlayıcı dikdörtgenini içerecek şekilde ayarlar. `AdjustDockingLayout` `RecalcLayout` Takma düzeni ayarlamanız gerektiğinde veya ' yi çağırabilir ve Framework bu çağrıyı yerleştirme Yöneticisi 'ne yönlendirir.

## <a name="dock-bars"></a>Yerleştirme çubukları

Her bir ana çerçeve penceresi, çizgi *çubuklarının* kenarlıklarını üzerinde konumlandırabilirsiniz. Takma çubuğu, [CDockSite sınıfına](reference/cdocksite-class.md)ait olan bir bölmesidir. Yerleştirme çubukları, [CPane](reference/cpane-class.md)'dan türetilmiş ve araç çubukları gibi nesneleri kabul edebilir. Ana çerçeve penceresi başlatıldığında yerleştirme çubukları oluşturmak için çağırın `EnableDocking` . Otomatik gizleme çubuklarını etkinleştirmek için çağrısı yapın `EnableAutoHideBars` . `EnableAutoHideBars`[CAutoHideDockSite](reference/cautohidedocksite-class.md) nesneleri oluşturur ve her bir dock çubuğunun yanına konumlandırır.

Her Dock çubuğu, Dock satırlarına bölünmüştür. Dock satırları [CDockingPanesRow sınıfı](reference/cdockingpanesrow-class.md)tarafından temsil edilir. Her dock Satırı araç çubuklarının bir listesini içerir. Bir Kullanıcı bir araç çubuğunu veya araç çubuğunu aynı yuva çubuğunda bir satırdan diğerine taşıdığında, çerçeve yeni bir satır oluşturur ve Dock çubuğunu uygun şekilde yeniden boyutlandırır ya da araç çubuğunu varolan bir satıra konumlandırır.

## <a name="mini-frame-windows"></a>Mini çerçeve pencereleri

Kayan bölme bir mini çerçeve penceresinde bulunur. Mini çerçeve pencereleri iki sınıf tarafından temsil edilir: [Cmditabınfo sınıfı](reference/cmditabinfo-class.md) (yalnızca bir bölme içerebilir) ve [Cmultipane framewnd sınıfı](reference/cmultipaneframewnd-class.md) (çeşitli bölmeler içerebilen). Kodunuzda bir bölmeyi kaydırmak için [CBasePane:: FloatPane](reference/cbasepane-class.md#floatpane)' ı çağırın. Bir bölme üstten sonra çerçeve otomatik olarak bir mini çerçeve penceresi oluşturur ve bu mini çerçeve penceresi kayan bölmenin üst öğesi olur. Kayan bölme noktaları, çerçeve üst öğesini sıfırlar ve kayan bölme bir yuva çubuğu (araç çubukları için) veya bir dock sitesi (yeniden boyutlandırılabilir bölmeler için) olur.

## <a name="pane-dividers"></a>Bölme bölücüleri

Bölme bölücüleri (kaydırıcıları veya bölümlendiricileri de adlandırılır) [CPaneDivider sınıfı](reference/cpanedivider-class.md)tarafından temsil edilir. Bir Kullanıcı bir bölmeyi oluşturduğunda, bölmenin yerleştirme sitesine veya başka bir bölmeye yerleştirilmiş olmasına bakılmaksızın çerçeve bölme bölücüleri oluşturur. Dock sitesine bir bölme noktaları, bölme ayracına *varsayılan bölme etiketi* olarak adlandırılır. Varsayılan bölme bölücü, Dock sitesindeki tüm yerleştirme bölmelerinin düzeninden sorumludur. Dock Manager, varsayılan bölme bölücülerin ve bir bölme listesinin bir listesini tutar. Dock yöneticileri, tüm yerleştirme bölmelerinin düzeninden sorumludur.

## <a name="containers"></a>Kapsayıcılar

Birbirine yerleştirilmiş olan tüm yeniden boyutlandırılabilir bölmeler kapsayıcılar içinde tutulur. Kapsayıcılar [Cbölmesi kapsayıcı sınıfı](reference/cpanecontainer-class.md)tarafından temsil edilir. Her kapsayıcının sol bölmesi, sağ bölmesi, sol alt kapsayıcı, sağ alt kapsayıcı ve sol ve sağ parçalar arasındaki Bölümlendirici işaretçileri vardır. (*Sol* ve *sağ* , fiziksel kenarlara başvurmayın, bunun yerine bir ağaç yapısının dallarını belirler.) Bu şekilde, bir dizi bölme ve bölümlendiricileri derleyebilir ve bu nedenle birlikte yeniden boyutlandırılabileceğiniz karmaşık bölme düzenlerine ulaşabilirsiniz. `CPaneContainer`Sınıfı kapsayıcı ağacını korur; Ayrıca bu ağaçta bulunan bölme ve kaydırıcıların iki listesini de korur. Bölme kapsayıcısı yöneticileri, genellikle birden çok bölme gerçekleştiren varsayılan kaydırıcılar ve mini çerçeve pencereleri içine gömülür.

## <a name="auto-hide-control-bars"></a>Denetim çubuklarını otomatik gizle

Varsayılan olarak, her biri `CDockablePane` otomatik gizleme özelliğini destekler. Bir Kullanıcı öğesinin açıklamalı alt yazısının sabitleme düğmesine tıkladığında `CDockablePane` Framework, bölmeyi otomatik gizleme moduna geçirir. Tıklama, tıklamak için bir [CMFCAutoHideBar sınıfı](reference/cmfcautohidebar-class.md) ve nesneyle Ilişkili bir [CMFCAutoHideButton sınıfı](reference/cmfcautohidebutton-class.md) oluşturur `CMFCAutoHideBar` . Framework, `CMFCAutoHideBar` [CAutoHideDockSite](reference/cautohidedocksite-class.md)üzerine yeni bir koyar. Çerçeve araç çubuğuna da ekler `CMFCAutoHideButton` . [CDockingManager sınıfı](reference/cdockingmanager-class.md) , öğesini saklar `CDockablePane` .

## <a name="tabbed-control-bars-and-outlook-bars"></a>Sekmeli denetim çubukları ve Outlook çubukları

[CMFCBaseTabCtrl sınıfı](reference/cmfcbasetabctrl-class.md) , bir sekmeli pencerenin temel işlevlerini çıkarılabilir sekmelerle uygular. Bir nesnesi kullanmak için `CMFCBaseTabCtrl` , uygulamanızda bir [CBaseTabbedPane sınıfı](reference/cbasetabbedpane-class.md) başlatın. `CBaseTabbedPane` , öğesinden türetilir `CDockablePane` ve bir nesneye yönelik bir işaretçi tutar `CMFCBaseTabCtrl` . , `CBaseTabbedPane` Kullanıcıların sekmeli Denetim çubuklarını yerleştirmeyi ve yeniden boyutlandırmasını sağlar. Yerleştirilmiş ve sekmeli Denetim çubuklarını dinamik olarak oluşturmak için [CDockablePane:: AttachToTabWnd](reference/cdockablepane-class.md#attachtotabwnd) kullanın.

Outlook çubuğu denetimi de sekmeli çubuklara dayalıdır. [CMFCOutlookBar sınıfı](reference/cmfcoutlookbar-class.md) öğesinden türetilir `CBaseTabbedPane` . Outlook çubuğu kullanma hakkında daha fazla bilgi için bkz. [CMFCOutlookBar sınıfı](reference/cmfcoutlookbar-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](mfc-concepts.md)
