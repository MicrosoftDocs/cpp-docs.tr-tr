---
title: "MFC'de durum çubuğu uygulaması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COldStatusBar
dev_langs: C++
helpviewer_keywords:
- status bars [MFC], implementing in MFC
- CStatusBarCtrl class [MFC], and MFC status bars
- CStatusBar class [MFC], and CStatusBarCtrl class [MFC]
- CStatusBarCtrl class [MFC], and CStatusBar class [MFC]
- status bars [MFC], backward compatibility
- status bars [MFC], old with COldStatusBar class [MFC]
- COldStatusBar class [MFC]
- status bars [MFC], and CStatusBarCtrl class
- CStatusBar class [MFC], and MFC status bars
- status indicators
- status bars [MFC], Windows 95 implementation
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d81982e23f100fe75d6cc5769cd19359bfaa6f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="status-bar-implementation-in-mfc"></a>MFC'de Durum Çubuğu Uygulaması
A [CStatusBar](../mfc/reference/cstatusbar-class.md) denetim çubuğu metni çıkış bölmeleri oluşan bir satır içeren bir nesnedir. Çıkış bölmeleri, ileti satırları ve durum göstergesi olarak yaygın olarak kullanılır. Örnekler seçili menü komutu kısaca açıklayan menü Yardım iletisi satırları ve Kaydırma kilidi, NUM LOCK ve diğer anahtarlar durumunu göster göstergelerini içerir.  
  
 MFC sürüm 4. 0'dan sonra durum çubukları sınıfı kullanılarak uygulanan [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), bir durum çubuğu ortak denetimi yalıtır. Geriye dönük uyumluluk için MFC eski durum çubuğu uygulaması sınıfında korur **COldStatusBar**. MFC önceki sürümleri için belgelere açıklar **COldStatusBar** altında `CStatusBar`.  
  
 [CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl), üye işlevi yeni MFC 4.0 ile Windows ortak denetimin durum çubuğu özelleştirme ve ek işlevsellik için desteğinden olanak tanır. `CStatusBar`Windows ortak denetimleri işlevselliğini çoğunu size üye işlevleri; çağırdığınızda ancak `GetStatusBarCtrl`, durum çubukları durum çubuğu özelliklerini daha da verebilirsiniz. Çağırdığınızda `GetStatusBarCtrl`, bir başvuru döndürür bir `CStatusBarCtrl` nesnesi. Durum çubuğu denetimi işlemek için bu başvuruyu kullanabilirsiniz.  
  
 Aşağıdaki şekilde birkaç göstergeleri görüntüleyen bir durum çubuğunu gösterir.  
  
 ![Durum çubuğu](../mfc/media/vc37dy1.gif "vc37dy1")  
Durum çubuğu  
  
 Araç çubuğu gibi durum çubuğu nesne kendi üst çerçeve penceresinde katıştırılır ve çerçeve penceresi oluşturulduğunda otomatik olarak oluşturulur. Üst çerçeve bozulduğunda durum çubuğu, tüm denetim çubukları gibi otomatik olarak da yok.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Durum çubuğu bölmesinin metnini güncelleştirme](../mfc/updating-the-text-of-a-status-bar-pane.md)  
  
-   MFC sınıfları [CStatusBar](../mfc/reference/cstatusbar-class.md) ve [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
  
-   [Denetim çubukları](../mfc/control-bars.md)  
  
-   [İletişim kutusu çubukları](../mfc/dialog-bars.md)  
  
-   [Araç çubukları (MFC araç çubuğu uygulaması)](../mfc/mfc-toolbar-implementation.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Durum Çubukları](../mfc/status-bars.md)

