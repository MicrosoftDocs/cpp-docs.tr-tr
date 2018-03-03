---
title: "ODBC sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.data
dev_langs:
- C++
helpviewer_keywords:
- database classes [MFC], ODBC
- ODBC classes [MFC]
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33fcc3453d36a2567330f60cec73383f842210c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-classes"></a>ODBC Sınıfları
Bu sınıfları, çok çeşitli açık veritabanı bağlantısı (ODBC) sürücüler kullanılabilir veritabanları için kolay erişim sağlamak için diğer uygulama framework sınıfları birlikte çalışın.  
  
 ODBC veritabanları kullanan programlar olacaktır en az bir `CDatabase` nesne ve `CRecordset` nesne.  
  
 [CDatabase](../mfc/reference/cdatabase-class.md)  
 Bir bağlantı veri kaynağı üzerinde çalışabilir, bir veri kaynağına yalıtır.  
  
 [CRecordset](../mfc/reference/crecordset-class.md)  
 Bir veri kaynağından seçilen kayıt kümesini yalıtır. Seçimi sıralama kayıt kümeleri kaydı başka bir kayıt kaydırma, (ekleme, düzenleme ve kayıt silme) kayıtları güncelleştirme, bir filtre ile seçimi niteleme etkinleştirin ve alınan bilgilerle seçim kümesini parametreleştirme veya çalışma zamanında hesaplanan.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Bir form sağlar doğrudan bağlı bir kayıt kümesi nesnesi görünümü. İletişim verisi (DDX) mekanizması kayıt kümesi ve kayıt görünümü denetimleri arasında veri değişimi. Tüm form görünümleri gibi bir kayıt görünümü bir iletişim şablon kaynağını temel alır. Kayıt görünümleri de kayıt kaydı kayıt kümesinde taşıma kayıtları güncelleştirme ve kayıt görünümü kapandığında ilişkili kayıt kümesi kapatma destekler.  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 Veri erişim hatalarına işlem kaynaklanan bir özel durum. Bu sınıf, sınıf kitaplığı özel durum işleme mekanizması içinde diğer özel durum sınıfları aynı amaca hizmet eder.  
  
 [CFieldExchange](../mfc/reference/cfieldexchange-class.md)  
 Hangi alan veri üyeleri ve parametre veri üyeleri bir kayıt kümesi nesnesi ve veri kaynağı üzerinde karşılık gelen tablo sütunları arasında veri alış verişleri kayıt alanı değişimi (RFX) desteklemek için bağlam bilgisi sağlar. Sınıfı için benzer [CDataExchange](../mfc/reference/cdataexchange-class.md), kullanılan benzer şekilde iletişim kutusu veri değişimi (DDX).  
  
## <a name="related-classes"></a>İlgili sınıflar  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 İkili büyük nesne (BLOB) için depolama alanı için bir tanıtıcı bir bit eşlem gibi yalıtır. `CLongBinary`nesneleri veritabanı tablolarında depolanan büyük veri nesneleri yönetmek için kullanılır.  
  
 [CDBVariant](../mfc/reference/cdbvariant-class.md)  
 Bir değer değerinin veri türü hakkında endişelenmeden depolamanıza olanak sağlar. `CDBVariant`veri türü bir birleşim içinde depolanan geçerli değeri izler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

