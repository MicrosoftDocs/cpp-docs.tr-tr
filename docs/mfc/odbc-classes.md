---
title: ODBC Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [MFC], ODBC
- ODBC classes [MFC]
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
ms.openlocfilehash: a4cfa0d7afa197de7b65b6a0bd6b881a09534ef6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447701"
---
# <a name="odbc-classes"></a>ODBC Sınıfları

Bu sınıflar, açık veritabanı bağlantısı (ODBC) sürücülerinin kullanılabildiği çok çeşitli veritabanlarına kolay erişim sağlamak için diğer uygulama çerçevesi sınıflarıyla birlikte çalışır.

ODBC veritabanları kullanan programlar en az bir `CDatabase` nesnesine ve `CRecordset` nesnesine sahip olur.

[CDatabase](../mfc/reference/cdatabase-class.md)<br/>
Veri kaynağında çalışabileceğiniz bir veri kaynağıyla bağlantısını kapsüller.

[CRecordset](../mfc/reference/crecordset-class.md)<br/>
Bir veri kaynağından seçilen bir kayıt kümesini kapsüller. Kayıt kümeleri kayıttan kayda kaydırma, kayıtları güncelleştirme (kayıtları ekleme, düzenlemeler ve silme), seçimi bir filtreyle niteleyen, seçimi sıralayarak ve seçimi çalışma zamanında elde edilen veya hesaplanan bilgilerle niteleyen şekilde etkinleştirir.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Bir Recordset nesnesine doğrudan bağlı bir form görünümü sağlar. İletişim kutusu veri değişimi (DDX) mekanizması, kayıt kümesi ve kayıt görünümünün denetimleri arasında veri değişimi. Tüm form görünümleri gibi, kayıt görünümü bir iletişim kutusu şablon kaynağını temel alır. Kayıt görünümleri Ayrıca kayıt görünümü kapandığında kayıt kümesinden kayda geçmeyi, kayıtları güncelleştirmeyi ve ilişkili kayıt kümesini kapatmayı destekler.

[CDBException](../mfc/reference/cdbexception-class.md)<br/>
Veri erişim işlemesinde hatalardan kaynaklanan bir özel durum. Bu sınıf, sınıf kitaplığının özel durum işleme mekanizmasında diğer özel durum sınıflarıyla aynı amaca hizmet eder.

[CFieldExchange](../mfc/reference/cfieldexchange-class.md)<br/>
, Alan veri üyeleri ve bir kayıt kümesi nesnesinin parametre veri üyeleri ile veri kaynağındaki karşılık gelen tablo sütunları arasındaki verileri değiş tokuş eden kayıt alanı değişimi 'ni (RFX) desteklemek için bağlam bilgilerini sağlar. İletişim kutusu veri değişimi (DDX) için benzer şekilde kullanılan [CDataExchange](../mfc/reference/cdataexchange-class.md)sınıfına benzer.

## <a name="related-classes"></a>İlgili sınıflar

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
Bir bit eşlem gibi ikili büyük nesne (BLOB) için bir tanıtıcıyı saklar. `CLongBinary` nesneler, veritabanı tablolarında depolanan büyük veri nesnelerini yönetmek için kullanılır.

[CDBVariant](../mfc/reference/cdbvariant-class.md)<br/>
Değerin veri türü hakkında endişelenmeden bir değer depolamanıza olanak sağlar. `CDBVariant`, birleşimde depolanan geçerli değerin veri türünü izler.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
