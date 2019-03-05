---
title: CDocument'ten Belge Sınıfı Türetme
ms.date: 11/04/2016
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
ms.openlocfilehash: 5998d5707eb741be0e8ac270f6ac5ce77a9ff8d8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272067"
---
# <a name="deriving-a-document-class-from-cdocument"></a>CDocument'ten Belge Sınıfı Türetme

Belgeler, içerir ve uygulamanızın verilerini yönetin. MFC Uygulama Sihirbazı tarafından sağlanan belge sınıfını kullanmak için aşağıdakileri yapmanız gerekir:

- Öğesinden bir sınıf türetin `CDocument` her tür belgeyi için.

- Her belgenin verilerini depolamak için üye değişkenleri ekleyin.

- Geçersiz kılma `CDocument`'s `Serialize` belge sınıfınızdaki üye işlevi. `Serialize` Yazar ve belge verilerini ve diskten okur.

## <a name="other-document-functions-often-overridden"></a>Sık sık geçersiz kılınan diğer belge işlevleri

Diğer geçersiz kılmak isteyebilirsiniz `CDocument` üye işlevleri. Özellikle, genellikle geçersiz kılmak ihtiyacınız olacak [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) ve [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) belgenin veri üyeleri başlatılamadı ve [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) yok etmek için dinamik olarak ayrılan verileri. Geçersiz kılınabilir üyeleri hakkında daha fazla bilgi için bkz. [CDocument](../mfc/reference/cdocument-class.md) içinde *MFC başvurusu*.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri Kullanma](../mfc/using-documents.md)
