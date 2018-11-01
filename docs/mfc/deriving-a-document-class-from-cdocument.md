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
ms.openlocfilehash: 042ba7adc8d36e57a714e03ec67c1c0f22b4da78
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496128"
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

