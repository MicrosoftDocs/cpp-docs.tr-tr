---
title: Veritabanı Uygulamaları Oluşturmak için İşlem Dizisi
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
ms.openlocfilehash: c393269d6af108ee82786e9d59f81aad11428157
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372767"
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>Veritabanı Uygulamaları Oluşturmak için İşlem Dizisi

Aşağıdaki tablo, veritabanı uygulamaları yazmadaki rolünüzü ve çerçevenin rolünü gösterir.

> [!NOTE]
> Visual C++ ortamı ve sihirbazlar DAO'yu desteklemez (her ne kadar DAO sınıfları dahil olsa da ve bunları kullanmaya devam edebilirsiniz). Microsoft, yeni MFC projeleri için ODBC kullanmanızı önerir. DAO'yu yalnızca varolan uygulamaları korurken kullanmalısınız.

### <a name="creating-database-applications"></a>Veritabanı Uygulamaları Oluşturma

|Görev|Öyle.|Çerçeve yok|
|----------|------------|------------------------|
|MFC ODBC veya DAO sınıflarını kullanıp kullanmamaya karar verin.|Yeni MFC projeleri için ODBC'yi kullanın. Yalnızca varolan uygulamaları korumak için DAO'yu kullanın. Genel bilgi için [Veri Erişim Programlama](../data/data-access-programming-mfc-atl.md)makalesine bakın.|Çerçeve, veritabanı erişimini destekleyen sınıflar sağlar.|
|Veritabanı seçenekleri ile iskelet uygulama oluşturun.|MFC Uygulama Sihirbazı çalıştırın. Veritabanı Desteği sayfasında seçenekleri seçin. Kayıt görünümü oluşturan bir seçenek seçerseniz, şunları da belirtin:<br /><br />- Veri kaynağı ve tablo adı veya adları<br />- Adı veya adlarını sorgula.|MFC Uygulama Sihirbazı dosyaları oluşturur ve gerekli içerir belirtir. Belirttiğiniz seçeneklere bağlı olarak, dosyalar bir kayıt kümesi sınıfı içerebilir.|
|Veritabanı formunuzu veya formlarınızı tasarla.|Kayıt görünümü sınıflarınız için iletişim şablonu kaynaklarına denetimler yerleştirmek için Visual C++ iletişim düzenleyicisini kullanın.|MFC Uygulama Sihirbazı, doldurmanız için boş bir iletişim şablonu kaynağı oluşturur.|
|Gerektiğinde ek kayıt görünümü ve kayıt kümesi sınıfları oluşturun.|Görünümleri tasarlamak için sınıfları ve iletişim düzenleyicisini oluşturmak için Sınıf Görünümü'ni kullanın.|Sınıf Görünümü yeni sınıflarınız için ek dosyalar oluşturur.|
|Kodunuzda gerektiği gibi kayıt kümesi nesneleri oluşturun. Kayıtları işlemek için her kayıt kümesini kullanın...|Kayıt kümeleriniz, sihirbazlarla [CRecordset'ten](../mfc/reference/crecordset-class.md) türetilen sınıfları temel alar.|ODBC, veritabanı ile kayıt setinizin alan veri üyeleri arasında veri alışverişi yapmak için kayıt alanı değişimi (RFX) kullanır. Bir kayıt görünümü kullanıyorsanız, iletişim veri alışverişi (DDX) kayıt kümesi ve kayıt görünümündeki denetimler arasında veri alışverişi.|
|... veya açmak istediğiniz her veritabanı için kodunuzda açık bir [CDatabase](../mfc/reference/cdatabase-class.md) oluşturun.|Kayıt kümesi nesnelerinizi veritabanı nesnelerine dayandırın.|Veritabanı nesnesi veri kaynağına bir arabirim sağlar.|
|Veri sütunlarını dinamik olarak kayıt setinize bağla.|ODBC'de, bağlamayı yönetmek için türetilmiş kayıt kümesi sınıfınıza kod ekleyin. Makaleye bakın [Recordset: Dinamik Bağlama Veri Sütunları (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||

## <a name="see-also"></a>Ayrıca bkz.

[Framework'te Derleme](../mfc/building-on-the-framework.md)<br/>
[MFC Uygulamaları Nın Oluşturulmasına Yönelik İşlemler Sırası](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[OLE Uygulamaları Oluşturmak için İşlemler Dizisi](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[ActiveX Denetimleri Oluşturmak için İşlem Dizisi](../mfc/sequence-of-operations-for-creating-activex-controls.md)
