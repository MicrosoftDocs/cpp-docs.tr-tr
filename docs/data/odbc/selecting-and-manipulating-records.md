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
ms.openlocfilehash: 2a4b76d0b4273e5afb32206336b4aabbfe9294eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="selecting-and-manipulating-records"></a>Kayıtları Seçme ve Düzenleme
Normalde seçtiğinizde kayıtları bir SQL kullanarak bir veri kaynağından **seçin** deyimi, bir tablo veya bir sorgu kayıtlarından bir dizi bir sonuç kümesi alın. Veritabanı sınıfları ile seçin ve sonuç kümesi erişmek için bir kayıt kümesi nesnesi kullanın. Bu sınıftan türeyen bir uygulamaya özgü sınıfın bir nesnesi olup [CRecordset](../../mfc/reference/crecordset-class.md). Bir kayıt kümesi sınıf tanımladığınızda, veri kaynağı ile ilişkilendirmek için kullanılacak tabloyu ve tablosunun sütunları belirtin. MFC Uygulama Sihirbazı'nı veya **sınıfı Ekle** (açıklandığı gibi [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) belirli bir veri kaynağı bağlantısı olan bir sınıf oluşturur. Sihirbazlar yazma [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) sınıfının üye işlevini `CRecordset` tablo adını döndürmek için. Kayıt kümesi sınıfları oluşturmak için sihirbaz kullanma hakkında daha fazla bilgi için bkz: [veritabanı desteği, MFC Uygulama Sihirbazı'nı](../../mfc/reference/database-support-mfc-application-wizard.md) ve [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Kullanarak bir [CRecordset](../../mfc/reference/crecordset-class.md) nesne çalışma zamanında, şunları yapabilirsiniz:  
  
-   Geçerli kayıt veri alanlarını inceleyin.  
  
-   Filtre veya kayıt sıralayabilirsiniz.  
  
-   Varsayılan SQL özelleştirme **seçin** deyimi.  
  
-   Seçili kayıt arasında gezinin.  
  
-   Ekleme, güncelleştirme veya (veri kaynağı ve kayıt güncelleştirilebilir değilse) kayıtları silin.  
  
-   Kayıt kümesinde yeniden sorgulama izin verip vermediğini test edin ve kayıt kümesinin içeriği yenileyin.  
  
 Kayıt kümesi nesnesi kullanılarak bitirdikten sonra kapatın ve onu yok. Kayıt kümeleri hakkında daha fazla bilgi için bkz: [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)