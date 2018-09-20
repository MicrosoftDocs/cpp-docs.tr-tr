---
title: Belge-görünüm mimarisinin avantajları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], advantages
- document/view architecture [MFC], advantages of
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 213fc108b11d6056df6696f92658e74a736c4a16
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392846"
---
# <a name="advantages-of-the-documentview-architecture"></a>Belge/Görünüm Mimarisinin Avantajları

MFC belge/görünüm mimarisi kullanarak en önemli avantajı mimarisi birden çok görünüm aynı belgede, özellikle de desteklemesidir. (Birden çok görünüm gerekmez ve belge/görünüm küçük yükü uygulamanızda aşırı ise, mimari önleyebilirsiniz. [Belge/görünüm mimarisinin alternatifleri](../mfc/alternatives-to-the-document-view-architecture.md).)

Uygulamanızı elektronik biçimde ya da grafik biçimde sayısal veri görüntüleme olanağı varsayalım. Bir kullanıcı aynı anda hem ham verileri, elektronik tablo form ve verilerden sonuçları bir grafik görmek isteyebilirsiniz. Bu ayrı görünümleri, ayrı bir çerçeve pencereleri veya tek bir pencere Bölümlendirici bölmelerini görüntüler. Artık kullanıcı görmek ve elektronik tablo verileri düzenleyebilir varsayalım değişiklikleri anında grafiğe yansıtılır.

MFC içinde elektronik tablo ve grafik görünümünde CView türetilen farklı sınıflara temel. Her iki görünümde bir tek belge nesnesi ile ilişkilendirilmiş olabilir. Belge verileri depoları (veya belki de bir veritabanından alır). Her iki görünümde belgeye erişmek ve ondan alma verileri görüntüleyin.

Ne zaman bir kullanıcı güncelleştirmeleri nesne çağrıları görüntülemek görünümlerden birine `CDocument::UpdateAllViews`. Bu işlev tüm belgenin görünümlerinin bildirir ve her görünüm kendisi belgeyi en son verileri güncelleştirir. Tek çağrısı `UpdateAllViews` farklı görünümleri eşitler.

Bu senaryo, özellikle veri görünümleri depolanırsa görünümünden zor kod olmadan veri ayrımı olacaktır. Belge/görünüm ile kolaydır. Framework koordinasyon işin çoğunu sizin için halleder.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge/görünüm için alternatifleri](../mfc/alternatives-to-the-document-view-architecture.md)

- [CDocument](../mfc/reference/cdocument-class.md)

- [CView](../mfc/reference/cview-class.md)

- [CDocument::UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews)

- [CView::GetDocument](../mfc/reference/cview-class.md#getdocument)

## <a name="see-also"></a>Ayrıca Bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

