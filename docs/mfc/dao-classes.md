---
title: DAO sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.data
dev_langs:
- C++
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f43595ca5f688372a70999231ceebec5282cd3b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="dao-classes"></a>DAO Sınıfları
Microsoft Visual Basic ve Microsoft Access aynı veritabanı altyapısı'nı kullanan veri erişim nesnesi (DAO) veritabanları kolay erişim sağlamak için diğer uygulama framework sınıfları ile bu sınıfların çalışır. DAO sınıfları, çok çeşitli açık veritabanı bağlantısı (ODBC) sürücüler kullanılabilir veritabanlarını da erişebilirsiniz.  
  
 DAO veritabanı kullanan programlar olacaktır en az bir `CDaoDatabase` nesne ve `CDaoRecordset` nesne.  
  
> [!NOTE]
>  Artık Visual C++ ortamı ve sihirbazları DAO (DAO sınıfları dahil edilmiştir ve bunları kullanmaya devam edebilirsiniz ancak) destekler. Microsoft, yeni MFC projeleri için ODBC kullanma önerir. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.  
  
 [CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)  
 Bir adlandırılmış, parola korumalı veritabanı oturum kapatma için oturumu açma yönetir. Çoğu program varsayılan çalışma alanını kullanın.  
  
 [CDaoDatabase](../mfc/reference/cdaodatabase-class.md)  
 Bir bağlantı verilerin çalışabilir veritabanına.  
  
 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)  
 Bir veri kaynağından seçilen kayıt kümesini temsil eder.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Veritabanı kayıtlarını denetimlerinde görüntüleyen bir görünüm.  
  
 [CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)  
 Sorgu tanımı, genellikle bir veritabanında kaydedilmiş temsil eder.  
  
 [CDaoTableDef](../mfc/reference/cdaotabledef-class.md)  
 Temel tablo veya ekli bir tablo saklı tanımını temsil eder.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 DAO sınıfları kaynaklanan bir özel durum koşulu temsil eder.  
  
 [CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)  
 DAO veritabanı sınıfları tarafından kullanılan DAO kayıt alanı değişimi (DFX) yordamları destekler. Doğrudan bu sınıfı kullanacağınız normalde değil.  
  
## <a name="related-classes"></a>İlgili sınıflar  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 İkili büyük nesne (BLOB) için depolama alanı için bir tanıtıcı bir bit eşlem gibi yalıtır. `CLongBinary` nesneleri veritabanı tablolarında depolanan büyük veri nesneleri yönetmek için kullanılır.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 OLE Otomasyon türü için sarmalayıcı **para birimi**, 15 basamağa ondalık ayırıcıdan önce ve sonra 4 basamaklı bir sabit noktalı aritmetik türü.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 OLE Otomasyon türü için sarmalayıcı **tarih**. Tarih ve saat değerlerini temsil eder.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 OLE Otomasyon türü için sarmalayıcı **değişken**. Verileri **değişken**s birçok biçimlerinde depolanabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

