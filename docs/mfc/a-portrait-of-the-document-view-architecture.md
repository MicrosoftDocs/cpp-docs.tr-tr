---
title: Belge-görünüm mimarisinin dikey
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
ms.openlocfilehash: f0e71c42004b5409eeb6f5e2ddabd33296cf5f49
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623443"
---
# <a name="a-portrait-of-the-documentview-architecture"></a>Belge/Görünüm Mimarisinin Bir Özeti

Belgeler ve görünümler tipik bir MFC uygulamasında eşleştirilmelidir. Veriler belgede depolanır, ancak görünümün verilere ayrıcalıklı erişimi vardır. Belgedeki belgenin ayrımı, verilerin depolama ve bakımını, görünümünden ayırır.

## <a name="gaining-access-to-document-data-from-the-view"></a>Görünümden belge verilerine erişim elde etme

Görünüm, belgenin verilerine, belgeye yönelik bir işaretçi döndüren [GetDocument](reference/cview-class.md#getdocument) işleviyle veya View sınıfını belge sınıfının C++ ' ı yaparak sağlar `friend` . Daha sonra Görünüm, verileri çizmeye veya başka bir şekilde çalışmaya hazırsa verileri almak için veri erişimini kullanır.

Örneğin, görünümün [OnDraw](reference/cview-class.md#ondraw) üye işlevinde, görünümü `GetDocument` bir belge işaretçisi almak için kullanır. Sonra bu işaretçiyi belgedeki bir veri üyesine erişmek için kullanır `CString` . Görünüm, dizeyi `TextOut` işleve geçirir. Bu örneğe ilişkin kodu görmek için bkz. [bir görünümde çizim](drawing-in-a-view.md).

## <a name="user-input-to-the-view"></a>Görünüme Kullanıcı girişi

Görünüm aynı zamanda bir fare tıklamasını, verilerin seçimi veya düzenlenmesiyle de yorumlayabilir. Benzer şekilde, tuş vuruşlarını veri girişi veya düzenlemesi olarak yorumlayabilir. Kullanıcının, metni yöneten bir görünümde dize oluşturduğunu varsayalım. Görünüm belgeye bir işaretçi edinir ve yeni verileri belgeye geçirmek için işaretçiyi kullanır, bu da verileri bazı veri yapısına depolar.

## <a name="updating-multiple-views-of-the-same-document"></a>Aynı belgenin birden çok görünümünü güncelleştirme

Aynı belgenin birden çok görünümüne sahip bir uygulamada — Örneğin, bir metin düzenleyicisinde ayırıcı pencere gibi — görünüm ilk olarak belgeye yeni verileri geçirir. Ardından belgenin [UpdateAllViews](reference/cdocument-class.md#updateallviews) üye işlevini çağırır, bu da belgenin tüm görünümlerinin güncelleştirilmesini ve yeni verileri yansıtmasını söyler. Bu, görünümleri eşitler.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge/görünüm mimarisinin avantajları](advantages-of-the-document-view-architecture.md)

- [Belge/görünüm mimarisi alternatifleri](alternatives-to-the-document-view-architecture.md)

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](document-view-architecture.md)
