---
title: Cdocument'ten belge sınıfı türetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a81f3c3a36f049e3f47401efa31b36677b3b9ba6
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931755"
---
# <a name="deriving-a-document-class-from-cdocument"></a>CDocument'ten Belge Sınıfı Türetme
Belge içerir ve uygulamanızın veri yönetin. MFC Uygulama Sihirbazı tarafından sağlanan belge sınıfını kullanmak için aşağıdakileri yapmanız gerekir:  
  
-   Öğesinden bir sınıf türetin `CDocument` her belge türü için.  
  
-   Her bir belgenin verileri depolamak için üye değişkenleri ekleyin.  
  
-   Geçersiz kılma `CDocument`'s `Serialize` belge sınıfınızda üye işlevi. `Serialize` Yazar ve disk belgenin veri okur.  
  
## <a name="other-document-functions-often-overridden"></a>Sık sık geçersiz kılınan diğer belge işlevleri  
 Diğer geçersiz kılma isteyebilirsiniz `CDocument` üye işlevleri. Özellikle, sık sık geçersiz kılma gerekir [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) ve [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) belgenin veri üyeleri başlatılamadı ve [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) yok etme dinamik olarak ayrılan veriler. Geçersiz kılınabilir üyeleri hakkında daha fazla bilgi için bkz [CDocument](../mfc/reference/cdocument-class.md) içinde *MFC başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri Kullanma](../mfc/using-documents.md)

