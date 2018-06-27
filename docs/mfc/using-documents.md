---
title: Belgeleri kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb5e6ad4cfcc1e14d3b6accc1e5adaf4037669a4
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950220"
---
# <a name="using-documents"></a>Belgeleri Kullanma
Birlikte, belgeleri ve görünümleri çalışma:  
  
-   İçeren, yönetmek ve görüntülemek, uygulamaya özgü [veri](../mfc/managing-data-with-document-data-variables.md).  
  
-   Oluşan bir arabirim sağlayacağı [belge verisi değişkenleri](../mfc/managing-data-with-document-data-variables.md) verileri işlemek için.  
  
-   Katılan [dosyaları okuma ve yazma](../mfc/serializing-data-to-and-from-files.md).  
  
-   Katılan [yazdırma](../mfc/role-of-the-view-in-printing.md).  
  
-   [Tanıtıcı](../mfc/handling-commands-in-the-document.md) uygulamanızın komutları ve iletileri çoğu.  
  
 Belge verileri yönetme özellikle karmaşıktır. Verilerinizi, normalde, belge sınıfı üye değişkenleri depolar. Görünümü, görüntü verilere erişme ve güncelleştirmek için bu değişkenleri kullanır. Belgenin varsayılan seri hale getirme mekanizmasını okuma ve veri dosyalarını gelen ve giden yazma yönetir. Belgeleri de komutları (ancak değil Windows iletilerini WM_COMMAND dışında) işleyebilir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Cdocument'ten belge sınıfı türetme](../mfc/deriving-a-document-class-from-cdocument.md)  
  
-   [Belge verisi değişkenleri ile verileri yönetme](../mfc/managing-data-with-document-data-variables.md)  
  
-   [Verileri ve dosyaları gelen seri hale getirme](../mfc/serializing-data-to-and-from-files.md)  
  
-   [Seri hale getirme mekanizmasını atlama](../mfc/bypassing-the-serialization-mechanism.md)  
  
-   [Belgedeki komutları işleme](../mfc/handling-commands-in-the-document.md)  
  
-   [OnNewDocument üye işlevi](../mfc/reference/cdocument-class.md#onnewdocument)  
  
-   [DeleteContents üye işlevi](../mfc/reference/cdocument-class.md#deletecontents)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

