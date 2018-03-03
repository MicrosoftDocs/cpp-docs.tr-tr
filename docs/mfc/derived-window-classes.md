---
title: "Türetilen pencere sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- window class hierarchy
- hierarchies, window classes
- classes [MFC], derived
- CWnd class [MFC], classes derived from
- derived classes [MFC], window classes
- window classes [MFC], derived
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4601a04932f467be3b63527f12c46f797d9e11d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="derived-window-classes"></a>Türetilen Pencere Sınıfları
Doğrudan windows oluşturabilirsiniz [CWnd](../mfc/reference/cwnd-class.md), ya da yeni pencere sınıflarından `CWnd`. Özel windows genellikle oluşturma budur. Bununla birlikte, çoğu windows framework programda kullanılan yerine birinden oluşturulan `CWnd`-çerçeve penceresi sınıfları MFC tarafından sağlanan türetilmiş.  
  
## <a name="frame-window-classes"></a>Çerçeve penceresi sınıfları  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Tek bir belgenin ve kendi görünüm çerçeve SDI çerçeve pencereleri için kullanılır. Çerçeve penceresi, hem uygulama için ana çerçeve penceresi hem de geçerli belge çerçeve penceresi gerçekleşir.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Ana çerçeve pencere olarak MDI uygulamaları için kullanılır. Ana çerçeve penceresi tüm MDI belge pencereleri ilişkin bir kapsayıcıdır ve bunlarla menü çubuğunu paylaşır. Bir MDI çerçeve penceresi masaüstünde görünür üst düzey bir penceredir.  
  
 [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md)  
 Bir MDI ana çerçeve penceresinde açılan tek tek belgeler için kullanılır. MDI ana çerçeve penceresi bulunan bir MDI alt çerçeve penceresi tarafından her belge ve kendi görünüm Çerçeveli. MDI alt pencere çok tipik çerçeve penceresi gibi görünüyor, ancak masaüstünde durduğunu yerine bir MDI çerçeve penceresi içinde yer alır. Ancak, MDI alt pencere menü çubuğu kendi eksik ve içerdiği MDI çerçeve penceresi menü çubuğu paylaşması gerekir.  
  
 Daha fazla bilgi için bkz: [çerçeve pencereleri](../mfc/frame-windows.md).  
  
## <a name="other-window-classes-derived-from-cwnd"></a>CWnd türetilen diğer pencere sınıfları  
 Çerçeve pencereleri yanı sıra windows birkaç diğer ana kategoriye türetilmiş `CWnd`:  
  
 *Görünümler*  
 Görünümleri kullanarak oluşturulur `CWnd`-türetilmiş sınıf [CView](../mfc/reference/cview-class.md) (veya türetilmiş sınıflarından biri). Bir görünüm belgeye eklenir ve belge ve kullanıcı arasında bir aracı gibi davranır. Genellikle bir SDI çerçeve penceresi veya bir MDI alt çerçeve penceresi (ya da bir araç ve/veya bir durum çubuğu tarafından kapsanmayan istemci alanını bölümünü) istemci alanını doldurur alt pencere (MDI alt değil) görülmektedir.  
  
 *İletişim Kutuları*  
 İletişim kutuları kullanılarak oluşturulan `CWnd`-türetilmiş sınıf [CDialog](../mfc/reference/cdialog-class.md).  
  
 *Formlar*  
 İletişim kutuları gibi iletişim şablonu kaynaklarına göre form görünümleri sınıflarını kullanarak oluşturulan [Cformview'yu](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), veya [CDaoRecordView](../mfc/reference/cdaorecordview-class.md).  
  
 *Denetimler*  
 Denetimleri düğmeleri, liste kutuları ve birleşik giriş kutuları gibi türetilen diğer sınıfları kullanılarak oluşturulur `CWnd`. Bkz: [denetim konuları](../mfc/controls-mfc.md).  
  
 *Denetim Çubukları*  
 Denetimleri içeren alt öğe pencerelerini. Araç çubukları ve durum çubukları örnekleri içerir. Bkz: [denetim çubukları](../mfc/control-bars.md).  
  
## <a name="window-class-hierarchy"></a>Pencere sınıfı hiyerarşisi  
 Başvurmak [MFC hiyerarşi grafiği](../mfc/hierarchy-chart.md) içinde *MFC başvurusu*. Görünümler içinde açıklanan [belge/görünüm mimarisinin](../mfc/document-view-architecture.md). İletişim kutuları içinde açıklanan [iletişim kutuları](../mfc/dialog-boxes.md).  
  
## <a name="creating-your-own-special-purpose-window-classes"></a>Kendi özel amaçlı pencere sınıfları oluşturma  
 Sınıf kitaplığı tarafından sağlanan pencere sınıfları ek olarak, özel amaçlı alt windows gerekebilir. Bu tür bir pencere oluşturmak için kendi oluşturun [CWnd](../mfc/reference/cwnd-class.md)-türetilmiş sınıf ve alt pencere çerçevesi veya görünümünün yapın. Çerçeve bir belge çerçeve penceresi istemci alanını kapsamını yönetir de hesaba katılmalıdır. İstemci alanını çoğunu bir görünüm, ancak diğer windows tarafından yönetilen, denetimi gibi çubukları veya kendi özel windows paylaşım alanı görünümüyle. Sınıflardaki mekanizmaları ile etkileşim gerekebilir [CView](../mfc/reference/cview-class.md) ve [CControlBar](../mfc/reference/ccontrolbar-class.md) çerçeve pencerenin istemci alanında alt öğe pencerelerini konumlandırma için.  
  
 [Pencereler oluşturma](../mfc/creating-windows.md) pencere nesneleri ve onların yönettiği windows oluşturmayı açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere Nesneleri](../mfc/window-objects.md)

