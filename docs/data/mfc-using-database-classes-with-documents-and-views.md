---
title: "MFC: Belgeler ve görünümler ile veritabanı sınıflarını kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- documents [C++], database applications
- recordsets [C++], documents and views
- CRecordView class, using in database forms
- views [C++], database applications
- forms [C++], database applications
- record views [C++], form-based applications
- document/view architecture [C++], in databases
- database applications [C++], forms
- database classes [C++], MFC
- ODBC recordsets [C++], documents and views
- ODBC [C++], forms
ms.assetid: 83979974-fc63-46ac-b162-e8403a572e2c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b63e864b519dd55eedf96d525a25897c81f16ac0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC: Belgeler ve Görünümler ile Veritabanı Sınıflarını Kullanma
MFC veritabanı sınıfları ile veya belge/görünüm mimarisinin olmadan kullanabilirsiniz. Bu konu, belgeler ve görünümler ile çalışma vurgular. Açıklar:  
  
-   [Form tabanlı bir uygulama yazmak nasıl](#_core_writing_a_form.2d.based_application) kullanarak bir `CRecordView` nesnesi belgenizi ana görünüm olarak.  
  
-   [Kayıt kümesi nesnelerinin belgeler ve görünümler içinde nasıl kullanılacağını](#_core_using_recordsets_in_documents_and_views).  
  
-   [Diğer noktalar](#_core_other_factors).  
  
 Alternatifler için bkz: [MFC: olmadan veritabanı sınıflarını belgeleri kullanarak ve görünümleri](../data/mfc-using-database-classes-without-documents-and-views.md).  
  
##  <a name="_core_writing_a_form.2d.based_application"></a>Form tabanlı bir uygulama yazma  
 Birçok veri erişimi uygulamaları formlarını temel alır. Kullanıcı arabirimi, kullanıcı inceler, girer veya veri düzenler denetimleri içeren bir biçimidir. Uygulamanızı form temelli yapmak için bir sınıf kullanma `CRecordView`. MFC Uygulama Sihirbazı'nı çalıştırın ve seçin, **ODBC** istemci türüne **veritabanı desteği** sayfası, proje kullanır `CRecordView` görünüm sınıfı için.
  
 Form tabanlı bir uygulama, her kayıt görünümü nesneyi gösteren bir işaretçi depolar bir `CRecordset` nesnesi. Framework'ün kayıt alanı değişimi (RFX) mekanizması kayıt kümesi ve veri kaynağı arasında veri değiş tokuş eder. İletişim verisi (DDX) mekanizması kayıt kümesi nesnesi alan veri üyeleri ve form üzerinde denetimleri arasında veri değişimi. `CRecordView`Ayrıca varsayılan kayıt kaydı formda gezinme için komut işleyici işlevleri sağlar.  
  
 Uygulama Sihirbazı'nı form tabanlı bir uygulama oluşturmak için bkz: [bir form tabanlı MFC uygulaması oluşturma](../mfc/reference/creating-a-forms-based-mfc-application.md) ve [veritabanı desteği, MFC Uygulama Sihirbazı'nı](../mfc/reference/database-support-mfc-application-wizard.md).  
  
 Forms tam bir irdelemesi için bkz: [kayıt görünümleri](../data/record-views-mfc-data-access.md).  
  
##  <a name="_core_using_recordsets_in_documents_and_views"></a>Kayıt kümeleri belgeler ve görünümler içinde kullanma  
 Birçok basit form tabanlı uygulamalar belgeleri gerekmez. Uygulamanızı büyük olasılıkla bir belge bir proxy olarak veritabanı için kullanmak istediğiniz daha karmaşık ise, depolama bir `CDatabase` veri kaynağına bağlanan nesne. Form tabanlı uygulamalar genellikle görünümde bir kayıt kümesi nesnesi için bir işaretçi depolar. Veritabanı uygulamaları diğer tür kayıt kümelerini depolamak ve `CDatabase` belgedeki nesne. Veritabanı uygulamalarında belgeleri kullanmak için bazı olanaklar şunlardır:  
  
-   Kayıt kümesi yerel bağlamda erişiyorsanız, oluşturma bir `CRecordset` nesne yerel olarak içindeki üye işlevleri belge veya görünümünün gerektiğinde.  
  
     Bir işlevdeki yerel değişken olarak bir kayıt kümesi nesnesi bildirin. Geçirmek **NULL** oluşturucuya neden olan oluşturmak ve geçici bir açmak framework `CDatabase` nesnesi. Alternatif olarak, geçirmek için bir işaretçi bir `CDatabase` nesnesi. Kayıt kümesi işlev içinde kullanmak ve onu işlevi çıktığında otomatik olarak yok edilmesi izin verin.  
  
     Geçirdiğiniz zaman **NULL** bir kayıt kümesi oluşturucuya çerçevesi kümesinin tarafından döndürülen bilgileri kullanır, `GetDefaultConnect` oluşturmak için üye işlevi bir `CDatabase` nesne ve açın. Sihirbazlar uygulamak `GetDefaultConnect` sizin için.  
  
-   Belgenizi ömrü boyunca kayıt erişiyorsanız, bir veya daha fazla katıştırmak `CRecordset` belgenizi nesneleri.  
  
     Kayıt kümesi nesneleri belgeyi başlattığınızda veya gerektiği şekilde oluşturun. Zaten var veya oluşturur ve henüz yoksa kayıt kümesi açar, kayıt kümesine bir işaretçi döndüren bir işlev yazabilirsiniz. Kapatın, silin ve kayıt gerektiği gibi yeniden oluşturun veya çağrı kendi **Requery** kayıtları yenilemek için üye işlevi.  
  
-   Belgenizi ömrü boyunca bir veri kaynağı erişiyorsanız katıştırmak bir `CDatabase` nesne veya depolamak için bir işaretçi bir `CDatabase` nesnesine.  
  
     `CDatabase` Nesnesi, veri kaynağına bağlantı yönetir. Nesne belge oluşturma sırasında otomatik olarak oluşturulur ve çağırmanız kendi **açık** belge başlattığınızda üye işlevi. Belge üye işlevlerinde kayıt kümesi nesneleri oluşturmak olduğunda, belgenin bir işaretçi geçir `CDatabase` nesnesi. Bu, her kayıt kümesi kendi veri kaynağı ile ilişkilendirir. Belge kapandığında veritabanı nesnesi genellikle yok. Bir işlev kapsamını çıktığınızda kayıt kümesi nesneleri genellikle yok olur.  
  
##  <a name="_core_other_factors"></a>Diğer etkenlere bağlı  
 Form tabanlı uygulamalar genellikle yok kullanım framework'ün belge serileştirme mekanizması, Kaldır, devre dışı bırakın ya da değiştirmek isteyebilirsiniz `New` ve **açık** komutlarını **dosya**menüsü. Makalesine bakın [seri hale getirme: seri hale getirme vs. Veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md).  
  
 Yapmak isteyebilirsiniz çerçevesini destekleyen birçok kullanıcı arabirimi fırsatından kullanın. Örneğin, birden çok kullanabilirsiniz `CRecordView` Bölümlendirici penceresinde açık nesneleri birden çok kayıt kümeleri farklı birden çok belge arabirimi (MDI) alt pencereleri ve benzeri.  
  
 Görünümünüzde ne olursa olsun, yazdırma uygulamak isteyebilirsiniz, bunun bir form ile uygulanan `CRecordView` veya başka bir şey. Türetilmiş sınıflar olarak `CFormView`, `CRecordView` yazdırma desteklemiyor, ancak geçersiz kılabilirsiniz mu `OnPrint` yazdırma izin verecek şekilde üye işlevi. Daha fazla bilgi için bkz [Cformview'yu](../mfc/reference/cformview-class.md).  
  
 Belgeler ve görünümler tüm kullanılacak istemeyebilirsiniz. Bu durumda, bkz: [MFC: olmadan veritabanı sınıflarını belgeleri kullanarak ve görünümleri](../data/mfc-using-database-classes-without-documents-and-views.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC veritabanı sınıfları (.. / data/mfc-database-classes-odbc-and-dao.md)