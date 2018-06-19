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
ms.openlocfilehash: e46d130f535076c2591101ab57423db1130ef749
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348055"
---
# <a name="initializing-documents-and-views"></a>Belgeleri ve Görünümleri Başlatma
Belge sınıfı her iki yönde desteklemesi gerekir böylece belgeleri iki farklı şekilde oluşturulur. İlk olarak, kullanıcı yeni, boş bir belge dosya yeni komutla oluşturabilirsiniz. Bu durumda geçersiz kılma belgede başlatma [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) sınıfının üye işlevini [CDocument](../mfc/reference/cdocument-class.md). İkinci olarak, içeriği bir dosyadan okunan yeni bir belge oluşturmak için kullanıcı Aç komutu Dosya menüsünde kullanabilirsiniz. Bu durumda geçersiz kılma belgede başlatma [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) sınıfının üye işlevini **CDocument**. Her iki başlatmada aynıysa iki geçersiz kılmaları, ortak bir üye işlevi çağırabilir veya `OnOpenDocument` çağırabilirsiniz `OnNewDocument` temiz bir belge başlatmak ve açma işlemi tamamlamak için.  
  
 Kendi belgeleri oluşturulduktan sonra görünümlerin oluşturulur. Belge çerçeve penceresi ve görünüm oluşturma framework tamamlandıktan sonra bir görünüm başlatmak için en iyi saattir. Geçersiz kılarak görünümünüzü başlatabilir [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) üye işlevini [CView](../mfc/reference/cview-class.md). Yeniden başlatın veya hiçbir şey ayarlamak gerekiyorsa, belge değişiklikleri her zaman, geçersiz kılabilirsiniz [in](../mfc/reference/cview-class.md#onupdate).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri ve Görünümleri Başlatma ve Temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)

