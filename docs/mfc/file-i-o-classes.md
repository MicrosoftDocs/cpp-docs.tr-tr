---
title: Dosya g / Ç sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.file
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
ms.openlocfilehash: 914325ec56f0cae30c7293305496d65f358f2731
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405813"
---
# <a name="file-io-classes"></a>Dosya G/Ç Sınıfları

Bu sınıflar, geleneksel disk dosyaları, bellek içi dosyaları, etkin akışları ve Windows yuva için bir arabirim sağlar. Türetilen sınıfların tümü `CFile` ile kullanılan bir `CArchive` serileştirme gerçekleştirmek için nesne.

Aşağıdaki sınıflar, özellikle kullanıyorsanız `CArchive` ve `CFile`, kendi giriş/çıkış işleme yazma. Normalde bu sınıflarından gerekmez. Uygulama Çerçevesi, varsayılan uygulamalarını kullanırsanız **açık** ve **Kaydet** komutlarını **dosya** menü dosya g/ç işlemlerini ele alacak ( sınıfınıkullanarak`CArchive`) belgenizin geçersiz kılma sürece `Serialize` işlevi sağlamak için bir belge içeriğini nasıl serileştiren hakkında ayrıntıları. Dosya sınıfları ve seri hale getirme hakkında daha fazla bilgi için bkz [MFC'deki dosyalar](../mfc/files-in-mfc.md) ve makale [serileştirme](../mfc/serialization-in-mfc.md).

[CFile](../mfc/reference/cfile-class.md)<br/>
İkili disk dosyaları bir dosya arabirim sağlar.

[CStdioFile](../mfc/reference/cstdiofile-class.md)<br/>
Sağlar bir `CFile` metin modunda genellikle arabelleğe alınan akışa disk dosyalarına arabirimi.

[CMemFile](../mfc/reference/cmemfile-class.md)<br/>
Sağlar bir `CFile` bellek içi dosyaları için arabirim.

[CSharedFile](../mfc/reference/csharedfile-class.md)<br/>
Sağlar bir `CFile` paylaşılan bellek içi dosyaları arabirimi.

[COleStreamFile](../mfc/reference/colestreamfile-class.md)<br/>
COM kullanan `IStream` sağlamak için arabirimi `CFile` bileşik dosyalar için erişim.

[CSocketFile](../mfc/reference/csocketfile-class.md)<br/>
Sağlar bir `CFile` Windows yuva için arabirim.

## <a name="related-classes"></a>İlgili sınıflar

[CArchive](../mfc/reference/carchive-class.md)<br/>
İle cooperates bir `CFile` kalıcı depolama için seri hale getirme nesnelerde uygulamak için nesne (bkz [CObject::Serialize](../mfc/reference/cobject-class.md#serialize)).

[CArchiveException](../mfc/reference/carchiveexception-class.md)<br/>
Arşiv özel durum.

[CFileException](../mfc/reference/cfileexception-class.md)<br/>
Bir dosya odaklı özel durumu.

[CFileDialog](../mfc/reference/cfiledialog-class.md)<br/>
Standart iletişim kutusunu açmak veya dosyayı kaydetmek için sağlar.

[CRecentFileList](../mfc/reference/crecentfilelist-class.md)<br/>
En son kullanılan (MRU) dosya listesi tutar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
