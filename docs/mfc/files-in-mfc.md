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
ms.openlocfilehash: 8b8859e188e42f4419ca7ee7f683cc31de0c75b3
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625873"
---
# <a name="files-in-mfc"></a>MFC'deki Dosyalar

Microsoft Foundation Class Kitaplığı (MFC), sınıf [CFile](reference/cfile-class.md) normal dosya g/ç işlemlerini işler. Bu makale ailesinde, dosyaların nasıl açılacağı ve kapatılanları ve bu dosyalardaki verileri okuma ve yazma işlemleri açıklanmaktadır. Ayrıca dosya durumu işlemlerini de açıklar. MFC 'nin nesne tabanlı serileştirme özelliklerinin, dosyalardaki verileri okumaktan ve yazmanın alternatif bir yolu olarak nasıl kullanılacağına ilişkin bir açıklama için bkz. [serileştirme](serialization-in-mfc.md)makalesi.

> [!NOTE]
> MFC `CDocument` nesnelerini kullandığınızda çerçeve, serileştirme işinin çoğunu sizin için işler. Özellikle, çerçeve nesnesini oluşturur ve kullanır `CFile` . Yalnızca sınıfının üye işlevinin geçersiz kılmada kod yazmanız yeterlidir `Serialize` `CDocument` .

`CFile`Sınıfı, genel amaçlı ikili dosya işlemlerine yönelik bir arabirim sağlar. Ve sınıfından türetilmiş `CStdioFile` `CMemFile` sınıflar ve `CFile` `CSharedFile` `CMemFile` daha özelleştirilmiş dosya hizmetleri sağlayın.

MFC dosya işleme alternatifleri hakkında daha fazla bilgi için bkz. *çalışma zamanı kitaplık başvurusunda* [Dosya işleme](../c-runtime-library/file-handling.md) .

Türetilmiş sınıflar hakkında daha fazla bilgi için `CFile` bkz. [MFC hiyerarşi grafiği](hierarchy-chart.md).

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

*CFile kullan*

- [CFile ile dosya açma](opening-files.md)

- [CFile ile dosya okuma ve yazma](reading-and-writing-files.md)

- [CFile ile bir dosyayı kapatma](closing-files.md)

- [CFile ile dosya durumuna erişme](accessing-file-status.md)

*MFC serileştirme kullanma (nesne kalıcılığı)*

- [Serileştirilebilir sınıf oluşturma](serialization-making-a-serializable-class.md)

- [CArchive nesnesi aracılığıyla bir nesneyi seri hale getirme](serialization-serializing-an-object.md)

- [CArchive nesnesi oluşturma](two-ways-to-create-a-carchive-object.md)

- [CArchive <\< and >> işleçlerini kullanma](using-the-carchive-output-and-input-operators.md)

- [CObjects ve CObject ile türetilmiş nesneleri bir arşiv aracılığıyla depolayın ve yükleyin](storing-and-loading-cobjects-via-an-archive.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](mfc-concepts.md)<br/>
[Genel MFC Konuları](general-mfc-topics.md)<br/>
[CArchive sınıfı](reference/carchive-class.md)<br/>
[CObject sınıfı](reference/cobject-class.md)
