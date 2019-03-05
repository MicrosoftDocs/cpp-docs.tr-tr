---
title: Belge-görünüm mimarisinin bir özeti
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], views
- multiple views [MFC], updating from document
- document/view architecture [MFC]
- views [MFC], and user input
- documents [MFC], accessing data from view
- views [MFC], updating
- input [MFC], view class
- documents [MFC], multiple views
- document/view architecture [MFC], accessing data from view
- document/view architecture [MFC], about document/view architecture
- views [MFC], accessing document data from
ms.assetid: 4e7f65dc-b166-45d8-bcd5-9bb0d399b946
ms.openlocfilehash: 51f963acf5aacdfe4050a076d3bb0e651a92d021
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298873"
---
# <a name="a-portrait-of-the-documentview-architecture"></a>Belge/Görünüm Mimarisinin Bir Özeti

Belgeler ve görünümler tipik bir MFC uygulamasında eşleştirilmelidir. Belge içinde depolanan veri ancak görünüm ayrıcalıklı erişimi verilere. Belge ayrımı görünümünden veri Bakım ve depolama, ekrandan ayırır.

## <a name="gaining-access-to-document-data-from-the-view"></a>Belge görünümünden verilerine erişim elde etme

Görünüm, belgenin verilerini ile erişir [GetDocument](../mfc/reference/cview-class.md#getdocument) işlevi, belgeye veya bir C++ sınıf görünümü yaparak bir işaretçi döndürür `friend` belge sınıfı. Görünümü, veri erişimini ardından çizin veya aksi halde işlemek hazır olduğunda verileri almak için kullanır.

Örneğin, Görünüm'den [OnDraw](../mfc/reference/cview-class.md#ondraw) görünümü üye işlevini kullanır `GetDocument` belge işaretçisi elde edilir. Sonra işaretçiyle erişmek için kullandığı bir `CString` belgedeki veri üyesi. Görünüm dizesine geçirir `TextOut` işlevi. Örnek kodu görmek için bkz: [bir görünümde çizim yapma](../mfc/drawing-in-a-view.md).

## <a name="user-input-to-the-view"></a>Görüntülenecek kullanıcı girişi

Görünüm ayrıca seçim veya veri düzenleme olarak kendi içinde bir fare tıklaması yorumlayabilir. Benzer şekilde, tuş vuruşlarınızı veri girişi veya düzenleme olarak yorumlayabilir. Kullanıcı türleri metin yöneten bir görünümde bir dize varsayalım. Görünüm, belge için bir işaretçi alır ve bazı veri yapıda depolar belgenin yeni verileri geçirmek için işaretçi kullanır.

## <a name="updating-multiple-views-of-the-same-document"></a>Aynı belgede birden çok görünüm güncelleştiriliyor

Uygulamada aynı belgenin birden çok görünüm — bir metin düzenleyicisinde bir ayırıcı penceresi gibi — görünümü belgeye ilk yeni verileri geçirir. Belgenin çağırdığı sonra [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) kendileri yeni verileri yansıtacak şekilde güncelleştirmek için belgedeki tüm görünümleri belirten üye işlevi. Bu görünümler eşitler.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge/görünüm mimarisinin avantajları](../mfc/advantages-of-the-document-view-architecture.md)

- [Belge/görünüm mimarisinin alternatifleri](../mfc/alternatives-to-the-document-view-architecture.md)

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)
