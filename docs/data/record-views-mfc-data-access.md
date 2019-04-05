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
ms.openlocfilehash: 199f51f20dd42ee9105b4e09f579c1f48948745f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59040205"
---
# <a name="record-views--mfc-data-access"></a>Kayıt görünümleri (MFC veri erişimi)

Bu bölüm, yalnızca MFC ODBC sınıfları için geçerlidir. OLE DB kayıt görünümleri hakkında daha fazla bilgi için bkz: [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) ve [kullanarak OLE DB kayıt görünümleri](../data/oledb/using-ole-db-record-views.md).

Form tabanlı veri erişimi uygulamaları desteklemek için sınıf kitaplığı SAX [CRecordView](../mfc/reference/crecordview-class.md). Kayıt görünümü, denetimleri doğrudan alan veri üyeleri için eşlenmiş bir form görünümü nesnesi olan bir [kayıt](../data/odbc/recordset-odbc.md) nesnesi (ve karşılık gelen bir sorgu sonucunu veya veri kaynağında tablo sütunları için dolaylı olarak). Temel sınıfı gibi [CFormView](../mfc/reference/cformview-class.md), `CRecordView` iletişim şablon kaynağında temel alır.

## <a name="form-uses"></a>Form kullanır

Formlar çeşitli veri erişim görevleri için kullanışlıdır:

- Veri girme

- Salt okunur veri incelemesi gerçekleştirme

- Verileri güncelleştirme

## <a name="further-reading-about-record-views"></a>Kayıt görünümleri hakkında daha fazla bilgi

Malzeme konular, ODBC tabanlı ve DAO tabanlı sınıflar için geçerlidir. Kullanım `CRecordView` ODBC için ve `CDaoRecordView` DAO için.

Konular şunlardır:

- [Kayıt Görünümü Sınıflarının Özellikleri](../data/features-of-record-view-classes-mfc-data-access.md)

- [Kayıt Görünümleri için Veri Değişimi](../data/data-exchange-for-record-views-mfc-data-access.md)

- [Kayıt Görünümü ile Çalışırken Sizin Rolünüz](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)

- [Kayıt Görünümü Tasarlama ve Oluşturma](../data/designing-and-creating-a-record-view-mfc-data-access.md)

- [Kayıt Görünümünü Kullanma](../data/using-a-record-view-mfc-data-access.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri erişim programlama (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)