---
description: 'Daha fazla bilgi edinin: dosya g/ç sınıfları'
title: Dosya g-ç sınıfları
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
ms.openlocfilehash: b2a0404864cd63ea3992ebada643b15531bcfc3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228020"
---
# <a name="file-io-classes"></a>Dosya G/Ç Sınıfları

Bu sınıflar, geleneksel disk dosyaları, bellek içi dosyalar, etkin akışlar ve Windows Yuvaları için bir arabirim sağlar. Öğesinden türetilen tüm sınıflar, `CFile` `CArchive` serileştirme gerçekleştirmek için bir nesneyle birlikte kullanılabilir.

Aşağıdaki sınıfları, özellikle `CArchive` ve `CFile` kendi giriş/çıkış işlelerinizi yazarsanız kullanın. Normalde bu sınıflardan türetmeniz gerekmez. Uygulama çerçevesini kullanıyorsanız, **Dosya** menüsündeki **Aç** ve **Kaydet** komutlarının varsayılan uygulamaları dosya g/ç 'yi (sınıfını kullanarak) işleyerek `CArchive` , belgenin `Serialize` işlevini bir belgenin nasıl seri hale getirip ilişkin ayrıntıları sağlamak üzere belgenizin işlevini geçersiz kılacaksınız. Dosya sınıfları ve serileştirme hakkında daha fazla bilgi için, [MFC 'deki](files-in-mfc.md) ve [serileştirme](serialization-in-mfc.md)makalesindeki makale dosyalarına bakın.

[CFile](reference/cfile-class.md)<br/>
İkili disk dosyaları için bir dosya arabirimi sağlar.

[CStdioFile](reference/cstdiofile-class.md)<br/>
`CFile`Genellikle metin modunda, arabelleğe alınmış akış disk dosyaları için bir arabirim sağlar.

[CMemFile](reference/cmemfile-class.md)<br/>
`CFile`Bellek içi dosyalar için bir arabirim sağlar.

[CSharedFile](reference/csharedfile-class.md)<br/>
`CFile`Paylaşılan bellek dosyaları için bir arabirim sağlar.

[Cotastreamfile](reference/colestreamfile-class.md)<br/>
`IStream`Bileşik dosyalara erişim sağlamak IÇIN com arabirimini kullanır `CFile` .

[CSocketFile](reference/csocketfile-class.md)<br/>
Bir `CFile` Windows yuvasına arabirim sağlar.

## <a name="related-classes"></a>İlgili sınıflar

[CArchive](reference/carchive-class.md)<br/>
`CFile`Serileştirme yoluyla nesneler için kalıcı depolamayı uygulamak üzere bir nesneyle birlikte çalışır (bkz. [CObject:: serileştirme](reference/cobject-class.md#serialize)).

[CArchiveException](reference/carchiveexception-class.md)<br/>
Bir arşiv özel durumu.

[CFileException](reference/cfileexception-class.md)<br/>
Dosya odaklı özel durum.

[CFileDialog](reference/cfiledialog-class.md)<br/>
Dosya açmak veya kaydetmek için standart bir iletişim kutusu sağlar.

[CRecentFileList](reference/crecentfilelist-class.md)<br/>
En son kullanılan (MRU) dosya listesini korur.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
