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
ms.openlocfilehash: 94d8b7d026ee3aaf1bac9dee2226de6dd9382599
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615689"
---
# <a name="form-views-mfc"></a>Form Görünümleri (MFC)

[Form tabanlı uygulama](reference/creating-a-forms-based-mfc-application.md) (bir görünüm sınıfı öğesinden türetilir) dahil olmak üzere MFC kitaplıklarını destekleyen Visual C++ uygulamasına formlar ekleyebilirsiniz `CFormView` . Uygulamanızı ilk olarak formları destekleyecek şekilde oluşturmadıysanız, Visual C++ yeni bir form eklediğinizde bu desteği size ekler. Varsayılan [belge/görünüm mimarisini](document-view-architecture.md)uygulayan bir SDI veya MDI uygulamasında, Kullanıcı **Yeni** komutu seçtiğinde (varsayılan olarak, **Dosya** menüsünde), Visual C++ kullanıcıdan kullanılabilir formlardan seçim yapmanızı ister.

Bir SDI uygulamasıyla, Kullanıcı **Yeni** komutu seçtiğinde formun geçerli örneği çalışmaya devam eder, ancak bir tane bulunmazsa seçili form ile uygulamanın yeni bir örneği oluşturulur. MDI uygulamasında, Kullanıcı **Yeni** komutu seçtiğinde formun geçerli örneği çalışmaya devam eder.

> [!NOTE]
> İletişim kutusu tabanlı uygulamaya bir form ekleyebilirsiniz (iletişim sınıfı temel alan `CDialog` ve bir görünüm sınıfının uygulanmadığı bir tane). Ancak, belge/görünüm mimarisi olmadan Visual C++ **dosyayı**&#124;**Yeni** işlevselliği otomatik olarak uygulamaz. Farklı özellik sayfaları ile sekmeli bir iletişim kutusu uygulayarak, kullanıcının ek formları görüntülemesi için bir yol oluşturmanız gerekir.

Uygulamanıza yeni bir form eklediğinizde şunları Visual C++:

- Seçtiğiniz form stili sınıflardan birini (, `CFormView` `CRecordView` ,, `CDaoRecordView` veya `CDialog` ) temel alan bir sınıf oluşturur.

- Uygun stillerle bir iletişim kutusu kaynağı oluşturur (veya henüz bir sınıfla ilişkilendirilmemiş mevcut bir iletişim kutusu kaynağını kullanabilirsiniz).

   Mevcut bir iletişim kutusu kaynağını seçerseniz, iletişim kutusunun Özellikler sayfasını kullanarak bu stilleri ayarlamanız gerekebilir. Bir iletişim kutusu için stiller şunları içermelidir:

     **WS_CHILD**= açık

     **WS_BORDER**= kapalı

     **WS_VISIBLE**= kapalı

     **WS_CAPTION**= kapalı

Belge/görünüm mimarisine dayalı uygulamalar için **Yeni form** komutu (Sınıf Görünümü ' de sağ tıklayın) ayrıca:

- Tabanlı bir `CDocument` sınıf oluşturur

   Yeni bir sınıf oluşturulmasını yerine, projenizde var olan herhangi bir `CDocument` temel sınıfı kullanabilirsiniz.

- `CDocument`Dize, menü ve simge kaynaklarıyla bir belge şablonu (öğesinden türetilir) oluşturur.

   Ayrıca, şablonu temel alan yeni bir sınıf da oluşturabilirsiniz.

- Uygulamanızın kodunda bir çağrı ekler `AddDocumentTemplate` `InitInstance` .

   Visual C++ oluşturduğunuz her yeni form için bu kodu, Kullanıcı **Yeni** komutu seçtiğinde kullanılabilir formlar listesine ekler. Bu kod formun ilişkili kaynak KIMLIĞINI ve birlikte yeni form nesnesini oluşturan ilişkili belge, görünüm ve çerçeve sınıflarının adlarını içerir.

   Belge şablonları, belgeler, çerçeve pencereleri ve görünümler arasında bağlantı işlevi sunar. Tek bir belge için birçok şablon oluşturabilirsiniz.

Daha fazla bilgi için bkz.

- [Form tabanlı uygulama oluşturma](reference/creating-a-forms-based-mfc-application.md)

- [Projeye form ekleme](inserting-a-form-into-a-project.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](user-interface-elements-mfc.md)
