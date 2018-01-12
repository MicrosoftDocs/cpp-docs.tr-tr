---
title: "Dosya t-O sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.file
dev_langs: C++
helpviewer_keywords:
- disk file classes [MFC]
- stdio classes [MFC]
- OLE streams [MFC]
- I/O [MFC], MFC classes
- translated stream classes [MFC]
- file I/O classes [MFC]
- I/O [MFC], classes
- sockets classes [MFC]
- stream classes [MFC]
- memory file classes [MFC]
ms.assetid: 92821c3f-d9e1-47f6-98c9-3b632d86e811
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 454e64d67321282030126d2aab023e9f587c1cca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="file-io-classes"></a>Dosya G/Ç Sınıfları
Bu sınıfların geleneksel disk dosyaları, bellek içi dosyaları, etkin akışları ve Windows yuvaları için bir arabirim sağlar. Türetilen tüm sınıfları `CFile` ile kullanılan bir `CArchive` serileştirme gerçekleştirmek için nesne.  
  
 Aşağıdaki sınıflar özellikle kullanıyorsanız `CArchive` ve `CFile`, kendi giriş/çıkış işleme yazma. Normalde bu sınıflarından gerekmez. Uygulama Çerçevesi, varsayılan uygulamalarını kullanırsanız **açık** ve **kaydetmek** komutlarını **dosya** menüsü, dosya g/ç işleyecek (sınıfı kullanarak`CArchive`), belgenizin geçersiz kılma sürece `Serialize` işlevi sağlamak için ayrıntılı bir belge içeriğinin nasıl serileştiren hakkında. Dosya sınıfları ve seri hale getirme hakkında daha fazla bilgi için bkz: [MFC'deki dosyalar](../mfc/files-in-mfc.md) ve makale [seri hale getirme](../mfc/serialization-in-mfc.md).  
  
 [CFile](../mfc/reference/cfile-class.md)  
 İkili disk dosyalarını bir dosya arabirim sağlar.  
  
 [CStdioFile](../mfc/reference/cstdiofile-class.md)  
 Sağlayan bir `CFile` metin modunda genellikle arabelleğe alınan akışa disk dosyalarına arabirimi.  
  
 [CMemFile](../mfc/reference/cmemfile-class.md)  
 Sağlayan bir `CFile` bellek içi dosyalara arabirimi.  
  
 [CSharedFile](../mfc/reference/csharedfile-class.md)  
 Sağlayan bir `CFile` paylaşılan bellek içi dosyaları arabirimi.  
  
 [COleStreamFile](../mfc/reference/colestreamfile-class.md)  
 COM kullanan `IStream` sağlamak için arabirimini `CFile` dosyaları bileşik erişimi.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 Sağlayan bir `CFile` Windows yuva için arabirim.  
  
## <a name="related-classes"></a>İlgili sınıflar  
 [CArchive](../mfc/reference/carchive-class.md)  
 İle cooperates bir `CFile` nesneleri seri hale getirme yoluyla için kalıcı depolama uygulamak için nesne (bkz [CObject::Serialize](../mfc/reference/cobject-class.md#serialize)).  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 Arşiv özel durum.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 Bir dosya odaklı özel durumu.  
  
 [CFileDialog](../mfc/reference/cfiledialog-class.md)  
 Standart iletişim kutusu açılarak veya bir dosyayı kaydetmek için sağlar.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 En son kullanılan dosya listesi (MRU) korur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

