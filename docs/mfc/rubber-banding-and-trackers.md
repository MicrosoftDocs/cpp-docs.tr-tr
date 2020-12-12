---
description: 'Daha fazla bilgi edinin: Rubber-Banding ve Izleyiciler'
title: Rubber-Banding ve İzleyiciler
ms.date: 11/04/2016
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
ms.openlocfilehash: 5d641e7553a2891e0319484558f025c6998f9693
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217841"
---
# <a name="rubber-banding-and-trackers"></a>Rubber-Banding ve İzleyiciler

İzleyiciler ile sağlanan diğer bir özellik, bir kullanıcının seçili olması için bir boyutlandırma dikdörtgeni sürükleyerek birden çok OLE öğesi seçmesini sağlayan "lastik bant" seçiminden bir özelliktir. Kullanıcı sol fare düğmesini bıraktığında, Kullanıcı tarafından seçilen bölge içindeki öğeler seçilir ve Kullanıcı tarafından yönetilebilir. Örneğin, Kullanıcı seçimi başka bir kapsayıcı uygulamasına sürükleyebilir.

Bu özelliğin uygulanması, uygulamanızın WM_LBUTTONDOWN işleyici işlevinde bazı ek kodlar gerektirir.

Aşağıdaki kod örneği, lastik bant seçimini ve ek özellikleri uygular.

[!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]

Lastik bant oluşturma sırasında izleyici 'nin ters yönlendirmesine izin vermek istiyorsanız, üçüncü parametresi **true** olarak ayarlanmış şekilde [CRectTracker:: TrackRubberBand](../mfc/reference/crecttracker-class.md#trackrubberband) ' i çağırmanız gerekir. Ters yönlendirmeye izin vermek bazen [CRectTracker:: m_rect](../mfc/reference/crecttracker-class.md#m_rect) ters çevrilmesine neden olur. Bu, [CRect:: NormalizeRect](../atl-mfc-shared/reference/crect-class.md#normalizerect)çağrısıyla düzeltilebilir.

Daha fazla bilgi için bkz. [kapsayıcı Istemci öğeleri](../mfc/containers-client-items.md) ve [OLE sürükle ve bırak: sürükle ve bırak seçeneğini özelleştirin](../mfc/drag-and-drop-ole.md#customize-drag-and-drop).

## <a name="see-also"></a>Ayrıca bkz.

[İzleyiciler: OLE uygulamanızda Izleyicileri uygulama](../mfc/trackers-implementing-trackers-in-your-ole-application.md)<br/>
[CRectTracker sınıfı](../mfc/reference/crecttracker-class.md)
