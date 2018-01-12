---
title: "Penceresiz etkinleştirme sağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- windowless activation of MFC ActiveX controls
- activation [MFC], MFC ActiveX controls
- MFC ActiveX controls [MFC], activate options
- activation [MFC], windowless
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eb33f1dd9f8be8cb06cdfcc2aeecb653c2762410
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="providing-windowless-activation"></a>Penceresiz Etkinleştirme Sağlama
Pencere oluşturma kod (diğer bir deyişle, gerçekleşen her şeyi çağırdığınızda **CreateWindow'u**) yürütmek maliyetli olabilir. Tutan bir denetim bir pencere iletileri yönetmek penceresinin ekran vardır. Penceresiz denetimleri, bu nedenle windows denetimleriyle daha hızlı bir şekilde bağlıdır.  
  
 Başka bir avantaj penceresiz denetimlerinin pencereli denetimleri penceresiz denetimleri saydam boyama ve dikdörtgen olmayan ekran bölgeleri, desteklemesidir. Bir ortak saydam denetim saydam arka plan metin denetimiyle örnektir. Denetimleri boyar metin ancak değil arka planda ne olursa olsun altındaki metin aracılığıyla gösterecek şekilde. Yeni formlar genellikle okları gibi dikdörtgen olmayan denetimleri kullanın ve düğmeleri yuvarlamak yapın.  
  
 Genellikle, bir denetim bir pencere kendi gerekmez ve, kapsayıcı penceresiz nesneleri desteklemek üzere yazılmış koşuluyla, bunun yerine, kapsayıcısının penceresi hizmetlerini kullanabilirsiniz. Penceresiz denetimleri eski kapsayıcıları ile geriye dönük olarak uyumludur. Penceresiz denetimleri desteklemek üzere yazılmış olmayan eski kapsayıcılarında penceresiz denetimleri bir pencere etkin olduğunda oluşturun.  
  
 Penceresiz denetimleri kendi windows olmadığından (olan bir pencere) kapsayıcı Aksi takdirde denetimin kendi pencere tarafından sağlanmış olan hizmetleri sağlamaktan sorumludur. Örneğin, Denetim klavye odağını sorgu, fare yakalama ya da bir cihaz bağlamı elde etmek gerekirse, bu işlemlerin kapsayıcı tarafından yönetilir. Kapsayıcı onun penceresi uygun penceresiz denetlemek için gönderilen kullanıcı giriş iletileri yönlendiren kullanarak `IOleInPlaceObjectWindowless` arabirimi. (Bkz *ActiveX SDK* bu arabirim açıklaması.) `COleControl` üye işlevlerini çağırma kapsayıcısından bu hizmetleri.  
  
 Penceresiz etkinleştirmesi kullanın, denetimi yapmak için dahil **windowlessActivate** tarafından döndürülen bayraklar kümesi bayrağı [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Örneğin:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-windowless-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/cpp/providing-windowless-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-windowless-activation_3.cpp)]  
  
 Seçerseniz bu bayrak eklemek için kodu otomatik olarak oluşturulan **penceresiz etkinleştirme** seçeneği [denetim ayarlarını](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX Denetim Sihirbazı sayfasında.  
  
 Penceresiz etkinleştirme etkinleştirildiğinde, kapsayıcı denetimin giriş iletilerini temsil edecek `IOleInPlaceObjectWindowless` arabirimi. `COleControl`kullanıcının bu arabirim uygulaması fare ayarlama uygun şekilde düzenler sonra denetiminizin ileti eşlemesi üzerinden ileti gönderir. İleti eşlemesi karşılık gelen girdilere ekleyerek sıradan pencere iletileri gibi iletileri işleyebilir. Bu iletiler, işleyicileri kullanmaktan kaçının `m_hWnd` üye değişkeni (veya bunu kullanan herhangi bir üye işlevini) denetlemeden ilk değeri olmayan **NULL**.  
  
 `COleControl`Fare yakalama, klavye odağı, kaydırma ve de dahil olmak üzere diğer pencere Hizmetleri gibi uygun kapsayıcısından çağırma üye işlevleri sağlar:  
  
-   [Tıklatma](../mfc/reference/colecontrol-class.md#getfocus), [SetFocus](../mfc/reference/colecontrol-class.md#setfocus)  
  
-   [GetCapture](../mfc/reference/colecontrol-class.md#getcapture), [SetCapture](../mfc/reference/colecontrol-class.md#setcapture), [ReleaseCapture](../mfc/reference/colecontrol-class.md#releasecapture)  
  
-   [GetDC](../mfc/reference/colecontrol-class.md#getdc), [ReleaseDC](../mfc/reference/colecontrol-class.md#releasedc)  
  
-   [InvalidateRgn](../mfc/reference/colecontrol-class.md#invalidatergn)  
  
-   [ScrollWindow](../mfc/reference/colecontrol-class.md#scrollwindow)  
  
-   [GetClientRect](../mfc/reference/colecontrol-class.md#getclientrect)  
  
 Her zaman kullanmalısınız penceresiz denetimlerinde `COleControl` karşılık gelen yerine üye işlevleri `CWnd` üye işlevleri veya kendi ilgili Win32 API işlevleri.  
  
 OLE sürükle ve bırak işlemi hedefi için penceresiz bir denetim isteyebilirsiniz. Normalde, bu denetimin penceresi bir bırakma hedefi olarak kaydedilmesi gerekir. Denetim kendi pencere olduğundan, kapsayıcı bir bırakma hedefi olarak kendi pencere kullanır. Denetim bir uygulamasını sağlar `IDropTarget` için kapsayıcı temsil çağrıları uygun zamanda arabirimi. Bu arabirim kapsayıcısı kullanıma sunmak için geçersiz kılma [COleControl::GetWindowlessDropTarget](../mfc/reference/colecontrol-class.md#getwindowlessdroptarget). Örneğin:  
  
 [!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/cpp/providing-windowless-activation_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)

