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
ms.openlocfilehash: 0f8cb2a8f3ccb36f3fa1ed2bf3f81087691ce988
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404416"
---
# <a name="interface-elements"></a>Arabirim Öğeleri

Bu belge, Visual Studio 2008 SP1'de tanıtılan arabirimi öğelerini açıklar ve ayrıca Kitaplığı'nın önceki sürümünü farklılıklar açıklanmaktadır.

Aşağıda yeni arabirim öğeleri kullanılarak oluşturulan bir uygulama gösterilmektedir.

![MFC özellik paketi örnek uygulama](../mfc/media/mfc_featurepack.png "mfc_featurepack")

## <a name="window-docking"></a>Yerleştirme penceresi

Pencere yerleştirme işlevleri Visual Studio grafik kullanıcı arabirimi kullandığını yerleştirme penceresi benzer.

## <a name="control-bars-are-now-panes"></a>Denetim çubukları artık bölmeleri bulunur

Denetim çubukları artık panolar olarak bilinir ve türetilmiş [CBasePane sınıfı](../mfc/reference/cbasepane-class.md). Denetim çubukları temel sınıfını MFC önceki sürümlerde olduğu `CControlBar`.

Uygulamanın ana çerçeve penceresinin genellikle tarafından temsil edilen [CFrameWndEx sınıfı](../mfc/reference/cframewndex-class.md) veya [Cmdıframewndex sınıfı](../mfc/reference/cmdiframewndex-class.md). Ana çerçeve adlı *site dock*. Bölmeleri üst öğeyi üç türlerden biri olabilir: bir dock sitesine, bir dock çubuğu veya mini çerçevenin.

Bölmeleri iki tür vardır: yeniden boyutlandırılabilir olmayan ve yeniden boyutlandırılabilir. Durum çubukları ve araç çubukları gibi yeniden boyutlandırılabilir bölmeleri ayırıcılar veya kaydırıcıları kullanarak yeniden boyutlandırılabilir. Yeniden boyutlandırılabilir bölmeleri (bir başka bir bölüme, bunlar arasında bir ayırıcı oluşturmak için yerleştirilmiş olabilir) bir kapsayıcı oluşturabilir. Ancak, yeniden boyutlandırılabilir bölmeleri çubukları sabitlemek için (yerleşik) eklenemiyor.

Uygulamanızı yeniden boyutlandırılabilir olmayan bölmeleri kullanıyorsa, onlardan türetilen [CPane sınıfı](../mfc/reference/cpane-class.md).  Uygulamanızı yeniden boyutlandırılabilir bölmeleri kullanıyorsa, onlardan türetilen [CDockablePane sınıfı](../mfc/reference/cdockablepane-class.md)

## <a name="dock-site"></a>Dock sitesiyle

Dock sitesiyle (veya ana çerçeve penceresinin) tüm bölmeleri ve uygulama kısa çerçeve pencerelerinde sahip olur. Dock sitesiyle içeren bir [CDockingManager](../mfc/reference/cdockingmanager-class.md) üyesi. Bu üye, dock sitesine ait tüm bölmeleri listesini tutar. Dock sitesiyle dış kenarları sırasında oluşturulan bölmeleri listenin başında konumlandırılır böylece Liste sıralanmıştır. Dock sitesiyle framework yeniden çizer, bu liste üzerinde döngü ve her bölmede dock sitesine geçerli sınırlayıcı dikdörtgenini içerecek şekilde düzenini ayarlar. Çağırabilirsiniz `AdjustDockingLayout` veya `RecalcLayout` zaman yerleştirme düzeni ayarlamak sahip ve yerleştirme Yöneticisi bu çağrı framework yönlendirir.

## <a name="dock-bars"></a>Dock çubukları

Her bir ana çerçeve penceresinin konumlandırabilirsiniz *çubukları yerleştirme* kenarlıkları boyunca. Bir dock çubuğudur ait bir bölme bir [CDockSite sınıfı](../mfc/reference/cdocksite-class.md). Dock çubukları öğesinden türetilen nesneler kabul edebilir [CPane](../mfc/reference/cpane-class.md), araç çubukları gibi. Ana çerçeve penceresinin başlatıldığında dock çubukları oluşturmak için arama `EnableDocking`. Otomatik Gizle çubuklarını etkinleştirmek için çağrı `EnableAutoHideBars`. `EnableAutoHideBars` oluşturur [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md) nesneleri ve bunları her dock çubuğunun yanında yerleştirir.

Her bir dock çubuğun dock satırlara ayrılmıştır. Dock satırları tarafından temsil edilir [CDockingPanesRow sınıfı](../mfc/reference/cdockingpanesrow-class.md). Her dock satır araç çubukları listesini içerir. Bir kullanıcı bir araç çubuğu docks ya da araç bir satırdan aynı dock çubuğu içinde diğerine taşır. framework yeni bir satır oluşturur ve dock çubuğu buna göre yeniden boyutlandırır veya mevcut bir satırı üzerinde araç yerleştirir.

## <a name="mini-frame-windows"></a>Windows mini çerçeve

Bir kayan bölme başlığının bir mini çerçeve penceresinde bulunur. Mini çerçeve pencereleri iki sınıf tarafından temsil edilir: [Cmdıtabınfo sınıfı](../mfc/reference/cmditabinfo-class.md) (yalnızca bir bölme içerebilir) ve [CMultiPaneFrameWnd sınıfı](../mfc/reference/cmultipaneframewnd-class.md) (birkaç bölmeleri içerebilir). Kodunuzda bir bölme kaydırmak için çağrı [CBasePane::FloatPane](../mfc/reference/cbasepane-class.md#floatpane). Bir bölme gezinen sonra framework otomatik olarak bir mini çerçeve penceresi oluşturur ve bu Mini çerçeve kayan bölme üst olur. Kayan bölme noktalarını, üst çerçeve sıfırlar ve bir dock çubuğu (için araç çubukları) veya bir dock sitesine (yeniden boyutlandırılabilir bölmeleri için) kayan bölme başlığının olur.

## <a name="pane-dividers"></a>Bölücü bölmesi

Bölmesinde Bölücü (kaydırıcıları veya ayırıcılar da adlandırılır) tarafından temsil edilir [CPaneDivider sınıfı](../mfc/reference/cpanedivider-class.md). Bir kullanıcı bir bölme docks, framework bölmesinde Bölücü, bölmesinin dock sitesine veya başka bir bölme yerleştirildiğini bağımsız olarak oluşturur. Bir bölme dock sitesine noktaları çalıştırdığınızda bölmesinde ayırıcı olarak adlandırılır *bölmesinde ayırıcı varsayılan*. Varsayılan bölmesinde ayırıcı dock sitedeki tüm yerleştirme bölmesine düzenini sorumludur. Dock Yöneticisi'ni varsayılan bölmesinde Bölücü listesini ve bölmeleri listesini tutar. Dock yöneticileri için tüm yerleştirme bölmesine düzenini sorumludur.

## <a name="containers"></a>Kapsayıcılar

Birbiriyle yerleştirildiğinde tüm yeniden boyutlandırılabilir bölmeleri kapsayıcılarda korunur. Kapsayıcıları tarafından temsil edilir [CPaneContainer sınıfı](../mfc/reference/cpanecontainer-class.md). Her kapsayıcı, sol ve sağ parçaları arasında işaretçileri, sol bölmede, sağ bölmede, sol alt kapsayıcıda, sağ alt kapsayıcısı ve bölme vardır. (*Sol* ve *doğru* fiziksel kenarlara atıfta bulunmayan, ancak bunun yerine bir ağaç yapısı dalları belirleyin.) Bu şekilde size bölme ve ayırıcılar ağacının oluşturun ve bu nedenle birlikte yeniden boyutlandırılabilir bölme karmaşık düzenleri elde etmek. `CPaneContainer` Sınıfı kapsayıcılar ağacı tutar; ayrıca bölmeleri ve bu ağacında bulunan kaydırıcıları iki listelerini tutar. Bölmesinde kapsayıcı yöneticileri genellikle varsayılan kaydırıcıları ve birden fazla bölme taşıyan Mini çerçeve pencereleri gömülür.

## <a name="auto-hide-control-bars"></a>Otomatik gizleme denetim çubukları

Varsayılan olarak, her `CDockablePane` otomatik gizleme özelliğini destekler. Bir kullanıcı, açıklamalı alt yazısı üzerinde görünen pin düğmesini tıkladığında `CDockablePane`, framework bölmesinde otomatik gizleme moduna geçer. Öğesini işlemek için çerçeve oluşturur. bir [CMFCAutoHideBar sınıfı](../mfc/reference/cmfcautohidebar-class.md) ve [CMFCAutoHideButton sınıfı](../mfc/reference/cmfcautohidebutton-class.md) ilişkili `CMFCAutoHideBar` nesne. Framework yeni koyar `CMFCAutoHideBar` üzerinde [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md). Framework ayrıca ekler `CMFCAutoHideButton` araç. [CDockingManager sınıfı](../mfc/reference/cdockingmanager-class.md) tutar `CDockablePane`.

## <a name="tabbed-control-bars-and-outlook-bars"></a>Denetim çubuklarını sekmeli ve Outlook Çubuğu

[CMFCBaseTabCtrl sınıfı](../mfc/reference/cmfcbasetabctrl-class.md) sekmeli pencere çıkarılabilir sekmeler içeren temel işlevselliğini uygular. Kullanılacak bir `CMFCBaseTabCtrl` nesne, başlatmak bir [CBaseTabbedPane sınıfı](../mfc/reference/cbasetabbedpane-class.md) uygulamanızdaki. `CBaseTabbedPane` türetilen `CDockablePane` ve bir işaretçi tutar bir `CMFCBaseTabCtrl` nesne. `CBaseTabbedPane` Dock ve sekmeli denetim çubukları yeniden boyutlandırmak kullanıcıların sağlar. Kullanım [CDockablePane::AttachToTabWnd](../mfc/reference/cdockablepane-class.md#attachtotabwnd) yerleştirilmiş ve sekmeli denetim çubukları dinamik olarak oluşturmak için.

Outlook çubuğu denetimini de sekmeli çubuklara dayalıdır. [CMFCOutlookBar sınıfı](../mfc/reference/cmfcoutlookbar-class.md) türetilir `CBaseTabbedPane`. Outlook Çubuğu kullanma hakkında daha fazla bilgi için bkz. [CMFCOutlookBar sınıfı](../mfc/reference/cmfcoutlookbar-class.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../mfc/mfc-concepts.md)

