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
ms.openlocfilehash: 698957d4e307ad1f099d5aef7de131c538ee4871
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="deriving-a-document-class-from-cdocument"></a>CDocument'ten Belge Sınıfı Türetme
Belge içerir ve uygulamanızın veri yönetin. MFC Uygulama Sihirbazı tarafından sağlanan belge sınıfını kullanmak için aşağıdakileri yapmanız gerekir:  
  
-   Öğesinden bir sınıf türetin **CDocument** her belge türü için.  
  
-   Her bir belgenin verileri depolamak için üye değişkenleri ekleyin.  
  
-   Geçersiz kılma **CDocument**'s `Serialize` belge sınıfınızda üye işlevi. `Serialize` Yazar ve disk belgenin veri okur.  
  
## <a name="other-document-functions-often-overridden"></a>Sık sık geçersiz kılınan diğer belge işlevleri  
 Diğer geçersiz kılma isteyebilirsiniz **CDocument** üye işlevleri. Özellikle, sık sık geçersiz kılma gerekir [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) ve [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) belgenin veri üyeleri başlatılamadı ve [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) yok etme dinamik olarak ayrılan veriler. Geçersiz kılınabilir üyeleri hakkında daha fazla bilgi için bkz [CDocument](../mfc/reference/cdocument-class.md) içinde *MFC başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri Kullanma](../mfc/using-documents.md)

