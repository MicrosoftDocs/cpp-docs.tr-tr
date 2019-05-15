---
title: Kayıtları Seçme ve Düzenleme
ms.date: 05/09/2019
helpviewer_keywords:
- records, selecting
- record selection, MFC ODBC classes
- ODBC recordsets, selecting records
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
ms.openlocfilehash: 745c0c35e42426242d92d720d5dcd3de631fb17b
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707803"
---
# <a name="selecting-and-manipulating-records"></a>Kayıtları Seçme ve Düzenleme

> [!NOTE] 
> MFC ODBC Tüketici Sihirbazı'nı ve sonrasında Visual Studio 2019 içinde kullanılabilir değil. Bir tüketici yine de el ile oluşturabilirsiniz.

Normalde seçtiğinizde, kayıtları bir SQL kullanarak bir veri kaynağından **seçin** deyimi, bir dizi kayıtlardan bir tablo veya bir sorgu bir sonuç kümesi alın. Veritabanı sınıfları ile seçin ve sonuç kümesi erişmek için bir kayıt kümesi nesnesi kullanın. Bu sınıftan türetilen bir uygulamaya özgü sınıfın bir nesnesi, [CRecordset](../../mfc/reference/crecordset-class.md). Kayıt kümesi sınıfı tanımladığınızda, ile ilişkilendirmek istediğiniz veri kaynağı tablosunu ve tablo sütunları belirtin. MFC Uygulama Sihirbazı'nı veya **sınıfı Ekle** (açıklandığı [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) belirli bir veri kaynağına bağlantı ile bir sınıf oluşturur. Sihirbazlar [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) sınıfının üye işlevinde `CRecordset` tablo adını döndürmek için.

Kullanarak bir [CRecordset](../../mfc/reference/crecordset-class.md) nesne çalışma zamanında, şunları yapabilirsiniz:

- Geçerli kayıt veri alanlarını inceleyin.

- Filtreleme veya sıralama kayıt.

- Varsayılan SQL özelleştirme **seçin** deyimi.

- Seçili kayıtlarda gezinin.

- Ekleme, güncelleştirme veya (hem veri kaynağı kayıt güncelleştirilebilir ise) kayıtlarını silin.

- Kayıt kümesinde yeniden sorgulama izin verip vermediğini test ve kümesinin içeriği yenileyin.

Kayıt kümesi nesnesi kullanarak işiniz bittiğinde kapatın ve onu yok. Kayıt kümeleri hakkında daha fazla bilgi için bkz. [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)