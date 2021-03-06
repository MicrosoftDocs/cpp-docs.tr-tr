---
description: 'Daha fazla bilgi edinin: özel durum sınıfları'
title: Özel Durum Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.exception
helpviewer_keywords:
- exception classes [MFC]
- exception handling [MFC], exception classes
- MFC, exceptions
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
ms.openlocfilehash: c07bd93a0abf95dc7d5f46c710faaad2dcad08c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290771"
---
# <a name="exception-classes"></a>Özel Durum Sınıfları

Sınıf kitaplığı, sınıfına dayalı bir özel durum işleme mekanizması sağlar `CException` . Uygulama çerçevesi, kodunda özel durumlar kullanır; bunları kendi içinde de kullanabilirsiniz. Daha fazla bilgi için bkz. Makale [özel durumları](exception-handling-in-mfc.md). Kendi özel durum türlerinizi içinden türetebilirsiniz `CException` .

MFC, kendi özel durumlarınızın yanı sıra desteklediği tüm özel durumlar için özel durum sınıflarını türetebilmeniz için bir özel durum sınıfı sağlar.

[CException](reference/cexception-class.md)<br/>
Özel durumlar için temel sınıf.

[CArchiveException](reference/carchiveexception-class.md)<br/>
Bir arşiv özel durumu.

[CDaoException](reference/cdaoexception-class.md)<br/>
Bir DAO veritabanı işleminde bir hatadan kaynaklanan bir özel durum.

[CDBException](reference/cdbexception-class.md)<br/>
ODBC veritabanı işlemede bir hatadan kaynaklanan bir özel durum.

[CFileException](reference/cfileexception-class.md)<br/>
Dosya odaklı özel durum.

[CMemoryException](reference/cmemoryexception-class.md)<br/>
Yetersiz bellek özel durumu.

[CNotSupportedException](reference/cnotsupportedexception-class.md)<br/>
Desteklenmeyen bir özelliğin kullanılmasıyla kaynaklanan bir özel durum.

[Colet özel durumu](reference/coleexception-class.md)<br/>
OLE işlemedeki bir hatadan kaynaklanan bir özel durum. Bu sınıf, hem kapsayıcılar hem de sunucular tarafından kullanılır.

[Cotadispatchexception](reference/coledispatchexception-class.md)<br/>
Otomasyon sırasında bir hatadan kaynaklanan bir özel durum. Otomasyon özel durumları otomasyon sunucuları tarafından oluşturulur ve Otomasyon istemcileri tarafından yakalanır.

[CResourceException](reference/cresourceexception-class.md)<br/>
Bir Windows kaynağı yükleme hatasından kaynaklanan bir özel durum.

[CUserException](reference/cuserexception-class.md)<br/>
Kullanıcı tarafından başlatılan bir işlemi durdurmak için kullanılan özel durum. Genellikle, bu özel durum oluşturulmadan önce kullanıcıya sorun bildirildi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
