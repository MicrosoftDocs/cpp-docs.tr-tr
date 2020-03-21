---
title: Kayıtları Seçme ve Düzenleme
ms.date: 05/09/2019
helpviewer_keywords:
- records, selecting
- record selection, MFC ODBC classes
- ODBC recordsets, selecting records
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
ms.openlocfilehash: 8388cd5c8c53a4595dc9b44430077421ee8680bf
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079794"
---
# <a name="selecting-and-manipulating-records"></a>Kayıtları Seçme ve Düzenleme

> [!NOTE]
> MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. Yine de bir tüketicisi el ile oluşturabilirsiniz.

Normal olarak, bir SQL **Select** ifadesini kullanarak bir veri kaynağından kayıtlar ' ı seçtiğinizde, bir tablo veya sorgudan bir kayıt kümesi olan bir sonuç kümesi elde edersiniz. Veritabanı sınıflarıyla, sonuç kümesini seçmek ve erişmek için bir kayıt kümesi nesnesi kullanırsınız. Bu, [CRecordset](../../mfc/reference/crecordset-class.md)sınıfından türettiğiniz uygulamaya özgü sınıfın bir nesnesidir. Bir kayıt kümesi sınıfı tanımladığınızda, ile ilişkilendirilecek veri kaynağını, kullanılacak tabloyu ve tablonun sütunlarını belirtirsiniz. MFC Uygulama Sihirbazı veya **Sınıf Ekle** ( [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)bölümünde açıklandığı gibi), belirli bir veri kaynağına bağlantısı olan bir sınıf oluşturur. Sihirbazlar tablo adını döndürmek için `CRecordset`, sınıfının [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) üye işlevini yazar.

Çalışma zamanında bir [CRecordset](../../mfc/reference/crecordset-class.md) nesnesi kullanarak şunları yapabilirsiniz:

- Geçerli kaydın veri alanlarını inceleyin.

- Kayıt kümesini filtreleyin veya sıralayın.

- Varsayılan SQL **Select** ifadesini özelleştirin.

- Seçili kayıtlarda ilerleyin.

- Kayıt ekleme, güncelleştirme veya silme (hem veri kaynağı hem de kayıt kümesi güncelleştirilebilir ise).

- Kayıt kümesinin, kayıt kümesinin içeriğini yeniden sorgulama ve yenileme izni verip etmeyeceğini test edin.

Kayıt kümesi nesnesini kullanmayı bitirdiğinizde, kapatır ve yok edersiniz. Kayıt kümeleri hakkında daha fazla bilgi için bkz. [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)