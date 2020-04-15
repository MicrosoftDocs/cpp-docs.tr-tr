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
ms.openlocfilehash: 9e071e0cc25492073cd74ed517284476b6e49ef8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368899"
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC: Belgeler ve Görünümler ile Veritabanı Sınıflarını Kullanma

Belge/görünüm mimarisi olan veya olmayan MFC veritabanı sınıflarını kullanabilirsiniz. Bu konu, belgeler ve görünümlerle çalışmayı vurgular. Bu açıklar:

- Belgenizdeki ana görünüm olarak bir `CRecordView` nesneyi kullanarak form tabanlı [bir uygulama nasıl yazılır.](#_core_writing_a_form.2d.based_application)

- [Belge ve görünümlerinizde kayıt kümesi nesneleri nasıl kullanılır.](#_core_using_recordsets_in_documents_and_views)

- [Diğer hususlar](#_core_other_factors).

Alternatifler için [MFC: Belge ve Görünümler Olmadan Veritabanı Sınıflarını Kullanma'](../data/mfc-using-database-classes-without-documents-and-views.md)ya bakın.

## <a name="writing-a-form-based-application"></a><a name="_core_writing_a_form.2d.based_application"></a>Form Tabanlı Başvuru Yazma

Birçok veri erişim uygulaması formları temel adamaktadır. Kullanıcı arabirimi, kullanıcının verileri incelediği, girdiği veya verileri oluşturduğu denetimleri içeren bir formdur. Başvuru formunuzu temel almak `CRecordView`için sınıfı kullanın. MFC Uygulama Sihirbazı'nı çalıştırdığınızda ve **Veritabanı Desteği** sayfasında `CRecordView` **ODBC** istemci türünü seçtiğinizde, proje görünüm sınıfı için kullanır.

Form tabanlı bir uygulamada, her kayıt görünümü nesnesi bir `CRecordset` nesneye işaretçi depolar. Çerçevenin kayıt alanı değişimi (RFX) mekanizması, kayıt kümesi ve veri kaynağı arasında veri alışverişi. İletişim veri alışverişi (DDX) mekanizması, kayıt kümesi nesnesinin alan veri üyeleri ile formdaki denetimler arasında veri alışverişi kurar. `CRecordView`ayrıca, formda kayıttan kayda gezinmek için varsayılan komut işleyicisi işlevleri de sağlar.

Uygulama sihirbazı yla form tabanlı bir uygulama oluşturmak için [bkz.](../mfc/reference/creating-a-forms-based-mfc-application.md) [Database Support, MFC Application Wizard](../mfc/reference/database-support-mfc-application-wizard.md)

Formlar hakkında tam bir tartışma için [Bkz.](../data/record-views-mfc-data-access.md)

## <a name="using-recordsets-in-documents-and-views"></a><a name="_core_using_recordsets_in_documents_and_views"></a>Belgelerde ve Görünümlerde Kayıt Kümelerini Kullanma

Birçok basit form tabanlı uygulamanın belgeye ihtiyacı yoktur. Uygulamanız daha karmaşıksa, büyük olasılıkla veritabanı için bir proxy olarak `CDatabase` bir belge kullanmak ve veri kaynağına bağlanan bir nesne depolamak istiyorsunuz. Form tabanlı uygulamalar genellikle görünümde bir kayıt kümesi nesnesine bir işaretçi depolar. Diğer veritabanı uygulamaları türleri belgedeki `CDatabase` kayıt kümelerini ve nesneyi depolar. Veritabanı uygulamalarında belgeleri kullanmak için bazı olanaklar şunlardır:

- Bir kayıt kümesine yerel bir bağlamda erişiyorsanız, gerektiğinde belgenin veya görünümün üye işlevlerinde yerel olarak bir `CRecordset` nesne oluşturun.

   Bir işlevde kayıt kümesi nesnesi yerel bir değişken olarak bildirin. NULL'u, çerçevenin sizin için geçici `CDatabase` bir nesne oluşturmasına ve açmasına neden olan oluşturucuya geçirin. Alternatif olarak, bir `CDatabase` nesneye işaretçi geçirin. İşlev içindeki kayıt kümesini kullanın ve işlev çıktığında otomatik olarak yok olmasına izin verin.

   NULL'u bir kayıt kümesi oluşturucuya geçtiğinde, çerçeve bir `GetDefaultConnect` `CDatabase` nesne oluşturmak ve açmak için kayıt kümesinin üye işlevi tarafından döndürülen bilgileri kullanır. Sihirbazlar sizin `GetDefaultConnect` için uygular.

- Belgenizin ömrü boyunca bir kayıt kümesine erişiyorsanız, `CRecordset` belgenize bir veya daha fazla nesne gömün.

   Belgeyi baş harfe aldığınızda veya gerektiğinde kayıt kümesi nesnelerini oluşturun. Bir işaretçiyi zaten varsa veya oluşturuyorsa ve henüz yoksa kayıt kümesini açan bir işlev yazabilirsiniz. Kayıt kümesini gerektiği gibi kapatın, silin ve `Requery` yeniden oluşturun veya kayıtları yenilemek için üye işlevini arayın.

- Belgenizin ömrü boyunca bir veri kaynağına erişiyorsanız, bir `CDatabase` nesne gömün veya bir işaretçiyi içinde bir `CDatabase` nesneye depolayın.

   Nesne, `CDatabase` veri kaynağınızla olan bağlantıyı yönetir. Nesne belge yapımı sırasında otomatik olarak oluşturulur `Open` ve belgeyi başharfe aldığınızda üye işlevini çağırırsınız. Belge üye işlevlerinde kayıt kümesi nesneleri oluştursanız, belgenin `CDatabase` nesnesine bir işaretçi geçersiniz. Bu, her kayıt kümesini veri kaynağıyla ilişkilendirer. Veritabanı nesnesi genellikle belge kapandığında yok edilir. Kayıt kümesi nesneleri genellikle bir işlevin kapsamı dışında yok edilir.

## <a name="other-factors"></a><a name="_core_other_factors"></a>Diğer Faktörler

Form tabanlı uygulamalar genellikle çerçevenin belge serileştirme mekanizması için herhangi bir kullanıma sahip değildir, bu nedenle **Dosya** menüsündeki **Yeni** ve **Aç** komutlarını kaldırmak, devre dışı kakmak veya değiştirmek isteyebilirsiniz. [Makaleserialization bakınız: Serialization vs Veritabanı Giriş / Çıktı](../mfc/serialization-serialization-vs-database-input-output.md).

Ayrıca, çerçevenin destekleyebileceği birçok kullanıcı arabirimi olanaklarından da yararlanmak isteyebilirsiniz. Örneğin, bir bölücü `CRecordView` penceresinde birden çok nesne kullanabilirsiniz, farklı birden çok belge arabirimi (MDI) alt pencerelerinde birden çok kayıt kümesi açabilirsiniz, vb.

Görünümünüzde ne varsa, bu form la `CRecordView` birlikte uygulanan bir form veya başka bir şey olsun, yazdırma uygulamak isteyebilirsiniz. Türetilen `CFormView`sınıflar, `CRecordView` yazdırmayı desteklemez, ancak yazdırmaya izin vermek için `OnPrint` üye işlevi geçersiz kılabilirsiniz. Daha fazla bilgi için [CFormView](../mfc/reference/cformview-class.md)sınıfına bakın.

Belgeleri ve görünümleri hiç kullanmak istemeyebilirsiniz. Bu durumda, [Bkz. MFC: Belge ve Görünümler Olmadan Veritabanı Sınıfları kullanma.](../data/mfc-using-database-classes-without-documents-and-views.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Veritabanı Sınıfları](../data/mfc-database-classes-odbc-and-dao.md)
