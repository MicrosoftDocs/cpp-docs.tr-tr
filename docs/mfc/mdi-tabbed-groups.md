---
description: 'Daha fazla bilgi edinin: MDI sekmeli grupları'
title: MDI Sekmeli Grupları
ms.date: 11/04/2016
helpviewer_keywords:
- mdi [MFC], tabbed groups
- tabbed grous [MFC]
ms.assetid: 0a464f36-39b7-4e68-8b67-ec175de28377
ms.openlocfilehash: b859445c5cc1e14f19ec91c31b4d618237cfb9a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280774"
---
# <a name="mdi-tabbed-groups"></a>MDI Sekmeli Grupları

Birden çok belge arabirimi (MDI) sekmeli gruplar özelliği, birden çok belge arabirimi (MDI) uygulamalarının MDI istemci alanında bir veya daha fazla sekmeli pencere (ya da sekmeli *Grup* olarak bilinen sekmeli pencere gruplarını) görüntülemesine olanak sağlar. Sekmeli pencereler dikey veya yatay olarak hizalanabilir. Bir uygulama birden fazla MDI sekmeli grubu barındırıyorsa, gruplar bölümlendiricileri ile ayrılır.

## <a name="features"></a>Özellikler

MDI sekmeli gruplarının özellikleri şunlardır:

- Bir uygulama, dinamik olarak sekmeli pencereler oluşturabilir.

- Bir uygulama sekmeli pencereleri yatay veya dikey olarak hizalayabilir.

- Sekmeli pencerelerin grupları, bölümlendiricileri ile ayrılır. Kullanıcı Bölümlendirici kullanarak sekmeli grupları yeniden boyutlandırabilir.

- Kullanıcı gruplar arasında tek tek sekmeler sürükleyebilirsiniz.

- Kullanıcı yeni gruplar oluşturmak için sekmeleri tek tek sürükleyebilir.

- Kullanıcı, kısayol menüsünü kullanarak sekmeleri taşıyabilir veya yeni gruplar oluşturabilir.

- Uygulama, sekmeli pencerelerin yerleşimini kaydedebilir ve yükleyebilir.

- Bir uygulama MDI belgelerinin listesini kaydedebilir ve yükleyebilir.

- Bir uygulama, tek tek sekmeli gruplara erişebilir ve parametrelerini değiştirebilir.

### <a name="using-mdi-tabbed-groups"></a>MDI sekmeli gruplarını kullanma

Aşağıda, MDI sekmeli gruplarıyla yaygın olarak gerçekleştirilen görevler verilmiştir:

- Bir ana çerçeve penceresinde MDI sekmeli gruplarını etkinleştirmek için [Cmdiframewndex:: Enabhadıtabbedgroups](reference/cmdiframewndex-class.md#enablemditabbedgroups)komutunu çağırın. Bu yöntemin ikinci parametresi, sınıfının bir örneğidir `CMDITabInfo` . Varsayılan parametreleri kullanabilir veya çağırabilmeniz için bunları değiştirebilirsiniz `CMDIFrameWndEx::EnableMDITabbedGroups` .

- Çalışma zamanında bir MDI sekmeli grubunun özelliklerini değiştirmek için bir nesne oluşturun veya değiştirin `CMDITabInfo` ve `CMDIFrameWndEx::EnableMDITabbedGroups` yeniden çağırın

- MDI sekmeli pencerelerinin bir listesini almak için çağrısı yapın `CMDIFrameWndEx::GetMDITabGroups` .

- Etkin bir sekmeli grubun yanında yeni bir MDI sekmeli grubu oluşturmak için çağırın `CMDIFrameWndEx::MDITabNewGroup` .

- Giriş odağını sekmeli grubun önceki veya sonraki penceresine kaydırmak için çağrısı yapın `CMDIFrameWndEx::MDITabMoveToNextGroup` .

- Bir pencerenin bir MDI sekmeli grup çağrısının üyesi olup olmadığını belirleme `CMDIFrameWndEx::IsMemberOfMDITabGroup` .

- MDI sekmelerinin veya MDI sekmeli grupların ana çerçeve penceresinde etkinleştirilip etkinleştirilmeyeceğini anlamak için çağırın `CMDIFrameWndEx::AreMDITabs` . Yalnızca MDI sekmeli gruplarının etkinleştirilip etkinleştirilmeyeceğini anlamak için çağırın `CMDIFrameWndEx::IsMDITabbedGroup` .

- Kullanıcı bir sekmeye tıkladığında veya başka bir MDI sekmeli grubuna sürüklendiğinde kısayol menüsünü göstermek için, `CMDIFrameWndEx::OnShowMDITabContextMenu` `CMDIFrameWndEx` -türetilmiş sınıfta geçersiz kılın. Bu yöntemi gerçekleştirmeyin, uygulama kısayol menüsünü görüntülemez.

- Bir uygulamadaki MDI sekmeli gruplarının yerleşimini kaydetmek için çağırın `CMDIFrameWndEx::SaveMDIState` . Daha önce kaydedilmiş bir MDI sekmeli grup profilini yüklemek için çağrısı yapın `CMDIFrameWndEx::LoadMDIState` . Ayrıca, açık belgelerin listesini bir MDI uygulamasında yüklemek veya kaydetmek için bu yöntemleri çağırabilirsiniz. MDI durumunu kaydetme ve yükleme hakkında daha fazla bilgi için bkz. [Cmdiframewndex:: LoadMDIState](reference/cmdiframewndex-class.md#loadmdistate).

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](user-interface-elements-mfc.md)<br/>
[CMDIFrameWndEx sınıfı](reference/cmdiframewndex-class.md)<br/>
[Cmdictepdwndex sınıfı](reference/cmdichildwndex-class.md)<br/>
[CMDITabInfo sınıfı](reference/cmditabinfo-class.md)
