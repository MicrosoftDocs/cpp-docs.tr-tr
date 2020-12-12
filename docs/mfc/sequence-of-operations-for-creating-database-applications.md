---
description: 'Daha fazla bilgi edinin: veritabanı uygulamaları oluşturmak için Işlem dizisi'
title: Veritabanı Uygulamaları Oluşturmak için İşlem Dizisi
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
ms.openlocfilehash: 86f06ae5200fc8646ccb80bfec4e2814b94f9225
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217594"
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>Veritabanı Uygulamaları Oluşturmak için İşlem Dizisi

Aşağıdaki tabloda, veritabanı uygulamaları yazarken rolünüzün ve Framework 'ün rolü gösterilmektedir.

> [!NOTE]
> Visual C++ ortamı ve sihirbazları DAO 'YU desteklemez (DAO sınıfları dahil edilip kullanmaya devam edebilirsiniz). Microsoft, yeni MFC projeleri için ODBC kullanmanızı önerir. Yalnızca var olan uygulamaları korumak için DAO kullanmanız gerekir.

### <a name="creating-database-applications"></a>Veritabanı uygulamaları oluşturma

|Görev|Bunu yaptığınızda|Çerçeve|
|----------|------------|------------------------|
|MFC ODBC veya DAO sınıflarını kullanıp kullanmayacağınızı belirleyin.|Yeni MFC projeleri için ODBC kullanın. Mevcut uygulamaları sürdürmek için yalnızca DAO kullanın. Genel bilgi için bkz. [veri erişim programlama](../data/data-access-programming-mfc-atl.md)makalesi.|Framework, veritabanı erişimini destekleyen sınıflar sağlar.|
|Veritabanı seçenekleriyle iskelet uygulamanızı oluşturun.|MFC Uygulama Sihirbazı 'Nı çalıştırın. Veritabanı desteği sayfasında seçenekleri belirleyin. Kayıt görünümü oluşturan bir seçenek belirlerseniz, şunları da belirtin:<br /><br />-Veri kaynağı ve tablo adı veya adları<br />-Sorgu adı veya adları.|MFC Uygulama Sihirbazı dosyaları oluşturur ve gerekli eklemeleri belirtir. Belirttiğiniz seçeneklere bağlı olarak, dosyalar bir kayıt kümesi sınıfı içerebilir.|
|Veritabanı formunuzu veya formlarınızı tasarlayın.|Kayıt görünümü sınıflarınız için iletişim kutusu şablon kaynaklarına denetim yerleştirmek için Visual C++ iletişim düzenleyicisini kullanın.|MFC Uygulama Sihirbazı, doldurmanız için boş bir iletişim kutusu şablon kaynağı oluşturur.|
|Gerektiğinde ek kayıt görünümü ve kayıt kümesi sınıfları oluşturun.|Görünümleri tasarlamak üzere sınıfları ve iletişim kutusu düzenleyicisini oluşturmak için Sınıf Görünümü kullanın.|Sınıf Görünümü yeni sınıflarınız için ek dosyalar oluşturur.|
|Kodunuzda gereken şekilde kayıt kümesi nesneleri oluşturun. Kayıtları işlemek için her bir kayıt kümesini kullanın...|Kayıt kümeleriniz, Sihirbazlarla birlikte [CRecordset](../mfc/reference/crecordset-class.md) 'den türetilmiş sınıfları temel alır.|ODBC, veritabanı ve kayıt kümenizin alan veri üyeleri arasında veri alışverişi yapmak için kayıt alanı değişimi (RFX) kullanır. Bir kayıt görünümü kullanıyorsanız, iletişim kutusu veri değişimi (DDX) kayıt görünümündeki ve kayıt görünümündeki denetimler arasında verileri değiş tokuş eder.|
|... ya da açmak istediğiniz her veritabanı için kodunuzda açık bir [CDatabase](../mfc/reference/cdatabase-class.md) oluşturun.|Veritabanı nesnelerinde kayıt kümesi nesnelerinizi temel alır.|Veritabanı nesnesi veri kaynağına bir arabirim sağlar.|
|Veri sütunlarını dinamik olarak kayıt kümenize bağlayın.|ODBC ' de, bağlamayı yönetmek için türetilmiş kayıt kümesi sınıfınıza kod ekleyin. [Kayıt kümesi: dinamik olarak veri sütunlarını bağlama (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)makalesine bakın.||

## <a name="see-also"></a>Ayrıca bkz.

[Çerçevede derleme](../mfc/building-on-the-framework.md)<br/>
[MFC uygulamaları oluşturmak için Işlem dizisi](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[OLE uygulamaları oluşturmak için Işlem dizisi](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[ActiveX denetimleri oluşturmak için Işlem dizisi](../mfc/sequence-of-operations-for-creating-activex-controls.md)
