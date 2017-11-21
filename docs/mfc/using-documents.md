---
title: Belgeleri kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6e584804ce2d1828002b2fdb09bb4bc1a7ed773
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-documents"></a>Belgeleri Kullanma
Birlikte, belgeleri ve görünümleri çalışma:  
  
-   İçeren, yönetmek ve görüntülemek, uygulamaya özgü [veri](../mfc/managing-data-with-document-data-variables.md).  
  
-   Oluşan bir arabirim sağlayacağı [belge verisi değişkenleri](../mfc/managing-data-with-document-data-variables.md) verileri işlemek için.  
  
-   Katılan [dosyaları okuma ve yazma](../mfc/serializing-data-to-and-from-files.md).  
  
-   Katılan [yazdırma](../mfc/role-of-the-view-in-printing.md).  
  
-   [Tanıtıcı](../mfc/handling-commands-in-the-document.md) uygulamanızın komutları ve iletileri çoğu.  
  
 Belge verileri yönetme özellikle karmaşıktır. Verilerinizi, normalde, belge sınıfı üye değişkenleri depolar. Görünümü, görüntü verilere erişme ve güncelleştirmek için bu değişkenleri kullanır. Belgenin varsayılan seri hale getirme mekanizmasını okuma ve veri dosyalarını gelen ve giden yazma yönetir. Belgelerini de komutları işleyen (ancak değil Windows iletilerini dışında **WM_COMMAND**).  
  
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

