---
title: ODBC sınıfları | Microsoft Docs
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
- database classes [MFC], ODBC
- ODBC classes [MFC]
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97bbdb74d122e633574dcf76876f0907de8ef2c4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400591"
---
# <a name="odbc-classes"></a>ODBC Sınıfları

Bu sınıflar, çok çeşitli veritabanları açık veritabanı bağlantısı (ODBC) sürücüleri kullanılabilir kolay erişim vermek için diğer uygulama framework sınıfları ile çalışır.

ODBC veritabanı kullanan programlar olacaktır en az bir `CDatabase` nesnesi ve bir `CRecordset` nesne.

[CDatabase](../mfc/reference/cdatabase-class.md)<br/>
Veri kaynağı üzerinde çalışabileceğiniz bir veri kaynağına bağlantı kapsüller.

[CRecordset](../mfc/reference/crecordset-class.md)<br/>
Bir veri kaynağından seçilen kayıt kümesini yalıtır. Seçimi sıralama kayıt kümeleri kaydı başka bir kayıt kaydırma (ekleme, düzenleme ve silme kayıtlarını) kayıtlarınızı güncelleştirirken, seçime uygun bir filtre ile etkinleştirin ve elde edilen bilgilerle seçimi kümesini parametreleştirme veya çalışma zamanında hesaplanan.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Bir form sağlar doğrudan bağlı bir kayıt kümesi nesnesi için görünümü. İletişim kutusu veri değişimi (DDX) mekanizmasını kayıt ve kayıt görünümü denetimler arasında veri yapar. Tüm form görünümleri gibi bir iletişim şablon kaynağında bir kayıt görünümü temel alır. Kayıt görünümleri kaydı başka bir kayıt kümenize taşıma, kayıtları güncelleştirmek ve kayıt görünümü kapandığında ilişkili kayıt kapatma de destekler.

[CDBException](../mfc/reference/cdbexception-class.md)<br/>
Veri erişimi hataları işleme kaynaklanan bir özel durum. Bu sınıf, sınıf kitaplığı yer alan özel durum işleme mekanizması diğer özel durum sınıfları aynı amaca hizmet eder.

[CFieldExchange](../mfc/reference/cfieldexchange-class.md)<br/>
Hangi veri alan veri üyeleri ve ilgili tablo sütunları veri kaynağında bir kayıt kümesi nesnesi ve parametre veri üyeleri arasında kayıt alanı değişimi (RFX) desteklemek için bağlam bilgilerini sağlar. Sınıfına benzer [CDataExchange](../mfc/reference/cdataexchange-class.md), kullanılan benzer şekilde için iletişim kutusu veri değişimi (DDX).

## <a name="related-classes"></a>İlgili sınıflar

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
İkili büyük nesne (BLOB) depolama birimi için bir tanıtıcı gibi bir bit eşlemi kapsüller. `CLongBinary` nesneler, veritabanı tablolarında depolanan büyük veri nesnelerini yönetmek için kullanılır.

[CDBVariant](../mfc/reference/cdbvariant-class.md)<br/>
bir değeri, değerin veri türü hakkında endişelenmeden depolamanıza olanak tanır. `CDBVariant` veri türü bir birleşim içinde depolanan geçerli değer izler.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

