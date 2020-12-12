---
description: 'Daha fazla bilgi edinin: MFC: belgeler ve görünümler ile veritabanı sınıflarını kullanma'
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
ms.openlocfilehash: 9742e180c8acab7e882cd31a94afec935a5ce21a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170873"
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC: Belgeler ve Görünümler ile Veritabanı Sınıflarını Kullanma

MFC veritabanı sınıflarını belge/görünüm mimarisi ile veya olmadan kullanabilirsiniz. Bu konu, belgeler ve görünümler ile çalışmayı vurgular. Şunları açıklar:

- Belgenizdeki ana görünüm olarak bir nesneyi kullanarak [form tabanlı bir uygulama yazma](#_core_writing_a_form.2d.based_application) `CRecordView` .

- [Belgeleriniz ve görünümlerinizin kayıt kümesi nesnelerini kullanma](#_core_using_recordsets_in_documents_and_views).

- [Diğer noktalar](#_core_other_factors).

Alternatifler için bkz. [MFC: belgeler ve görünümler olmadan veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-without-documents-and-views.md).

## <a name="writing-a-form-based-application"></a><a name="_core_writing_a_form.2d.based_application"></a> Form-Based uygulaması yazma

Birçok veri erişimi uygulaması formları temel alır. Kullanıcı arabirimi, kullanıcının verileri incelediği, girdiği veya düzenledikleri denetimleri içeren bir formdur. Uygulama formunuzu temel hale getirmek için sınıfı kullanın `CRecordView` . MFC Uygulama Sihirbazı 'Nı çalıştırdığınızda ve **veritabanı desteği** sayfasında **ODBC** istemci türü ' nü seçtiğinizde, proje `CRecordView` View sınıfı için kullanır.

Form tabanlı bir uygulamada, her kayıt görünümü nesnesi bir nesnenin işaretçisini depolar `CRecordset` . Framework 'ün kayıt alanı değişimi (RFX) mekanizması, verileri kayıt kümesi ve veri kaynağı arasında değiş tokuş eder. İletişim kutusu veri değişimi (DDX) mekanizması, verileri kayıt kümesi nesnesinin alan veri üyeleri ve formdaki denetimler arasında değiş tokuş eder. `CRecordView` Ayrıca, formdaki kayda gitmek için varsayılan komut işleyici işlevlerini sağlar.

Uygulama Sihirbazıyla form tabanlı bir uygulama oluşturmak için bkz. [Forms-Based MFC uygulaması](../mfc/reference/creating-a-forms-based-mfc-application.md) ve [VERITABANı desteği, MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md)oluşturma.

Form hakkında tam bir açıklama için bkz. [Kayıt görünümleri](../data/record-views-mfc-data-access.md).

## <a name="using-recordsets-in-documents-and-views"></a><a name="_core_using_recordsets_in_documents_and_views"></a> Belgeler ve görünümlerde kayıt kümelerini kullanma

Birçok basit form tabanlı uygulama için belge gerekmez. Uygulamanız daha karmaşıksa, büyük olasılıkla bir belgeyi veri kaynağına bağlanan bir nesneyi depolayarak veritabanı için bir proxy olarak kullanmak istersiniz `CDatabase` . Form tabanlı uygulamalar genellikle görünümdeki bir kayıt kümesi nesnesine bir işaretçi depolar. Diğer veritabanı uygulamaları türleri, kayıt kümelerini ve `CDatabase` nesneyi belgede depolar. Veritabanı uygulamalarında belgeleri kullanmaya yönelik bazı olanaklar aşağıda verilmiştir:

- Yerel bağlamdaki bir kayıt kümesine erişiyorsanız, `CRecordset` gerektiğinde belgenin veya görünümün üye işlevlerinde yerel olarak bir nesne oluşturun.

   Bir işlevde yerel değişken olarak bir kayıt kümesi nesnesi bildirin. Oluşturucuya NULL geçirin ve bu, çerçevenin sizin için geçici bir nesne oluşturmasına ve açmasına neden olur `CDatabase` . Alternatif olarak, bir nesnenin işaretçisini geçirin `CDatabase` . İşlev içindeki kayıt kümesini kullanın ve işlev çıktığında otomatik olarak yok edilebilmesine izin verin.

   Bir kayıt kümesi oluşturucusuna NULL geçirdiğinizde, çerçeve `GetDefaultConnect` bir nesne oluşturmak ve açmak için kayıt kümesinin üye işlevi tarafından döndürülen bilgileri kullanır `CDatabase` . Sihirbazlar `GetDefaultConnect` sizin için uygulanır.

- Belgenizin ömrü boyunca bir kayıt kümesine erişiyorsanız, belgenize bir veya daha fazla `CRecordset` nesne ekleyin.

   Belgeyi başlattığınızda ya da gerektiğinde kayıt kümesi nesneleri oluşturun. Zaten varsa kayıt kümesine bir işaretçi döndüren bir işlev yazabilir veya henüz yoksa kayıt kümesini oluşturur ve açar. Kayıt kümesini gerektiği gibi kapatın, silin ve yeniden oluşturun veya `Requery` kayıtları yenilemek için üye işlevini çağırın.

- Belgenizin ömrü boyunca bir veri kaynağına erişiyorsanız bir `CDatabase` nesne ekleyin veya bir işaretçi `CDatabase` içindeki bir nesneye depolayın.

   `CDatabase`Nesnesi, veri kaynağınıza bir bağlantı yönetir. Nesne, belge oluşturma sırasında otomatik olarak oluşturulur ve `Open` belgeyi başlattığınızda üye işlevini çağırabilirsiniz. Belge üye işlevlerinde kayıt kümesi nesneleri oluşturduğunuzda, belgenin nesnesine bir işaretçi geçirirsiniz `CDatabase` . Bu, her bir kayıt kümesini veri kaynağıyla ilişkilendirir. Veritabanı nesnesi genellikle belge kapandığında yok edilir. Kayıt kümesi nesneleri, bir işlevin kapsamından çıkarken genellikle yok edilir.

## <a name="other-factors"></a><a name="_core_other_factors"></a> Diğer faktörler

Form tabanlı uygulamalar genellikle Framework 'ün belge serileştirme mekanizması için herhangi bir kullanıma sahip değildir, bu nedenle **Dosya** menüsündeki **Yeni** ve **Açık** komutları kaldırmak, devre dışı bırakmak veya değiştirmek isteyebilirsiniz. [Serileştirme: serileştirme Ile veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md)makalesini inceleyin.

Ayrıca, Framework 'ün destekleyebileceği birçok kullanıcı arabirimi olasılıklarını da kullanmak isteyebilirsiniz. Örneğin, `CRecordView`  bir bölücü penceresinde birden çok nesne kullanabilirsiniz, birden çok kayıt kümelerini farklı birden çok belge arabirimi (MDI) alt penceresinde açabilir ve bu şekilde devam edebilirsiniz.

Görünümünüzde ne olduğunu, bir veya başka bir şekilde uygulanıp uygulanmadığını görüntülemek isteyebilirsiniz `CRecordView`  . ' Den türetilen sınıflar `CFormView` `CRecordView` yazdırmayı desteklemez, ancak `OnPrint` yazdırmaya izin vermek için üye işlevini geçersiz kılabilirsiniz. Daha fazla bilgi için bkz. sınıf [CFormView](../mfc/reference/cformview-class.md).

Belge ve görünümleri hiç kullanmak istememeyebilirsiniz. Bu durumda, bkz. [MFC: belgeler ve görünümler olmadan veritabanı sınıflarını kullanma](../data/mfc-using-database-classes-without-documents-and-views.md).

## <a name="see-also"></a>Ayrıca bkz.

[MFC veritabanı sınıfları](../data/mfc-database-classes-odbc-and-dao.md)
