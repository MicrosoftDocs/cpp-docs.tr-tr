---
title: Form Görünümleri (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces [MFC], forms
- forms [MFC]
- applications [MFC], forms-based
- forms-based applications [MFC]
- forms [MFC], adding to applications
ms.assetid: efbe73c1-4ca4-4613-aac2-30d916e92c0e
ms.openlocfilehash: 5e8912c9013175fe254b2f4a4a968a67fd071f39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365292"
---
# <a name="form-views-mfc"></a>Form Görünümleri (MFC)

[Form tabanlı](../mfc/reference/creating-a-forms-based-mfc-application.md) bir uygulama da dahil olmak üzere MFC kitaplıklarını destekleyen herhangi bir Visual C++ uygulamasına form ekleyebilirsiniz (görünüm sınıfı türetilmiş). `CFormView` Başlangıçta formları desteklemek için uygulamanızı oluşturmadıysanız, Visual C++ yeni bir form eklediğinizde bu desteği sizin için ekler. Kullanıcı **Yeni** komutu seçtiğinde (varsayılan olarak **Dosya** menüsünde) varsayılan [belge/görünüm mimarisini](../mfc/document-view-architecture.md)uygulayan bir SDI veya MDI uygulamasında, Visual C++ kullanıcıdan kullanılabilir formlardan seçim yapmalarını ister.

Bir SDI uygulamasıyla, kullanıcı **Yeni** komutu seçtiğinde, formun geçerli örneği çalıştırmaya devam eder, ancak bir tane bulunamazsa seçili formun bulunduğu yeni bir örnek oluşturulur. Bir MDI uygulamasında, kullanıcı **Yeni** komutu seçtiğinde formun geçerli örneği çalışmadevam eder.

> [!NOTE]
> Bir form iletişim tabanlı bir uygulamaya ekleyebilirsiniz (iletişim sınıfı temel `CDialog` alınan ve görünüm sınıfının uygulanmadığı bir uygulama). Ancak, belge/görünüm mimarisi olmadan Visual C++ **Dosya**&#124;**Yeni** işlevselliğini otomatik olarak uygulamaz. Kullanıcının, çeşitli özellik sayfaları içeren sekmeli bir iletişim kutusu uygulamak gibi ek formları görüntülemesi için bir yol oluşturmanız gerekir.

Uygulamanıza yeni bir form eklediğinizde, Visual C++ aşağıdakileri yapar:

- Seçtiğiniz form stili sınıflarından birine dayalı bir sınıf`CFormView`oluşturur `CRecordView` `CDaoRecordView`( `CDialog`, , , veya ).

- Uygun stillesahip bir iletişim kaynağı oluşturur (veya henüz bir sınıfla ilişkilendirilmemiş varolan bir iletişim kaynağı kullanabilirsiniz).

   Varolan bir iletişim kaynağı seçerseniz, iletişim kutusunun Özellikleri sayfasını kullanarak bu stilleri ayarlamanız gerekebilir. İletişim kutusunun stilleri şunları içermelidir:

     **WS_CHILD**=A)'ya

     **WS_BORDER**=Kapalı

     **WS_VISIBLE**=Kapalı

     **WS_CAPTION**=Kapalı

Belge/görünüm mimarisine dayalı uygulamalar için **Yeni Form** komutu (Sınıf Görünümünde sağ tıklatın) da:

- Tabanlı bir `CDocument`sınıf oluşturur

   Yeni bir sınıf oluşturulması yerine, projenizde `CDocument`varolan tabanlı herhangi bir sınıfı kullanabilirsiniz.

- Dize, menü ve `CDocument`simge kaynaklarına sahip bir belge şablonu (türetilmiş) oluşturur.

   Ayrıca şablonu temel almak için yeni bir sınıf oluşturabilirsiniz.

- Uygulamanızın `AddDocumentTemplate` `InitInstance` koduna bir arama ekler.

   Visual C++ oluşturduğunuz her yeni form için bu kodu ekler ve kullanıcı **Yeni** komutu seçtiğinde formu kullanılabilir formlar listesine ekler. Bu kod, formun ilişkili kaynak kimliğini ve yeni form nesnesini birlikte oluşturan ilişkili belge, görünüm ve çerçeve sınıflarının adlarını içerir.

   Belge şablonları belgeler, çerçeve pencereleri ve görünümler arasında bağlantı görevi görüyor. Tek bir belge için birçok şablon oluşturabilirsiniz.

Daha fazla bilgi için bkz.

- [Form Tabanlı Uygulama Oluşturma](../mfc/reference/creating-a-forms-based-mfc-application.md)

- [Projeye Form Ekleme](../mfc/inserting-a-form-into-a-project.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı Arabirimi Elemanları](../mfc/user-interface-elements-mfc.md)
