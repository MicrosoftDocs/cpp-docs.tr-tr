---
title: Kayıt görünümleri (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], record views
- ODBC recordsets [C++], record views
- databases [C++], record views
- record views [C++]
- forms [C++], data access tasks
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
ms.openlocfilehash: 31dbd92219f263c625050524279b97ef38ba9ba1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209137"
---
# <a name="record-views--mfc-data-access"></a>Kayıt görünümleri (MFC veri erişimi)

Bu bölüm yalnızca MFC ODBC sınıfları için geçerlidir. OLE DB kaydı görünümleri hakkında daha fazla bilgi için bkz. [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) ve [OLE DB kayıt Görünümlerini kullanma](../data/oledb/using-ole-db-record-views.md).

Form tabanlı veri erişimi uygulamalarını desteklemek için, sınıf kitaplığı [CRecordView](../mfc/reference/crecordview-class.md)sınıfına sağlar. Kayıt görünümü, denetimleri bir [kayıt kümesi](../data/odbc/recordset-odbc.md) nesnesinin alan veri üyelerine doğrudan eşlenmiş olan bir form görünümü nesnesidir (ve dolaylı olarak bir sorgu sonucu veya veri kaynağındaki tablodaki karşılık gelen sütunlara). Temel sınıf [CFormView](../mfc/reference/cformview-class.md)gibi `CRecordView`, bir iletişim şablonu kaynağını temel alır.

## <a name="form-uses"></a>Form kullanımları

Formlar çeşitli veri erişim görevleri için yararlıdır:

- Veri girme

- Verilerin salt okunurdur incelenmesi gerçekleştiriliyor

- Veriler güncelleştiriliyor

## <a name="further-reading-about-record-views"></a>Kayıt görünümleri hakkında daha fazla bilgi

Konulardaki malzemeler hem ODBC tabanlı hem de DAO tabanlı sınıflar için geçerlidir. ODBC için `CRecordView` ve DAO için `CDaoRecordView` kullanın.

Konu başlıkları şunlardır:

- [Kayıt görünümü sınıflarının özellikleri](../data/features-of-record-view-classes-mfc-data-access.md)

- [Kayıt görünümleri için veri değişimi](../data/data-exchange-for-record-views-mfc-data-access.md)

- [Bir kayıt görünümü ile çalışırken rolünüzün](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)

- [Kayıt görünümü tasarlama ve oluşturma](../data/designing-and-creating-a-record-view-mfc-data-access.md)

- [Kayıt görünümü kullanma](../data/using-a-record-view-mfc-data-access.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri erişim programlama (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)
