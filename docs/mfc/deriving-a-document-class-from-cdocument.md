---
description: 'Daha fazla bilgi edinin: CDocument sınıfından belge sınıfı türetme'
title: CDocument'ten Belge Sınıfı Türetme
ms.date: 11/04/2016
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
ms.openlocfilehash: 9f6dccb5400ba0e62b2f11a3c2d4074cb9bb2f25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327890"
---
# <a name="deriving-a-document-class-from-cdocument"></a>CDocument'ten Belge Sınıfı Türetme

Belgeler, uygulamanızın verilerini içerir ve yönetir. MFC Uygulama Sihirbazı tarafından sağlanan belge sınıfını kullanmak için aşağıdakileri yapmanız gerekir:

- `CDocument`Her belge türü için bir sınıf türetirsiniz.

- Her belgenin verilerini depolamak için üye değişkenleri ekleyin.

- `CDocument` `Serialize` Belge sınıfınızın üye işlevini geçersiz kılın. `Serialize` belgenin verilerini diske ve diske yazar ve okur.

## <a name="other-document-functions-often-overridden"></a>Diğer belge Işlevleri genellikle geçersiz kılındı

Diğer üye işlevlerini de geçersiz kılmak isteyebilirsiniz `CDocument` . Özellikle, dinamik olarak ayrılan verileri yok etmek için belgenin veri üyelerini ve [DeleteContents](reference/cdocument-class.md#deletecontents) 'i başlatmak üzere [OnNewDocument](reference/cdocument-class.md#onnewdocument) ve [OnOpenDocument](reference/cdocument-class.md#onopendocument) 'yi geçersiz kılmanız gerekir. Geçersiz kılınabilir Üyeler hakkında daha fazla bilgi için *MFC başvurusu* Içindeki sınıf [CDocument](reference/cdocument-class.md) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri kullanma](using-documents.md)
