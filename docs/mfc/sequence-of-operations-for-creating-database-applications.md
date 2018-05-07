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
ms.openlocfilehash: cbe18e9733388cc6e43f6ca3de520596c713b783
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>Veritabanı Uygulamaları Oluşturmak için İşlem Dizisi
Aşağıdaki tabloda, rol ve framework'ün rol veritabanı uygulamaları yazma gösterir.  
  
> [!NOTE]
>  Visual C++ ortamı ve sihirbazları DAO (DAO sınıfları dahil edilmiştir ve bunları kullanmaya devam edebilirsiniz ancak) desteklemez. Microsoft, yeni MFC projeleri için ODBC kullanma önerir. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.  
  
### <a name="creating-database-applications"></a>Veritabanı uygulamaları oluşturma  
  
|Görev|Bunu|Framework mu|  
|----------|------------|------------------------|  
|MFC ODBC veya DAO sınıfları kullanıp kullanmamaya karar verin.|ODBC yeni MFC projeleri için kullanın. DAO yalnızca var olan uygulamaları korumak için kullanın. Genel bilgi için bkz: [veri erişim programlama](../data/data-access-programming-mfc-atl.md).|Framework veritabanı erişimi destekleyen sınıflar sağlar.|  
|Veritabanı seçenekleri ile iskelet uygulamanızı oluşturun.|MFC Uygulama Sihirbazı'nı çalıştırın. Veritabanı desteği sayfasındaki seçenekleri seçin. Kayıt görünümü oluşturan bir seçeneği seçerseniz, ayrıca belirtin:<br /><br /> -Veri kaynağı ve tablo adı veya adları<br />-Ad veya adlar sorgu.|MFC Uygulama Sihirbazı'nı dosyaları oluşturur ve gerekli içerip belirtir. Belirttiğiniz seçeneklere bağlı olarak, bir kayıt kümesi sınıfı dosyaları içerebilir.|  
|Veritabanı form ya da formlar tasarlayın.|Kayıt görünümü sınıfları için iletişim kutusu şablon kaynakları denetimlere yerleştirmek için Visual C++ iletişim kutusu düzenleyicisi kullanın.|MFC Uygulama Sihirbazı'nı, doldurmak bir boş iletişim şablon kaynağı oluşturur.|  
|Ek Kayıt görünümü ve kayıt kümesi sınıfları gerektiği şekilde oluşturun.|Sınıfları ve iletişim kutusu Düzenleyicisi'ni görünümleri tasarlama oluşturmak için sınıfı görünümünü kullanın.|Sınıf Görünümü yeni sınıflar için ek dosyalar oluşturur.|  
|Kayıt kümesi nesneleri kodunuzda gerektiği şekilde oluşturun. Kayıtları işlemek için her kayıt kümesi kullanmak...|Kümeleriniz kaynağından türetilmiş sınıflar temel alan [CRecordset](../mfc/reference/crecordset-class.md) sihirbazlarıyla.|ODBC kayıt alanı değişimi (RFX) veritabanı kümenizin alan veri üyeleri arasında veri değişimi için kullanır. Kayıt görünümü kullanıyorsanız, iletişim kutusu veri değişimi (DDX) kayıt kümesi ve kayıt görünümü denetimlerini arasında veri değiş tokuş eder.|  
|.. veya açık bir oluşturma [CDatabase](../mfc/reference/cdatabase-class.md) kodunuzda açmak istediğiniz her veritabanı için.|Kayıt kümesi nesnelerinizi veritabanı nesneleri üzerinde temel alır.|Veritabanı nesnesinin veri kaynağı için bir arabirim sağlar.|  
|Veri sütunlarını dinamik olarak kümenize bağlayın.|ODBC, kodu bağlama yönetmek için türetilmiş kayıt kümesi sınıfına ekleyin. Makalesine bakın [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'te derleme](../mfc/building-on-the-framework.md)   
 [MFC uygulamaları oluşturmak için işlem dizisi](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [OLE uygulamaları oluşturmak için işlem dizisi](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [ActiveX Denetimleri Oluşturmak için İşlem Dizisi](../mfc/sequence-of-operations-for-creating-activex-controls.md)
