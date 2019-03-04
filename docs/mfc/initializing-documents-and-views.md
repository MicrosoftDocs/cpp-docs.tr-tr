---
title: Belgeleri ve Görünümleri Başlatma
ms.date: 11/04/2016
helpviewer_keywords:
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
ms.openlocfilehash: 0cf9faecbb7e0d74c2199a1a829aa68241e1c019
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264098"
---
# <a name="initializing-documents-and-views"></a>Belgeleri ve Görünümleri Başlatma

Her iki yönde belge sınıfınıza desteklemelidir şekilde iki farklı yolla belge oluşturulur. İlk olarak, kullanıcı yeni, boş bir belge ile dosya yeni komutunun oluşturabilirsiniz. Bu durumda geçersiz kılma belgede başlatmak [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) sınıfının üye işlevinde [CDocument](../mfc/reference/cdocument-class.md). İkinci olarak, içerikleri bir dosyadan okunan yeni bir belge oluşturmak için kullanıcı Aç komutunu Dosya menüsünü kullanabilirsiniz. Bu durumda geçersiz kılma belgede başlatmak [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) sınıfının üye işlevinde `CDocument`. Her iki başlatmalar aynıysa iki geçersiz kılmaları, bir ortak üye işlevi çağırabilir veya `OnOpenDocument` çağırabilirsiniz `OnNewDocument` temiz bir belgeyi başlatın ve ardından açma işlemi tamamlamak için.

Görünüm belgelerini oluşturulduktan sonra oluşturulur. Framework belge çerçeve penceresi ve görünüm oluşturma tamamlandıktan sonra bir görünüm başlatmak için en iyi saattir. Geçersiz kılarak görünümünüzü başlatabilirsiniz [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) üye işlevinin [CView](../mfc/reference/cview-class.md). Yeniden başlatın veya hiçbir şey ayarlamak istiyorsanız, belge değişiklikleri her zaman, geçersiz kılabilirsiniz [OnUpdate](../mfc/reference/cview-class.md#onupdate).

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri ve Görünümleri Başlatma ve Temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)
