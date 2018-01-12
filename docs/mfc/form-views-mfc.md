---
title: "Form görünümleri (MFC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- user interfaces [MFC], forms
- forms [MFC]
- applications [MFC], forms-based
- forms-based applications [MFC]
- forms [MFC], adding to applications
ms.assetid: efbe73c1-4ca4-4613-aac2-30d916e92c0e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e784858c17c01c8a538edebdb15a89863d16438
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="form-views-mfc"></a>Form Görünümleri (MFC)
Formlar dahil olmak üzere MFC kitaplıkları destekleyen Visual C++ uygulamasını ekleyebilirsiniz bir [forms tabanlı uygulama](../mfc/reference/creating-a-forms-based-mfc-application.md) (biri olan Görünüm sınıfı türetilir `CFormView`). Forms desteklemek için uygulamanızın başlangıçta oluşturmadıysanız, Visual C++ yeni bir form eklediğinizde, bu desteği ekler. SDI veya MDI bir uygulamada varsayılan uygulayan [belge/görünüm mimarisi](../mfc/document-view-architecture.md), kullanıcı seçtiğinde `New` komutu (varsayılan olarak, üzerinde **dosya** menüsü), Visual C++ kullanıcıya sorar kullanılabilir formlardan seçin.  
  
 Kullanıcı seçtiğinde bir uygulamayla SDI, `New` komutu, formun geçerli örneği çalışmaya devam eder ancak biri bulunamazsa, seçili form uygulamayla yeni bir örneğini oluşturulur. MDI uygulamada formu geçerli örneği kullanıcı seçtiğinde çalıştırmaya devam `New` komutu.  
  
> [!NOTE]
>  Form iletişim tabanlı bir uygulamaya ekleyebilirsiniz (iletişim kutusu sınıfı, temel bir `CDialog` ve hangi hiçbir görünümünde sınıfı uygulanır). Ancak, belge/görünüm mimarisinin Visual C++ otomatik olarak uygulamayan **dosya**&#124; **Yeni** işlevselliği. Kullanıcının çeşitli özellik sayfaları sekmeli iletişim kutusuyla uygulayarak gibi başka biçimlerde görüntülemek bir yol oluşturmanız gerekir.  
  
 Yeni bir form uygulamanıza eklediğinizde, Visual C++ şunları yapar:  
  
-   Seçtiğiniz form Stil sınıfları birini temel alan bir sınıf oluşturur (`CFormView`, `CRecordView`, `CDaoRecordView`, veya `CDialog`).  
  
-   Bir iletişim kutusu kaynağı uygun stilleri ile oluşturur (veya henüz bir sınıf ile ilişkilendirilmemiş var olan bir iletişim kutusu kaynağı kullanabilirsiniz).  
  
     Varolan bir iletişim kutusu kaynağı seçerseniz, bu stiller iletişim kutusu için Özellikler sayfasını kullanarak ayarlamanız gerekebilir. Bir iletişim kutusu stilleri şunları içermelidir:  
  
     **WS_CHILD**= açık  
  
     `WS_BORDER`= Off  
  
     **Ws_vısıble**= kapalı  
  
     **Ws_captıon =**devre dışı  
  
 Belge/görünüm mimarisine bağlı uygulamalar için **yeni bir Form** komutu (sağ tıklatma Sınıf Görünümü'nde) de:  
  
-   Oluşturur bir **CDocument**-temel sınıfı  
  
     Oluşturulan yeni bir sınıf sahip olmak yerine var olan kullanabilirsiniz **CDocument**-projenizdeki sınıfı tabanlı.  
  
-   Belge şablonu oluşturur (türetilmiş **CDocument**) dizesi, menü ve simge kaynaklara sahip.  
  
     Yeni bir sınıf şablona bağlanacağı de oluşturabilirsiniz.  
  
-   Çağrı ekler **AddDocumentTemplate** , uygulamanızın içinde `InitInstance` kodu.  
  
     Visual C++ ekler kullanıcı seçtiğinde, formun kullanılabilir Formlar listesine ekler oluşturduğunuz her yeni form için bu kodu `New` komutu. Bu kod formun ilişkili kaynak kimliği ile ilişkili belge, Görünüm ve birlikte yeni form nesnesi olun çerçeve sınıfları adlarını içerir.  
  
     Belge şablonları belgeler, çerçeve pencereler ve görünümler arasındaki bağlantıyı işlevini görür. Tek bir belge için birçok şablonu oluşturabilirsiniz.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Form tabanlı bir uygulama oluşturma](../mfc/reference/creating-a-forms-based-mfc-application.md)  
  
-   [Bir Projeye Form Ekleme](../mfc/inserting-a-form-into-a-project.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
