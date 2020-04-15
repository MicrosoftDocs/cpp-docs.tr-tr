---
title: MFC'deki Dosyalar
ms.date: 11/04/2016
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
ms.openlocfilehash: 3a99c4143bbd27ba765b0289b80be8870a940f63
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365308"
---
# <a name="files-in-mfc"></a>MFC'deki Dosyalar

Microsoft Foundation Class Library'de (MFC), [CFile](../mfc/reference/cfile-class.md) sınıfı normal dosya G/Ç işlemlerini işler. Bu makale ailesi, dosyaların nasıl açılacağını ve kapatılacağını ve bu dosyalara veri okuma ve yazmanın yanı sıra nasıl açılacağını açıklar. Ayrıca dosya durumu işlemleri tartışır. MFC'nin nesne tabanlı serileştirme özelliklerinin dosyalardaki verileri okuma ve yazmanın alternatif bir yolu olarak nasıl kullanılacağına ilişkin bir açıklama için [Serihale](../mfc/serialization-in-mfc.md)etme makalesine bakın.

> [!NOTE]
> MFC `CDocument` nesnelerini kullandığınızda, çerçeve sizin için serileştirme çalışmalarının çoğunu yapar. Özellikle, çerçeve oluşturur ve `CFile` nesne kullanır. Yalnızca sınıfın `Serialize` `CDocument`üye işlevini geçersiz kılmanıza kod yazmanız gerekir.

Sınıf, `CFile` genel amaçlı ikili dosya işlemleri için bir arabirim sağlar. Ve `CStdioFile` `CMemFile` sınıflar türetilen `CFile` `CSharedFile` ve sınıf `CMemFile` kaynağı daha özel dosya hizmetleri türetilmiştir.

MFC dosya işleme alternatifleri hakkında daha fazla bilgi *için, Çalışma Zamanı Kitaplığı Başvurusu'nda* [Dosya İşleme'ye](../c-runtime-library/file-handling.md) bakın.

Türetilen `CFile` sınıflar hakkında bilgi için [MFC hiyerarşi grafiğine](../mfc/hierarchy-chart.md)bakın.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsun?

*CFile'ı Kullanma*

- [CFile ile dosya açma](../mfc/opening-files.md)

- [CFile ile dosya okuma ve yazma](../mfc/reading-and-writing-files.md)

- [CFile ile dosyayı kapatma](../mfc/closing-files.md)

- [CFile ile dosya durumuna erişin](../mfc/accessing-file-status.md)

*MFC Serileştirme (Nesne Kalıcılığı) kullanma*

- [Serileştirilebilir bir sınıf oluşturma](../mfc/serialization-making-a-serializable-class.md)

- [CArchive nesnesi üzerinden nesneyi seri hale](../mfc/serialization-serializing-an-object.md)

- [CArchive nesnesi oluşturma](../mfc/two-ways-to-create-a-carchive-object.md)

- [CArchive <\< ve >> işleçlerini kullanma](../mfc/using-the-carchive-output-and-input-operators.md)

- [CObjects ve CObject türetilmiş nesneleri arşiv aracılığıyla depolama ve yükleme](../mfc/storing-and-loading-cobjects-via-an-archive.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../mfc/mfc-concepts.md)<br/>
[Genel MFC Konuları](../mfc/general-mfc-topics.md)<br/>
[CArchive Sınıfı](../mfc/reference/carchive-class.md)<br/>
[CObject Sınıfı](../mfc/reference/cobject-class.md)
