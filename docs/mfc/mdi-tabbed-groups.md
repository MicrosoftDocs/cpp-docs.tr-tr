---
title: "MDI sekmeli grupları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- mdi [MFC], tabbed groups
- tabbed grous [MFC]
ms.assetid: 0a464f36-39b7-4e68-8b67-ec175de28377
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3d58c079fc08935a11f65170b804f6a4b2786cbb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mdi-tabbed-groups"></a>MDI Sekmeli Grupları
Bir veya daha fazla sekmeli windows görüntülemek birden çok belge arabirimi (MDI) uygulamaları birden çok belge arabirimi (MDI) sekmeli gruplar özelliği sağlar (ya da kullanıcı grupları olarak bilinen sekmeli windows *sekmeli grupları*) MDI istemci alanında. Sekmeli windows dikey veya yatay olarak hizalanabilir. Bir uygulama birden fazla MDI sekmeli Grup barındırıyorsa, grupları ayırıcılar tarafından ayrılır.  
  
## <a name="features"></a>Özellikler  
 MDI sekmeli grupları özellikleri şunlardır:  
  
-   Bir uygulama sekmeli windows dinamik olarak oluşturabilir.  
  
-   Bir uygulama sekmeli windows yatay veya dikey olarak Hizala.  
  
-   Sekmeli windows grupları ayırıcılar tarafından ayrılır. Kullanıcı sekmeli gruplar Bölümlendirici kullanarak genişletebilir.  
  
-   Kullanıcı grupları arasında tek tek sekmeler sürükleyebilirsiniz.  
  
-   Kullanıcı, yeni gruplar oluşturmak için tek tek sekmeler sürükleyebilirsiniz.  
  
-   Kullanıcı sekmeler taşıyabilir veya bir kısayol menüsünü kullanarak yeni gruplar oluşturabilir.  
  
-   Bir uygulamayı kaydedin ve sekmeli windows düzenini yükleyin.  
  
-   Bir uygulamayı kaydedin ve MDI belgelerin listesini yükleyin.  
  
-   Bir uygulama bireysel sekmeli gruplar erişmek ve bunların parametrelerini değiştirin.  
  
### <a name="using-mdi-tabbed-groups"></a>Kullanarak MDI sekmeli grupları  
 MDI sekmeli grupları ile sık gerçekleştirilen görevleri şunlardır:  
  
-   MDI sekmeli grupları bir ana çerçeve penceresi etkinleştirmek için arama [CMDIFrameWndEx::EnableMDITabbedGroups](../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups). Bu yöntemin ikinci parametre örneğidir `CMDITabInfo` sınıfı. Varsayılan parametreleri kullanın veya çağırmadan önce bunları değiştirmek için `CMDIFrameWndEx::EnableMDITabbedGroups`.  
  
-   Çalışma zamanında bir MDI sekmeli grubunun özelliklerini değiştirmek için oluşturmak veya değiştirmek bir `CMDITabInfo` nesne ve çağrı `CMDIFrameWndEx::EnableMDITabbedGroups` yeniden  
  
-   MDI listesini almak için windows sekmeli, çağrı `CMDIFrameWndEx::GetMDITabGroups`.  
  
-   Etkin bir sekmeli grubunun yanındaki yeni bir MDI sekmeli grubu oluşturmak için arama `CMDIFrameWndEx::MDITabNewGroup`.  
  
-   Giriş odağını sekmeli grubunun önceki veya sonraki penceresine kaydırılacak çağrı `CMDIFrameWndEx::MDITabMoveToNextGroup`.  
  
-   Bir pencere MDI üyesi olup olmadığını belirlemek için grup çağrısı sekmeli `CMDIFrameWndEx::IsMemberOfMDITabGroup`.  
  
-   MDI sekmeler veya MDI sekmeli grupları için bir ana çerçeve penceresi etkinleştirilip etkinleştirilmeyeceğini belirlemek için arama `CMDIFrameWndEx::AreMDITabs`. Yalnızca MDI sekmeli grupları etkinleştirilip etkinleştirilmeyeceğini belirlemek için arama `CMDIFrameWndEx::IsMDITabbedGroup`.  
  
-   Kullanıcı bir sekmesini tıklatır ya da başka bir MDI sekmeli gruba sürüklediği bir kısayol menüsünü görüntülemek için geçersiz kılma `CMDIFrameWndEx::OnShowMDITabContextMenu` içinde `CMDIFrameWndEx`-türetilmiş sınıf. Bu yöntemi uygulaması değil, uygulama kısayol menüsünün görüntülenmez.  
  
-   MDI sekmeli grupları düzenini bir uygulamada kaydetmek için arama `CMDIFrameWndEx::SaveMDIState`. Daha önce kaydedilmiş bir MDI yüklemek için Grup profili sekmeli, çağrı `CMDIFrameWndEx::LoadMDIState`. Ayrıca yüklemek veya bir MDI uygulamada açık belgelerin listesini kaydetmek için bu yöntemleri çağırabilirsiniz. Kaydetme ve MDI durumu yükleme hakkında daha fazla bilgi için bkz: [CMDIFrameWndEx::LoadMDIState](../mfc/reference/cmdiframewndex-class.md#loadmdistate).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)   
 [CMDIFrameWndEx sınıfı](../mfc/reference/cmdiframewndex-class.md)   
 [CMDIChildWndEx sınıfı](../mfc/reference/cmdichildwndex-class.md)   
 [CMDITabInfo sınıfı](../mfc/reference/cmditabinfo-class.md)
