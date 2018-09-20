---
title: MFC'deki dosyalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serialization [MFC], MFC files
- I/O [MFC], MFC classes
- files [MFC], MFC
- files [MFC], serialization
- binary access, binary file operations in MFC
- file I/O classes [MFC]
- I/O [MFC]
- persistence [MFC]
- MFC, file operations
- files [MFC], manipulating
- binary access [MFC]
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bfc36a6b1610df07201833ed13a1c6ebd0ae6f7b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444499"
---
# <a name="files-in-mfc"></a>MFC'deki Dosyalar

Microsoft Foundation sınıf kitaplığı (MFC'de), sınıf [CFile](../mfc/reference/cfile-class.md) normal dosya g/ç işlemleri gerçekleştirir. Bu makaleler ailesi, açın ve dosyaları kapatın yanı sıra okuma ve bu dosyalara veri yazma açıklanmaktadır. Ayrıca, dosya durumu işlemleri açıklanır. Okumanın ve veri dosyaları yazılıyor alternatif bir yolu olarak MFC nesne tabanlı serileştirme özelliklerini kullanmayı açıklaması için bkz [serileştirme](../mfc/serialization-in-mfc.md).

> [!NOTE]
>  MFC kullandığınızda `CDocument` nesnelerini framework serileştirme işin çoğunu sizin için yapar. Özellikle, framework oluşturduğu ve kullandığı `CFile` nesne. Yalnızca geçersiz kılmada kod yazmak zorunda `Serialize` sınıfının üye işlevinde `CDocument`.

`CFile` Sınıfı, genel amaçlı ikili dosya işlemleri için bir arabirim sağlar. `CStdioFile` Ve `CMemFile` türetilen sınıflar `CFile` ve `CSharedFile` türetilmiş sınıf `CMemFile` daha özel dosya hizmetleri sağlayın.

MFC dosya işleme için diğer yollar hakkında daha fazla bilgi için bkz. [dosya işleme](../c-runtime-library/file-handling.md) içinde *çalışma zamanı kitaplığı başvurusu*.

Hakkında bilgi için türetilmiş `CFile` sınıfları için bkz [MFC hiyerarşisi grafiği](../mfc/hierarchy-chart.md).

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz

*CFile kullanın*

- [CFile ile bir dosyayı açma](../mfc/opening-files.md)

- [CFile ile bir dosyasını okuma ve yazma](../mfc/reading-and-writing-files.md)

- [CFile dosyasıyla kapatın](../mfc/closing-files.md)

- [CFile ile erişim dosya durumu](../mfc/accessing-file-status.md)

*MFC seri hale getirme (nesne Kalıcılık) kullanın*

- [Seri hale getirilebilir bir sınıf oluşturma](../mfc/serialization-making-a-serializable-class.md)

- [CArchive nesnesi aracılığıyla bir nesneyi serileştirmek](../mfc/serialization-serializing-an-object.md)

- [CArchive nesnesi oluşturma](../mfc/two-ways-to-create-a-carchive-object.md)

- [CArchive kullanın <\< ve >> işleçleri](../mfc/using-the-carchive-output-and-input-operators.md)

- [Store ve yük CObjects ve CObject türetilmiş nesneler aracılığıyla bir arşiv](../mfc/storing-and-loading-cobjects-via-an-archive.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../mfc/mfc-concepts.md)<br/>
[Genel MFC Konuları](../mfc/general-mfc-topics.md)<br/>
[CArchive Sınıfı](../mfc/reference/carchive-class.md)<br/>
[CObject Sınıfı](../mfc/reference/cobject-class.md)
