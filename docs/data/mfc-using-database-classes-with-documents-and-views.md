---
title: 'MFC: Belgeler ve görünümler ile veritabanı sınıflarını kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 527de152f7eea9e71cb38a9ca2f51e15803df337
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337053"
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC: Belgeler ve Görünümler ile Veritabanı Sınıflarını Kullanma
MFC veritabanı sınıfları ile veya olmadan belge/görünüm mimarisinin kullanabilirsiniz. Bu konuda, belgeler ve görünümler ile çalışma vurgular. Açıklar:  
  
-   [Form tabanlı bir uygulama yazmak nasıl](#_core_writing_a_form.2d.based_application) kullanarak bir `CRecordView` belgenizin ana görünümünde olarak nesnesi.  
  
-   [Kayıt kümesi nesneleri belgeleri ve görünümleri kullanma](#_core_using_recordsets_in_documents_and_views).  
  
-   [Dikkat edilecek diğer noktalar](#_core_other_factors).  
  
 Alternatifleri için bkz: [MFC: olmadan veritabanı sınıflarını belgeleri kullanarak ve görünümleri](../data/mfc-using-database-classes-without-documents-and-views.md).  
  
##  <a name="_core_writing_a_form.2d.based_application"></a> Form tabanlı bir uygulama yazma  
 Birçok veri erişimi uygulamaları formlarını temel alır. Kullanıcı arabirimi, kullanıcı inceler, girer veya veri düzenler denetimleri içeren bir biçimidir. Uygulamanızı form temelli, sınıf yapma `CRecordView`. MFC Uygulama Sihirbazı'nı çalıştırın ve seçin, **ODBC** istemci türüne **veritabanı desteği** kullanan sayfası, proje `CRecordView` görünüm sınıfı için.
  
 Form tabanlı bir uygulama, her kayıt görünümü nesne yönelik bir işaretçi depolayan bir `CRecordset` nesne. Framework'ün kayıt alanı değişimi (RFX) mekanizmasını kayıt kümesi ve veri kaynağı arasında veri birbiriyle değiştirir. İletişim kutusu veri değişimi (DDX) mekanizmasını kayıt kümesi nesnesi alan veri üyeleri ve form üzerinde denetimleri arasında veri yapar. `CRecordView` Ayrıca varsayılan kayıt kaydı formda gezinme için komut işleyici işlevleri sağlar.  
  
 Uygulama Sihirbazı'nı form tabanlı bir uygulama oluşturmak için bkz [bir form tabanlı MFC uygulaması oluşturma](../mfc/reference/creating-a-forms-based-mfc-application.md) ve [veritabanı desteği, MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md).  
  
 Forms tam bir irdelemesi için bkz: [kayıt görünümleri](../data/record-views-mfc-data-access.md).  
  
##  <a name="_core_using_recordsets_in_documents_and_views"></a> Kayıt kümeleri içinde belgeleri ve görünümleri kullanma  
 Çok basit form tabanlı uygulamalar belgeleri gerekmez. Uygulamanız, büyük olasılıkla istediğiniz bir belge veritabanı için bir proxy olarak kullanmak daha karmaşık ise, depolama bir `CDatabase` nesnesini, veri kaynağına bağlanır. Form tabanlı uygulamalar, genellikle Görünümü'nde bir kayıt nesnesine bir işaretçi depolar. Diğer tür veritabanı uygulamaları kayıt kümelerini depolamak ve `CDatabase` belge nesnesi. Belge veritabanı uygulamalarında kullanma bazı seçenekler şunlardır:  
  
-   Yerel bir bağlamda kayıt sağlıyorsanız, oluşturun bir `CRecordset` nesne yerel belge veya görünümün üye işlevlerde gerektiğinde.  
  
     Bir kayıt kümesi nesnesi, bir işlev yerel bir değişken olarak bildirin. Oluşturma ve geçici bir açık çerçeve neden oluşturucuya NULL geçirin `CDatabase` nesnesi. Alternatif olarak, geçirmek için bir işaretçi bir `CDatabase` nesne. Kayıt kümesi işlev içinde kullanmak ve bu işlev otomatik olarak yok izin verin.  
  
     Bir kayıt kümesi oluşturucuya NULL başarıyla sonuçlandıktan sonra çerçeve kümesinin tarafından döndürülen bilgileri kullanır. `GetDefaultConnect` üye işlevi bir `CDatabase` nesne ve açın. Uygulama sihirbazları `GetDefaultConnect` sizin için.  
  
-   Bir kayıt kümesi belgenizi ömrü boyunca erişiyorsanız, bir veya daha fazla ekleme `CRecordset` belgenizdeki nesneleri.  
  
     Kayıt kümesi nesneleri belge başlattığınızda veya gerektiği gibi oluşturun. Zaten var veya oluşturur ve henüz yoksa kayıt açar, kayıt kümesine bir işaretçi döndüren bir işlev yazabilirsiniz. Kapatın, silin ve kayıt gerektiği gibi yeniden oluşturun veya çağrı kendi `Requery` kayıtları yenilemek için üye işlevi.  
  
-   Bir veri kaynağını belgenizin ömrü boyunca erişiyorsanız, ekleme bir `CDatabase` nesne veya depolamak için bir işaretçi bir `CDatabase` nesnesine.  
  
     `CDatabase` Nesne veri kaynağı bağlantısı yönetir. Nesne belge oluşturma sırasında otomatik olarak oluşturulur ve çağırmanızı kendi `Open` belge başlattığınızda üye işlevi. Kayıt kümesi nesneleri belge üye işlevlerinde oluştururken, belgenin bir işaretçi geçirmek `CDatabase` nesne. Bu, her bir kayıt kümesi kendi veri kaynağı ile ilişkilendirir. Belge kapatıldığında veritabanı nesnesi genellikle yok edilir. Kayıt kümesi nesneleri genellikle, bir işlevin kapsamı çıktığınızda yok edilir.  
  
##  <a name="_core_other_factors"></a> Diğer faktörler  
 Form tabanlı uygulamalar genellikle yok kullanım framework'ün belge serileştirme mekanizması, kaldırma, devre dışı bırakın ya da değiştirmek isteyebilirsiniz **yeni** ve **açık** komutları**Dosya** menüsü. Makaleye göz atın [seri hale getirme: seri hale getirme vs. Veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md).  
  
 Yapmak isteyebilirsiniz, framework destekleyen çok sayıda kullanıcı arabirimi olasılıklarını kullanın. Örneğin, birden çok kullanabilirsiniz `CRecordView` içinde bir ayırıcı penceresi açık nesneleri birden çok kayıt kümeleri farklı birden çok belge arabirimi (MDI) alt pencereleri ve benzeri.  
  
 Görünümde ne olursa olsun, yazdırma uygulamak isteyebilirsiniz, bunun bir form ile uygulanan `CRecordView` veya başka bir şey. Öğesinden türetilmiş sınıflar olarak `CFormView`, `CRecordView` yazdırma desteklemiyor, ancak geçersiz kılabilirsiniz mu `OnPrint` yazdırma izin verecek şekilde üye işlevi. Daha fazla bilgi için bkz. [CFormView](../mfc/reference/cformview-class.md).  
  
 Belgeler ve görünümler tüm kullanılacak istemeyebilirsiniz. Bu durumda bkz [MFC: olmadan veritabanı sınıflarını belgeleri kullanarak ve görünümleri](../data/mfc-using-database-classes-without-documents-and-views.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC veritabanı sınıfları (.. / data/mfc-database-classes-odbc-and-dao.md)