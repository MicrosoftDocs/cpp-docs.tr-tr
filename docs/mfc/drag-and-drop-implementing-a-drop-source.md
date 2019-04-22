---
title: 'Sürükle ve bırak: Bir bırakma kaynağı uygulama'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
ms.openlocfilehash: 2aa593fa953f7a9874036d48124ae7b92d88e0a6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768646"
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>Sürükle ve bırak: Bir bırakma kaynağı uygulama

Bu makalede, bir Sürükle ve bırak işlemi verilerini sağlamak için uygulamanızı açıklanmaktadır.

Bir bırakma kaynağı uygulaması oldukça basittir. İlk adım, hangi olayların bir sürükleme işlemi başlamadan belirlemektir. Kullanıcı arabirimi yönergelerine tanımlayan bir sürükleme işlemi başına veri seçimi önerilen ve **WM_LBUTTONDOWN** içinde seçili veri noktasına oluşan olay. MFC OLE örnekleri [OCLIENT](../overview/visual-cpp-samples.md) ve [HIERSVR](../overview/visual-cpp-samples.md) aşağıdaki yönergeleri izleyin.

Uygulamanızı bir kapsayıcı, seçilen veri bağlantılı veya katıştırılmış nesne türü ise `COleClientItem`, arama, `DoDragDrop` üye işlevi. Aksi takdirde, oluşturun bir `COleDataSource` nesne, seçimi başlatın ve veri kaynağı nesnesinin çağrı `DoDragDrop` üye işlevi. Uygulamanız bir sunucu ise kullanın `COleServerItem::DoDragDrop`. Standart sürükle-bırak davranışı özelleştirme hakkında daha fazla bilgi için bkz [sürükle ve bırak: Özelleştirme](../mfc/drag-and-drop-customizing.md).

Varsa `DoDragDrop` döndürür **DROPEFFECT_MOVE**, kaynak verileri kaynak belgedeki hemen silin. Diğer dönüş değeri gelen `DoDragDrop` bir bırakma kaynağı üzerinde hiçbir etkisi olmaz.

Daha fazla bilgi için bkz.:

- [Bir bırakma hedefi uygulama](../mfc/drag-and-drop-implementing-a-drop-target.md)

- [Özelleştirme sürükle ve bırak](../mfc/drag-and-drop-customizing.md)

- [Oluşturma ve OLE veri nesneleri ve veri kaynakları yok etme](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [OLE veri nesneleri ve veri kaynakları düzenleme](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sürükleme ve Bırakma (OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDataSource::DoDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop)<br/>
[COleClientItem::DoDragDrop](../mfc/reference/coleclientitem-class.md#dodragdrop)<br/>
[CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)
