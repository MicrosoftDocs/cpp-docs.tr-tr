---
title: Rubber-Banding ve İzleyiciler
ms.date: 11/04/2016
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
ms.openlocfilehash: f15256f99a744273b3487925bf273ad563c32aff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450810"
---
# <a name="rubber-banding-and-trackers"></a>Rubber-Banding ve İzleyiciler

Başka bir özellik izleyicileri ile sağlanan boyutlandırma dikdörtgen etrafında seçilecek öğeleri sürükleyerek birden çok OLE öğelerini seçmek bir kullanıcı izin veren "Lastik bant" seçimdir. Kullanıcının sol fare düğmesini bıraktığında, kullanıcı tarafından seçilen bölge içindeki öğeleri seçili olduğundan ve kullanıcı tarafından yönetilebilir. Örneğin, kullanıcı seçimi başka bir kapsayıcı uygulamasına sürükleyin.

Bu özelliği uygulamak, uygulamanızın WM_LBUTTONDOWN işleyici işlevi içinde ek kod gerektirir.

Aşağıdaki kod örneği, Lastik bant seçimi ve ek özellikler uygular.

[!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]

İzleyici ters çevrilebilir yönünü rubber-banding sırasında izin vermek istiyorsanız, çağırmalıdır [CRectTracker::TrackRubberBand](../mfc/reference/crecttracker-class.md#trackrubberband) kümesine üçüncü parametresi **TRUE**. Ters yönlendirme izin vererek bazen neden olacağını unutmayın [CRectTracker::m_rect](../mfc/reference/crecttracker-class.md#m_rect) ters haline için. Bu, bir çağrı tarafından düzeltilebilir [CRect::NormalizeRect](../atl-mfc-shared/reference/crect-class.md#normalizerect).

Daha fazla bilgi için [kapsayıcı istemci öğeleri](../mfc/containers-client-items.md) ve [özelleştirme sürükle ve bırak](../mfc/drag-and-drop-customizing.md).

## <a name="see-also"></a>Ayrıca Bkz.

[İzleyiciler: OLE Uygulamanızda İzleyicileri Uygulama](../mfc/trackers-implementing-trackers-in-your-ole-application.md)<br/>
[CRectTracker Sınıfı](../mfc/reference/crecttracker-class.md)
