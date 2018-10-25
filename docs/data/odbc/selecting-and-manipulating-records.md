---
title: Kayıtları seçme ve düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, selecting
- record selection, MFC ODBC classes
- ODBC recordsets, selecting records
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8cfbeaa1fac2fd9df707dfa9c16ec168d48fc215
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078355"
---
# <a name="selecting-and-manipulating-records"></a>Kayıtları Seçme ve Düzenleme

Normalde seçtiğinizde, kayıtları bir SQL kullanarak bir veri kaynağından **seçin** deyimi, bir dizi kayıtlardan bir tablo veya bir sorgu bir sonuç kümesi alın. Veritabanı sınıfları ile seçin ve sonuç kümesi erişmek için bir kayıt kümesi nesnesi kullanın. Bu sınıftan türetilen bir uygulamaya özgü sınıfın bir nesnesi, [CRecordset](../../mfc/reference/crecordset-class.md). Kayıt kümesi sınıfı tanımladığınızda, ile ilişkilendirmek istediğiniz veri kaynağı tablosunu ve tablo sütunları belirtin. MFC Uygulama Sihirbazı'nı veya **sınıfı Ekle** (açıklandığı [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) belirli bir veri kaynağına bağlantı ile bir sınıf oluşturur. Sihirbazlar [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) sınıfının üye işlevinde `CRecordset` tablo adını döndürmek için. Kayıt kümesi sınıfları oluşturmak için sihirbaz kullanma hakkında daha fazla bilgi için bkz. [veritabanı desteği, MFC Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md) ve [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).

Kullanarak bir [CRecordset](../../mfc/reference/crecordset-class.md) nesne çalışma zamanında, şunları yapabilirsiniz:

- Geçerli kayıt veri alanlarını inceleyin.

- Filtreleme veya sıralama kayıt.

- Varsayılan SQL özelleştirme **seçin** deyimi.

- Seçili kayıtlarda gezinin.

- Ekleme, güncelleştirme veya (hem veri kaynağı kayıt güncelleştirilebilir ise) kayıtlarını silin.

- Kayıt kümesinde yeniden sorgulama izin verip vermediğini test ve kümesinin içeriği yenileyin.

Kayıt kümesi nesnesi kullanarak işiniz bittiğinde kapatın ve onu yok. Kayıt kümeleri hakkında daha fazla bilgi için bkz. [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md).

## <a name="see-also"></a>Ayrıca Bkz.

[ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)