---
title: Rubber-Banding ve izleyiciler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4f36a634e4e5e6d4ee6c2618d0d43313c7c8094
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931742"
---
# <a name="rubber-banding-and-trackers"></a>Rubber-Banding ve İzleyiciler
Başka bir özellik izleyicileri ile sağlanan seçilecek öğeleri etrafında boyutlandırma dikdörtgen sürükleyerek birden çok OLE öğeleri seçmek bir kullanıcının "bant dışı pencere" seçim değildir. Kullanıcı sol fare düğmesini bıraktığında, kullanıcı tarafından seçilen bölge içindeki öğeler seçilir ve kullanıcı tarafından yönetilebilir. Örneğin, kullanıcı seçimi sürükleyin ve bu da başka bir kapsayıcı uygulamasına.  
  
 Bu özellik uygulama bazı ek kod, uygulamanızın WM_LBUTTONDOWN işleyici işlevi gerektirir.  
  
 Aşağıdaki kod örneği, bant dışı pencere seçimi ve ek özellikler uygular.  
  
 [!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]  
  
 İzleyici ters çevrilebilir yönünü rubber-banding sırasında izin vermek istiyorsanız, çağırmalıdır [CRectTracker::TrackRubberBand](../mfc/reference/crecttracker-class.md#trackrubberband) kümesine üçüncü parametre ile **doğru**. Ters çevrilebilir yönlendirmesini izin vererek bazen neden olacak unutmayın [CRectTracker::m_rect](../mfc/reference/crecttracker-class.md#m_rect) ters hale için. Bu bir çağrı tarafından düzeltilebilir [CRect::NormalizeRect](../atl-mfc-shared/reference/crect-class.md#normalizerect).  
  
 Daha fazla bilgi için bkz: [kapsayıcı istemci öğeleri](../mfc/containers-client-items.md) ve [özelleştirme sürükle ve bırak](../mfc/drag-and-drop-customizing.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzleyiciler: OLE uygulamanızda izleyicileri uygulama](../mfc/trackers-implementing-trackers-in-your-ole-application.md)   
 [CRectTracker Sınıfı](../mfc/reference/crecttracker-class.md)
