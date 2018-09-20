---
title: Veritabanı uygulamaları oluşturmak için işlem dizisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef9c66324f886da27431a94a464554e2a8ddb00a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391586"
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>Veritabanı Uygulamaları Oluşturmak için İşlem Dizisi

Aşağıdaki tabloda, veritabanı uygulamaları yazılırken, rol ve framework'ün rol gösterir.

> [!NOTE]
>  Sihirbazlar ve Visual C++ ortamına DAO (DAO sınıflarına eklenmiştir ve bunları kullanmaya devam edebilirsiniz ancak) desteklemez. Microsoft, yeni MFC projeleri için ODBC kullanma önerir. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.

### <a name="creating-database-applications"></a>Veritabanı uygulamaları oluşturma

|Görev|Bunu|Framework yok|
|----------|------------|------------------------|
|DAO ya da MFC ODBC sınıfları kullanıp kullanmamaya karar verin.|ODBC yeni MFC projeleri için kullanın. DAO yalnızca mevcut uygulamaları korumak için kullanın. Genel bilgi için bkz [veri erişim programlama](../data/data-access-programming-mfc-atl.md).|Framework veritabanı erişimi destekleyen sınıflar sağlar.|
|Veritabanı seçenekleri ile iskelet uygulamanızı oluşturun.|MFC Uygulama Sihirbazı'nı çalıştırın. Veritabanı destek sayfasında seçenekleri belirleyin. Kayıt görünümü oluşturan bir seçeneği tercih ederseniz, ayrıca belirtin:<br /><br /> -Veri kaynağı ve tablo adı veya adları<br />-Sorgu ad veya adlar.|MFC Uygulama Sihirbazı dosyaları oluşturur ve gerekli içerir belirtir. Belirlediğiniz seçeneklere bağlı olarak, bir kayıt kümesi sınıfı dosyaları dahil edebilirsiniz.|
|Veritabanı formunu ya da formları tasarlayın.|Kayıt görünümü sınıfları için iletişim şablonu kaynaklarına denetimleri yerleştirmek için Visual C++ iletişim kutusu düzenleyicisi kullanın.|MFC Uygulama Sihirbazı, doldurmak bir boş iletişim şablon kaynağı oluşturur.|
|Ek Kayıt görünümü ve kayıt kümesi sınıflar gerektiği şekilde oluşturun.|Sınıf Görünümü sınıfları ve iletişim kutusunda, görünüm tasarlamak üzere düzenleyici oluşturmak için kullanın.|Sınıf Görünümü, yeni sınıflar için ek dosyalar oluşturur.|
|Kayıt kümesi nesneleri kodunuzda gerektiği gibi oluşturun. Kayıtları işlemek için her bir kayıt kümesi kullan...|Türetilen sınıflar kümeleriniz dayalı [CRecordset](../mfc/reference/crecordset-class.md) sihirbazları kullanarak.|ODBC kayıt alanı değişimi (RFX) veritabanı ve kümenizin alan veri üyeleri arasında veri alışverişi yapmak için kullanır. Kayıt görünümü kullanıyorsanız, kayıt ve kayıt görünümü denetimleri arasındaki veri iletişim kutusu veri değişimi (DDX) değiştirir.|
|.. veya açık bir oluşturma [CDatabase](../mfc/reference/cdatabase-class.md) açmak istediğiniz her veritabanı için kodunuzda.|Kayıt kümesi nesnelerinizi veritabanı nesneleri üzerinde temel alır.|Veritabanı nesnesini, veri kaynağı için bir arabirim sağlar.|
|Veri sütunlarını dinamik olarak kümenize bağlayın.|ODBC içinde kod bağlama yönetmek için türetilmiş bir kayıt kümesi sınıfına ekleyin. Makaleye göz atın [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'te Derleme](../mfc/building-on-the-framework.md)<br/>
[MFC Uygulamaları Oluşturmak için İşlem Dizisi](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[OLE Uygulamaları Oluşturmak için İşlem Dizisi](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[ActiveX Denetimleri Oluşturmak için İşlem Dizisi](../mfc/sequence-of-operations-for-creating-activex-controls.md)
