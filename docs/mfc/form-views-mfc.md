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
ms.openlocfilehash: f092b9eca0fe0b4af40a5e1f6e77d3a0f1af74b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655630"
---
# <a name="form-views-mfc"></a>Form Görünümleri (MFC)

Forms dahil olmak üzere MFC kitaplıkları destekleyen tüm Visual C++ uygulamasına ekleyebilirsiniz bir [forms tabanlı uygulama](../mfc/reference/creating-a-forms-based-mfc-application.md) (bir, görünüm sınıfı türetilen `CFormView`). Forms desteklemek üzere uygulamanızı başlangıçta oluşturmadıysanız, Visual C++, yeni bir form eklediğinizde bu desteğini ekler. Bir SDI veya MDI uygulamasında varsayılan uygulayan [belge/görünüm mimarisi](../mfc/document-view-architecture.md), kullanıcı seçtiğinde **yeni** komut (varsayılan olarak, üzerinde **dosya** menüsü), Visual C++ kullanılabilir formlardan seçmenizi ister.

Kullanıcı seçtiğinde bir SDI uygulaması ile **yeni** komutu, formun geçerli örneğini çalışmaya devam eder ancak biri bulunamazsa, seçili form uygulamasıyla yeni bir örneğini oluşturulur. Bir MDI uygulamasında, formun geçerli örneğini kullanıcı seçtiğinde çalışmaya devam **yeni** komutu.

> [!NOTE]
>  Bir formu bir iletişim kutusu tabanlı uygulamaya ekleyebilirsiniz (bir iletişim kutusu sınıfı, temel `CDialog` ve hangi hiçbir görünümünde sınıfı uygulanır). Ancak, belge/görünüm mimarisi Visual C++ otomatik olarak uygulamıyor **dosya**&#124;**yeni** işlevselliği. Kullanıcının, çeşitli özellik sayfaları sekmeli iletişim kutusuyla uygulayarak gibi başka biçimlerde görüntülemek bir yol oluşturmanız gerekir.

Yeni bir form uygulamanıza eklediğinizde, Visual C++ şunları yapar:

- Seçtiğiniz form-style sınıflarının biri üzerinde temel bir sınıf oluşturur (`CFormView`, `CRecordView`, `CDaoRecordView`, veya `CDialog`).

- Uygun stilleriyle bir iletişim kaynağı oluşturur (veya henüz bir sınıf ile ilişkilendirilmemiş mevcut bir iletişim kaynağı kullanabilirsiniz).

   Var olan bir iletişim kaynağı seçerseniz, iletişim kutusu için Özellikler sayfasını kullanarak bu stiller ayarlamak gerekebilir. Bir iletişim kutusu stilleri şunları içermelidir:

     **WS_CHILD**= açık

     **WS_BORDER**= kapalı

     **Ws_vısıble**= kapalı

     **Ws_captıon =** kapalı

Belge/görünüm mimarisini temel alan uygulamalar için **yeni formu** komut (Sınıf Görünümü'nde sağ tıklama) da:

- Oluşturur bir `CDocument`-temel sınıfı

   Oluşturulan yeni bir sınıf olması yerine var olan tüm kullanabilirsiniz `CDocument`-tabanlı projenizdeki sınıfı.

- Bir belge şablonu oluşturur (türetilen `CDocument`) dizesi, menü ve simge kaynaklara sahip.

   Yeni bir sınıf şablonunun temel de oluşturabilirsiniz.

- Bir çağrı ekler `AddDocumentTemplate` uygulamanızın `InitInstance` kod.

   Visual C++ için kullanıcı seçtiğinde, form kullanılabilir Formlar listesine ekler. oluşturduğunuz her yeni formu bu kodu ekler **yeni** komutu. Bu kod, formun ilişkili kaynak kimliği ile ilişkili belge, görünüm ile birlikte yeni form nesne olun çerçeve sınıfları adlarını içerir.

   Belge şablonları, belge çerçeve pencereleri ve görünümleri arasında bağlantı görür. Tek bir belge için birçok şablonu oluşturabilirsiniz.

Daha fazla bilgi için bkz.:

- [Form tabanlı bir uygulama oluşturma](../mfc/reference/creating-a-forms-based-mfc-application.md)

- [Bir Projeye Form Ekleme](../mfc/inserting-a-form-into-a-project.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
