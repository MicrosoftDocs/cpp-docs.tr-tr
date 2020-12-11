---
description: 'Hakkında daha fazla bilgi edinin: belgeleri kullanma'
title: Belgeleri Kullanma
ms.date: 11/04/2016
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
ms.openlocfilehash: 486604733808fb027d6dd0fbf81bb670c85313f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154506"
---
# <a name="using-documents"></a>Belgeleri Kullanma

Birlikte çalışan, belgeler ve görünümler:

- Uygulamaya özgü [verilerinizi](../mfc/managing-data-with-document-data-variables.md)içerir, yönetin ve görüntüleyin.

- Verileri işlemek için [belge veri değişkenlerinden](../mfc/managing-data-with-document-data-variables.md) oluşan bir arabirim sağlayın.

- [Dosyaları yazmaya ve okumaya](../mfc/serializing-data-to-and-from-files.md)katılın.

- [Baskıya](../mfc/role-of-the-view-in-printing.md)katılın.

- Uygulamanızın komutlarının ve iletilerinin çoğunu [işleyin](../mfc/handling-commands-in-the-document.md) .

Belge özellikle verileri yönetmeye dahil edilir. Verilerinizi normalde belge sınıfı üye değişkenlerinde depolayın. Görünüm, bu değişkenleri görüntüleme ve güncelleştirme için verilere erişmek üzere kullanır. Belgenin varsayılan serileştirme mekanizması, verileri okuma ve dosyalara yazma işlemlerini yönetir. Belgeler ayrıca komutları işleyebilir (ancak, WM_COMMAND dışındaki Windows iletilerini kullanmaz).

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [CDocument'ten belge sınıfı türetme](../mfc/deriving-a-document-class-from-cdocument.md)

- [Belge verisi değişkenleri ile verileri yönetme](../mfc/managing-data-with-document-data-variables.md)

- [Dosyalarda verileri seri hale getirme](../mfc/serializing-data-to-and-from-files.md)

- [Seri hale getirme mekanizmasını atlama](../mfc/bypassing-the-serialization-mechanism.md)

- [Belgedeki komutları işleme](../mfc/handling-commands-in-the-document.md)

- [OnNewDocument üye işlevi](../mfc/reference/cdocument-class.md#onnewdocument)

- [DeleteContents üye işlevi](../mfc/reference/cdocument-class.md#deletecontents)

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)
