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
ms.openlocfilehash: 30d220c928f2ca3fe0594d03d558d2d6dcfce773
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="files-in-mfc"></a>MFC'deki Dosyalar
Microsoft Foundation Class Kitaplığı (MFC içinde), sınıf [CFile](../mfc/reference/cfile-class.md) normal dosya g/ç işlemleri gerçekleştirir. Bu makaleler ailesi, açın ve dosyaları kapatın yanı sıra okuma ve bu dosyaların veri yazma açıklanmaktadır. Ayrıca, dosya durum işlemleri anlatılmaktadır. MFC nesne tabanlı serileştirme özelliklerini okuma ve veri dosyaları yazılıyor alternatif bir yolu olarak kullanmak üzere nasıl açıklaması için bkz [seri hale getirme](../mfc/serialization-in-mfc.md).  
  
> [!NOTE]
>  MFC kullandığınızda **CDocument** nesneleri framework mu seri hale getirme iş çoğunu sizin için. Özellikle, framework oluşturduğu ve kullandığı `CFile` nesne. Yalnızca geçersiz kılmada kod yazmak zorunda `Serialize` sınıfının üye işlevini **CDocument**.  
  
 `CFile` Sınıfı, genel amaçlı ikili dosya işlemleri için bir arabirim sağlar. `CStdioFile` Ve `CMemFile` türetilmiş sınıfları `CFile` ve `CSharedFile` türetilmiş sınıf `CMemFile` daha özel dosya hizmetleri sağlayın.  
  
 MFC dosya işleme alternatifleri hakkında daha fazla bilgi için bkz: [dosya işleme](../c-runtime-library/file-handling.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
 Hakkında bilgi için türetilen `CFile` sınıfları için bkz [MFC hiyerarşi grafiği](../mfc/hierarchy-chart.md).  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz  
 *CFile kullanın*  
  
-   [CFile ile bir dosya açın](../mfc/opening-files.md)  
  
-   [Okuma ve yazma CFile sahip bir dosya](../mfc/reading-and-writing-files.md)  
  
-   [CFile sahip bir dosyayı kapatma](../mfc/closing-files.md)  
  
-   [CFile ile erişim dosya durumu](../mfc/accessing-file-status.md)  
  
 *MFC seri hale getirme (nesne Kalıcılık) kullanın*  
  
-   [Seri hale getirilebilir bir sınıf oluşturun](../mfc/serialization-making-a-serializable-class.md)  
  
-   [CArchive nesnesi aracılığıyla bir nesneyi serileştirme](../mfc/serialization-serializing-an-object.md)  
  
-   [CArchive nesnesi oluşturun](../mfc/two-ways-to-create-a-carchive-object.md)  
  
-   [CArchive kullanın <\< ve >> işleçleri](../mfc/using-the-carchive-output-and-input-operators.md)  
  
-   [Depolamak ve CObjects ve CObject türetilmiş nesneler bir arşiv aracılığıyla yükle](../mfc/storing-and-loading-cobjects-via-an-archive.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../mfc/mfc-concepts.md)   
 [Genel MFC konuları](../mfc/general-mfc-topics.md)   
 [CArchive sınıfı](../mfc/reference/carchive-class.md)   
 [CObject Sınıfı](../mfc/reference/cobject-class.md)
