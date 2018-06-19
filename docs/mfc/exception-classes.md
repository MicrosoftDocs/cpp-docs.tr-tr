---
title: Özel durum sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.exception
dev_langs:
- C++
helpviewer_keywords:
- exception classes [MFC]
- exception handling [MFC], exception classes
- MFC, exceptions
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ce4085d0f5f2dcc73d126d04b7560ef8360ffd9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344902"
---
# <a name="exception-classes"></a>Özel Durum Sınıfları
Sınıf kitaplığı sınıfına dayalı bir özel durum işleme mekanizması sağlar `CException`. Uygulama Çerçevesi kendi kodunda özel durumları kullanır; Ayrıca bunları sizin kullanabilirsiniz. Daha fazla bilgi için bkz: [özel durumları](../mfc/exception-handling-in-mfc.md). Kendi özel durum türlerini türetmek `CException`.  
  
 MFC özel durum sınıfları yanı sıra kendi özel türetilen bir özel durum sınıfına tüm desteklediği özel durumlar için sağlar.  
  
 [CException](../mfc/reference/cexception-class.md)  
 Özel durumlar için temel sınıf.  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 Arşiv özel durum.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 DAO veritabanı işlemi bir hata kaynaklanan bir özel durum.  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 ODBC veritabanı işlem hatasından kaynaklanan bir özel durum.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 Bir dosya odaklı özel durumu.  
  
 [CMemoryException](../mfc/reference/cmemoryexception-class.md)  
 Bir bellek yetersiz özel durum.  
  
 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)  
 Desteklenmeyen bir özellik kullanımından kaynaklanan bir özel durum.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE işlenirken bir hata kaynaklanan bir özel durum. Bu sınıf, kapsayıcılar ve sunucular tarafından kullanılır.  
  
 [COleDispatchException](../mfc/reference/coledispatchexception-class.md)  
 Otomasyon sırasında bir hatayla sonuçlanan bir özel durum. Otomasyon özel durumlar otomasyon sunucuları tarafından oluşturulan ve Otomasyon istemcileri tarafından yakalandı.  
  
 [CResourceException](../mfc/reference/cresourceexception-class.md)  
 Bir Windows kaynağı yüklemek için bir hatadan kaynaklanan bir özel durum.  
  
 [CUserException](../mfc/reference/cuserexception-class.md)  
 Bir kullanıcı tarafından başlatılan işlemi durdurmak için kullanılan bir özel durum. Genellikle, bu özel durum önce kullanıcı sorun bildirildi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

