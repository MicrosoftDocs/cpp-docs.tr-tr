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
ms.openlocfilehash: 6f039b2e81b52c753a1fb065572d4eac53d55ec9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428713"
---
# <a name="using-documents"></a>Belgeleri Kullanma

Bu arada, belgeler ve görünümler çalışma:

- İçeren, yönetmek ve görüntülemek, uygulamaya özgü [veri](../mfc/managing-data-with-document-data-variables.md).

- Oluşan bir arabirim sağlayacağı [belge verisi değişkenleri](../mfc/managing-data-with-document-data-variables.md) verileri işlemek için.

- Katılmak [dosyaları okuma ve yazma](../mfc/serializing-data-to-and-from-files.md).

- Katılmak [yazdırma](../mfc/role-of-the-view-in-printing.md).

- [Tanıtıcı](../mfc/handling-commands-in-the-document.md) uygulamanızın komutları ve iletilerin çoğu.

Belge veri yönetme konusunda özellikle karmaşıktır. Verilerinizi, normalde, belge sınıfı üye değişkenlerinde Store. Görünümü, görüntü verilerine erişmek ve güncelleştirmek için bu değişkenleri kullanır. Belgenin varsayılan seri hale getirme mekanizmasını okuma ve dosyaları gelen ve giden veri yazma yönetir. Belgeler, ayrıca komutları (ancak değil Windows iletileri WM_COMMAND dışında) işleyebilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Cdocument'ten belge sınıfı türetme](../mfc/deriving-a-document-class-from-cdocument.md)

- [Belge verisi değişkenleri ile verileri yönetme](../mfc/managing-data-with-document-data-variables.md)

- [Gelen dosyaları ve verileri seri hale getirme](../mfc/serializing-data-to-and-from-files.md)

- [Seri hale getirme mekanizmasını atlama](../mfc/bypassing-the-serialization-mechanism.md)

- [Belgedeki komutları işleme](../mfc/handling-commands-in-the-document.md)

- [OnNewDocument üye işlevi](../mfc/reference/cdocument-class.md#onnewdocument)

- [DeleteContents üye işlevi](../mfc/reference/cdocument-class.md#deletecontents)

## <a name="see-also"></a>Ayrıca Bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

