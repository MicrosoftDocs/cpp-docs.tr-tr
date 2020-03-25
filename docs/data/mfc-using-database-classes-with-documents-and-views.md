---
title: 'MFC: Belgeler ve Görünümler ile Veritabanı Sınıflarını Kullanma'
ms.date: 11/04/2016
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
ms.openlocfilehash: e2b073b20b9518667b43c30e7ee3199a84a3ad38
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213388"
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC: Belgeler ve Görünümler ile Veritabanı Sınıflarını Kullanma

MFC veritabanı sınıflarını belge/görünüm mimarisi ile veya olmadan kullanabilirsiniz. Bu konu, belgeler ve görünümler ile çalışmayı vurgular. Şunları açıklar:

- Belgenizde ana görünüm olarak `CRecordView` nesnesini kullanarak [form tabanlı bir uygulama yazma](#_core_writing_a_form.2d.based_application) .

- [Belgeleriniz ve görünümlerinizin kayıt kümesi nesnelerini kullanma](#_core_using_recordsets_in_documents_and_views).

- [Diğer noktalar](#_core_other_factors).

Alternatifler için bkz. [MFC: belgeler ve görünümler olmadan veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-without-documents-and-views.md).

##  <a name="writing-a-form-based-application"></a><a name="_core_writing_a_form.2d.based_application"></a>Form tabanlı uygulama yazma

Birçok veri erişimi uygulaması formları temel alır. Kullanıcı arabirimi, kullanıcının verileri incelediği, girdiği veya düzenledikleri denetimleri içeren bir formdur. Uygulama formunuzu temel hale getirmek için `CRecordView`sınıfını kullanın. MFC Uygulama Sihirbazı 'Nı çalıştırdığınızda ve **veritabanı desteği** sayfasında **ODBC** istemci türü ' nü seçtiğinizde, proje görünüm sınıfı için `CRecordView` kullanır.

Form tabanlı uygulamada, her kayıt görünümü nesnesi bir `CRecordset` nesnesine bir işaretçi depolar. Framework 'ün kayıt alanı değişimi (RFX) mekanizması, verileri kayıt kümesi ve veri kaynağı arasında değiş tokuş eder. İletişim kutusu veri değişimi (DDX) mekanizması, verileri kayıt kümesi nesnesinin alan veri üyeleri ve formdaki denetimler arasında değiş tokuş eder. `CRecordView`, formdaki kayda gitmek için varsayılan komut işleyici işlevlerini de sağlar.

Uygulama Sihirbazıyla form tabanlı bir uygulama oluşturmak için bkz. [form tabanlı MFC uygulaması](../mfc/reference/creating-a-forms-based-mfc-application.md) ve [VERITABANı desteği, MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md)oluşturma.

Form hakkında tam bir açıklama için bkz. [Kayıt görünümleri](../data/record-views-mfc-data-access.md).

##  <a name="using-recordsets-in-documents-and-views"></a><a name="_core_using_recordsets_in_documents_and_views"></a>Belgeler ve görünümlerde kayıt kümelerini kullanma

Birçok basit form tabanlı uygulama için belge gerekmez. Uygulamanız daha karmaşıksa, muhtemelen veri kaynağına bağlanan `CDatabase` nesnesini depolayarak veritabanı için bir ara sunucu olarak kullanmak isteyeceksiniz. Form tabanlı uygulamalar genellikle görünümdeki bir kayıt kümesi nesnesine bir işaretçi depolar. Diğer veritabanı uygulamaları türleri, kayıt kümelerini ve `CDatabase` nesneyi belgede depolar. Veritabanı uygulamalarında belgeleri kullanmaya yönelik bazı olanaklar aşağıda verilmiştir:

- Yerel bağlamdaki bir kayıt kümesine erişiyorsanız, gerektiğinde belgenin veya görünümün üye işlevlerinde yerel olarak bir `CRecordset` nesnesi oluşturun.

   Bir işlevde yerel değişken olarak bir kayıt kümesi nesnesi bildirin. Oluşturucuya NULL geçirin ve bu, çerçevenin sizin için geçici bir `CDatabase` nesne oluşturmasına ve açmasına neden olur. Alternatif olarak, bir `CDatabase` nesnesine bir işaretçi geçirin. İşlev içindeki kayıt kümesini kullanın ve işlev çıktığında otomatik olarak yok edilebilmesine izin verin.

   NULL değeri bir kayıt kümesi oluşturucusuna geçirdiğinizde, çerçeve, bir `CDatabase` nesnesi oluşturmak ve açmak için kayıt kümesinin `GetDefaultConnect` üye işlevi tarafından döndürülen bilgileri kullanır. Sihirbazlar sizin için `GetDefaultConnect` uygular.

- Belgenizin ömrü boyunca bir kayıt kümesine erişiyorsanız, belgenizde bir veya daha fazla `CRecordset` nesne ekleyin.

   Belgeyi başlattığınızda ya da gerektiğinde kayıt kümesi nesneleri oluşturun. Zaten varsa kayıt kümesine bir işaretçi döndüren bir işlev yazabilir veya henüz yoksa kayıt kümesini oluşturur ve açar. Kayıt kümesini gerektiği gibi kapatın, silin ve yeniden oluşturun veya kayıtları yenilemek için `Requery` member işlevini çağırın.

- Belgenizin ömrü boyunca bir veri kaynağına erişiyorsanız, bir `CDatabase` nesnesi katıştırın veya bir işaretçi içindeki bir `CDatabase` nesnesine depolayın.

   `CDatabase` nesnesi, veri kaynağınıza bir bağlantı yönetir. Nesne, belge oluşturma sırasında otomatik olarak oluşturulur ve belgeyi başlatırken `Open` üye işlevini çağırabilirsiniz. Belge üye işlevlerinde kayıt kümesi nesneleri oluşturduğunuzda, belgenin `CDatabase` nesnesine bir işaretçi geçirirsiniz. Bu, her bir kayıt kümesini veri kaynağıyla ilişkilendirir. Veritabanı nesnesi genellikle belge kapandığında yok edilir. Kayıt kümesi nesneleri, bir işlevin kapsamından çıkarken genellikle yok edilir.

##  <a name="other-factors"></a><a name="_core_other_factors"></a>Diğer faktörler

Form tabanlı uygulamalar genellikle Framework 'ün belge serileştirme mekanizması için herhangi bir kullanıma sahip değildir, bu nedenle **Dosya** menüsündeki **Yeni** ve **Açık** komutları kaldırmak, devre dışı bırakmak veya değiştirmek isteyebilirsiniz. [Serileştirme: serileştirme Ile veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md)makalesini inceleyin.

Ayrıca, Framework 'ün destekleyebileceği birçok kullanıcı arabirimi olasılıklarını da kullanmak isteyebilirsiniz. Örneğin, bir bölücü penceresinde birden çok `CRecordView` nesnesi kullanabilir, birden çok kayıt kümelerini farklı birden çok belge arabirimi (MDI) alt penceresinde açabilir ve bu şekilde devam edebilirsiniz.

`CRecordView` veya başka bir şey ile uygulanmış bir form olup olmadığı görünüminizdeki her şeyi yazdırmayı uygulamak isteyebilirsiniz. `CFormView`türetilen sınıflar, `CRecordView` yazdırmayı desteklemez, ancak yazdırmaya izin vermek için `OnPrint` üye işlevini geçersiz kılabilirsiniz. Daha fazla bilgi için bkz. sınıf [CFormView](../mfc/reference/cformview-class.md).

Belge ve görünümleri hiç kullanmak istememeyebilirsiniz. Bu durumda, bkz. [MFC: belgeler ve görünümler olmadan veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-without-documents-and-views.md).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Veritabanı Sınıfları](../data/mfc-database-classes-odbc-and-dao.md)
