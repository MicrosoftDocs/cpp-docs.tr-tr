---
title: Kayıt görünümleri (MFC veri erişimi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], record views
- ODBC recordsets [C++], record views
- databases [C++], record views
- record views [C++]
- forms [C++], data access tasks
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fa8f3fd740de57cf556e723e00a8ef792adc5b36
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059018"
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

- [Kayıt görünümü sınıflarının özellikleri](../data/features-of-record-view-classes-mfc-data-access.md)

- [Kayıt görünümleri için veri değişimi](../data/data-exchange-for-record-views-mfc-data-access.md)

- [Kayıt görünümü ile çalışırken sizin rolünüz](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)

- [Kayıt görünümü tasarlama ve oluşturma](../data/designing-and-creating-a-record-view-mfc-data-access.md)

- [Kayıt görünümünü kullanma](../data/using-a-record-view-mfc-data-access.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Veri erişim programlama (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)