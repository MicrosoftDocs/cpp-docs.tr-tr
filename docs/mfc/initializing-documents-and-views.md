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
ms.openlocfilehash: 0e970d6e8a166283f82575b309cf023f48899403
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626349"
---
# <a name="initializing-documents-and-views"></a>Belgeleri ve Görünümleri Başlatma

Belgeler iki farklı şekilde oluşturulur, bu nedenle belge sınıfınız her iki şekilde de destek sağlamalıdır. İlk olarak, Kullanıcı File New komutuyla yeni, boş bir belge oluşturabilir. Bu durumda, [CDocument](reference/cdocument-class.md)sınıfının [OnNewDocument](reference/cdocument-class.md#onnewdocument) üye işlevinin geçersiz kılmada belgeyi başlatın. İkincisi, Kullanıcı, içeriği dosyadan okunan yeni bir belge oluşturmak için Dosya menüsündeki Aç komutunu kullanabilir. Bu durumda, sınıfının [OnOpenDocument](reference/cdocument-class.md#onopendocument) üye işlevini geçersiz kılmanızda belgeyi başlatın `CDocument` . Her iki başlatma da aynıysa, her iki geçersiz kılmalardan ortak bir üye işlevi çağırabilir veya `OnOpenDocument` `OnNewDocument` temiz bir belge başlatabilir ve sonra Aç işlemini tamamlayabilirler.

Görünümler, belgeleri oluşturulduktan sonra oluşturulur. Bir görünümü başlatmanın en iyi zamanı Framework 'ün belge, çerçeve penceresi ve görünüm oluşturmayı tamamladıktan sonra olur. [CView](reference/cview-class.md)'ın [OnInitialUpdate](reference/cview-class.md#oninitialupdate) üye işlevini geçersiz kılarak görünümünüzü başlatabilirsiniz. Belge her değiştiğinde yeniden başlatmanız veya ayarlamanız gerekiyorsa [OnUpdate](reference/cview-class.md#onupdate)'i geçersiz kılabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri ve görünümleri başlatma ve Temizleme](initializing-and-cleaning-up-documents-and-views.md)
