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
ms.openlocfilehash: b45dadbc062bbba61cdcb4c883f91943b1b18ba8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429831"
---
# <a name="deriving-a-document-class-from-cdocument"></a>CDocument'ten Belge Sınıfı Türetme

Belgeler, içerir ve uygulamanızın verilerini yönetin. MFC Uygulama Sihirbazı tarafından sağlanan belge sınıfını kullanmak için aşağıdakileri yapmanız gerekir:

- Öğesinden bir sınıf türetin `CDocument` her tür belgeyi için.

- Her belgenin verilerini depolamak için üye değişkenleri ekleyin.

- Geçersiz kılma `CDocument`'s `Serialize` belge sınıfınızdaki üye işlevi. `Serialize` Yazar ve belge verilerini ve diskten okur.

## <a name="other-document-functions-often-overridden"></a>Sık sık geçersiz kılınan diğer belge işlevleri

Diğer geçersiz kılmak isteyebilirsiniz `CDocument` üye işlevleri. Özellikle, genellikle geçersiz kılmak ihtiyacınız olacak [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) ve [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) belgenin veri üyeleri başlatılamadı ve [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) yok etmek için dinamik olarak ayrılan verileri. Geçersiz kılınabilir üyeleri hakkında daha fazla bilgi için bkz. [CDocument](../mfc/reference/cdocument-class.md) içinde *MFC başvurusu*.

## <a name="see-also"></a>Ayrıca Bkz.

[Belgeleri Kullanma](../mfc/using-documents.md)

