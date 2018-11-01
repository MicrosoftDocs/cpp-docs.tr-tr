---
title: MDI Sekmeli Grupları
ms.date: 11/04/2016
helpviewer_keywords:
- mdi [MFC], tabbed groups
- tabbed grous [MFC]
ms.assetid: 0a464f36-39b7-4e68-8b67-ec175de28377
ms.openlocfilehash: cefd97b377c2755b158830d8e649ac40f90fee11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544501"
---
# <a name="mdi-tabbed-groups"></a>MDI Sekmeli Grupları

Birden çok belge arabirimi (MDI) uygulamaları, bir veya daha fazla sekmeli pencerelerin görüntülemek birden çok belge arabirimi (MDI) sekmeli grupları özelliği sağlar (ya da grupları olarak bilinen sekmeli pencerelerin *sekmeli grupları*) MDI istemci alanında. Sekmeli pencerelerin dikey veya yatay yönde hizalanabilir. Bir uygulamanın birden fazla MDI sekmeli Grup barındırıyorsa, Grup ayırıcılar tarafından ayrılır.

## <a name="features"></a>Özellikler

MDI sekmeli gruplarının özellikleri şunlardır:

- Bir uygulama sekmeli pencerelerin dinamik olarak oluşturabilir.

- Bir uygulama, yatay veya dikey olarak sekmeli pencerelerin hizalayabilirsiniz.

- Sekmeli windows gruplarının ayırıcılar tarafından ayrılır. Kullanıcı, ayırıcıyı kullanarak sekmeli grupları genişletebilir.

- Kullanıcı, tek tek sekme grupları arasında sürükleyebilirsiniz.

- Kullanıcı, yeni gruplar oluşturabilmesi için ayrı ayrı sekmeler sürükleyebilirsiniz.

- Kullanıcının sekme taşıyabilir veya kısayol menüsünü kullanarak yeni gruplar oluşturabilir.

- Bir uygulamayı kaydedebilir ve sekmeli pencere düzenini yükleyin.

- Bir uygulamayı kaydedebilir ve MDI belge listesi yüklenemedi.

- Bir uygulamanın tek tek sekmeli gruplar erişebilir ve kendi parametrelerini değiştirin.

### <a name="using-mdi-tabbed-groups"></a>Kullanarak MDI sekmeli grupları

MDI sekmeli grupları ile yaygın olarak gerçekleştirilen görevler şunlardır:

- MDI sekmeli grupları için bir ana çerçeve penceresi etkinleştirmek için çağrı [CMDIFrameWndEx::EnableMDITabbedGroups](../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups). Bu yöntem, ikinci parametresinin örneğidir `CMDITabInfo` sınıfı. Varsayılan parametreleri kullanan veya çağırmadan önce bunları değiştirmeniz `CMDIFrameWndEx::EnableMDITabbedGroups`.

- Çalışma zamanında bir MDI sekmeli grubunun özelliklerini değiştirmek için oluşturma veya değiştirme bir `CMDITabInfo` nesne ve çağrı `CMDIFrameWndEx::EnableMDITabbedGroups` yeniden

- MDI listesini almak için windows sekmeli, çağrı `CMDIFrameWndEx::GetMDITabGroups`.

- Etkin bir sekmeli grubunun yanındaki yeni bir MDI sekmeli grup oluşturmak için arama `CMDIFrameWndEx::MDITabNewGroup`.

- Sekmeli Grup önceki veya sonraki pencerenin giriş odağı için çağrı `CMDIFrameWndEx::MDITabMoveToNextGroup`.

- Bir pencere bir MDI üyesi olup olmadığını belirlemek için grubun çağrı sekmeli `CMDIFrameWndEx::IsMemberOfMDITabGroup`.

- MDI sekmeleri veya MDI sekmeli grupları için bir ana çerçeve penceresi etkin olup olmadığını belirlemek için çağrı `CMDIFrameWndEx::AreMDITabs`. Yalnızca MDI sekmeli gruplarının etkin olup olmadığını belirlemek için çağrı `CMDIFrameWndEx::IsMDITabbedGroup`.

- Kullanıcı bir sekmeye tıkladığında veya başka bir MDI sekmeli Grup sürüklediğinde kısayol menüsünü görüntülemek için geçersiz kılma `CMDIFrameWndEx::OnShowMDITabContextMenu` içinde `CMDIFrameWndEx`-türetilmiş sınıf. Bu yöntemi uygulaması değil, uygulama kısayolunu görüntülenmez.

- MDI sekmeli gruplarının düzenini uygulamayı kaydetmek için çağrı `CMDIFrameWndEx::SaveMDIState`. Grup profili önceden kaydedilmiş bir MDI yüklemek için sekmeli, çağrı `CMDIFrameWndEx::LoadMDIState`. Ayrıca yüklemek veya bir MDI uygulamasında açılmış belgelerin listesini kaydetmek için bu yöntemleri çağırabilirsiniz. Kaydetme ve yükleme MDI durumu hakkında daha fazla bilgi için bkz. [CMDIFrameWndEx::LoadMDIState](../mfc/reference/cmdiframewndex-class.md#loadmdistate).

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)<br/>
[CMDIFrameWndEx Sınıfı](../mfc/reference/cmdiframewndex-class.md)<br/>
[CMDIChildWndEx Sınıfı](../mfc/reference/cmdichildwndex-class.md)<br/>
[CMDITabInfo Sınıfı](../mfc/reference/cmditabinfo-class.md)
