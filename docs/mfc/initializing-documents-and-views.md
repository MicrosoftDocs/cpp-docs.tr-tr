---
title: Belgeleri ve görünümleri başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d6a6f989b8c6b19c78cf9ad508d18e9592bb9305
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417403"
---
# <a name="initializing-documents-and-views"></a>Belgeleri ve Görünümleri Başlatma

Her iki yönde belge sınıfınıza desteklemelidir şekilde iki farklı yolla belge oluşturulur. İlk olarak, kullanıcı yeni, boş bir belge ile dosya yeni komutunun oluşturabilirsiniz. Bu durumda geçersiz kılma belgede başlatmak [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) sınıfının üye işlevinde [CDocument](../mfc/reference/cdocument-class.md). İkinci olarak, içerikleri bir dosyadan okunan yeni bir belge oluşturmak için kullanıcı Aç komutunu Dosya menüsünü kullanabilirsiniz. Bu durumda geçersiz kılma belgede başlatmak [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) sınıfının üye işlevinde `CDocument`. Her iki başlatmalar aynıysa iki geçersiz kılmaları, bir ortak üye işlevi çağırabilir veya `OnOpenDocument` çağırabilirsiniz `OnNewDocument` temiz bir belgeyi başlatın ve ardından açma işlemi tamamlamak için.

Görünüm belgelerini oluşturulduktan sonra oluşturulur. Framework belge çerçeve penceresi ve görünüm oluşturma tamamlandıktan sonra bir görünüm başlatmak için en iyi saattir. Geçersiz kılarak görünümünüzü başlatabilirsiniz [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) üye işlevinin [CView](../mfc/reference/cview-class.md). Yeniden başlatın veya hiçbir şey ayarlamak istiyorsanız, belge değişiklikleri her zaman, geçersiz kılabilirsiniz [OnUpdate](../mfc/reference/cview-class.md#onupdate).

## <a name="see-also"></a>Ayrıca Bkz.

[Belgeleri ve Görünümleri Başlatma ve Temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)

