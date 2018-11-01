---
title: Özel Durum Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.exception
helpviewer_keywords:
- exception classes [MFC]
- exception handling [MFC], exception classes
- MFC, exceptions
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
ms.openlocfilehash: fad88fa36c64bd9d8ca28135c09a3f0ce8fe3c0c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441944"
---
# <a name="exception-classes"></a>Özel Durum Sınıfları

Sınıf kitaplığı sağlar sınıfını esas bir özel durum işleme mekanizması `CException`. Uygulama Çerçevesi kendi kodunda özel durumları kullanır; Ayrıca bunları sizin kullanabilirsiniz. Daha fazla bilgi için bkz [özel durumları](../mfc/exception-handling-in-mfc.md). Kendi özel durum türlerinden türetebilirsiniz `CException`.

MFC destekleyen özel durumların tüm özel durum sınıfları yanı sıra, kendi özel durum türetilen bir özel durum sınıfı sağlar.

[CException](../mfc/reference/cexception-class.md)<br/>
Özel durumlar için temel sınıf.

[CArchiveException](../mfc/reference/carchiveexception-class.md)<br/>
Arşiv özel durum.

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
DAO veritabanı işlemi başarısız kaynaklanan bir özel durum.

[CDBException](../mfc/reference/cdbexception-class.md)<br/>
Bir ODBC veritabanı işlem hatası kaynaklanan bir özel durum.

[CFileException](../mfc/reference/cfileexception-class.md)<br/>
Bir dosya odaklı özel durumu.

[CMemoryException](../mfc/reference/cmemoryexception-class.md)<br/>
Bir bellek yetersiz özel durum.

[CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)<br/>
Desteklenmeyen bir özellik kullanımından kaynaklanan bir özel durum.

[COleException](../mfc/reference/coleexception-class.md)<br/>
OLE işlenirken bir hata kaynaklanan bir özel durum. Bu sınıf, kapsayıcılar ve sunucular tarafından kullanılır.

[COleDispatchException](../mfc/reference/coledispatchexception-class.md)<br/>
Otomasyon işlemi sırasında bir hatayla sonuçlanan bir özel durum. Otomasyon özel durumları otomasyon sunucuları tarafından oluşturulan ve Otomasyon istemcileri tarafından yakalandı.

[CResourceException](../mfc/reference/cresourceexception-class.md)<br/>
Bir Windows kaynağı yüklemek için bir hatasından kaynaklanan bir özel durum.

[CUserException](../mfc/reference/cuserexception-class.md)<br/>
Kullanıcı tarafından başlatılan bir işlemin durdurmak için kullanılan bir özel durum. Genellikle, bu özel durum önce kullanıcı sorun bildirildi.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

