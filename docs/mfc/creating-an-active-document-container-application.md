---
title: Etkin Belge Kapsayıcı Uygulaması Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- active document containers [MFC], creating
- MFC COM, active document containment
- applications [MFC], active document container
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
ms.openlocfilehash: 965778fd5d17aa416b198c101edc3a445a39580b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152949"
---
# <a name="creating-an-active-document-container-application"></a>Etkin Belge Kapsayıcı Uygulaması Oluşturma

Etkin belge kapsayıcı uygulaması oluşturmanın en kolay ve en çok önerilen yolu MFC Uygulama Sihirbazı'nı kullanarak bir MFC EXE kapsayıcı uygulaması oluşturmak için ardından etkin belge kapsaması destekleyecek şekilde değiştirin.

#### <a name="to-create-an-active-document-container-application"></a>Etkin belge kapsayıcı uygulaması oluşturma

1. Gelen **dosya** menüsünde tıklatın **proje**gelen **yeni** alt.

1. Sol bölmeden tıklayın **Visual C++** proje türü.

1. Seçin **MFC uygulaması** sağ bölmesinde.

1. Projeyi adlandırın *MyProj*, tıklayın **Tamam**.

1. Seçin **bileşik belge desteği** sayfası.

1. Seçin **kapsayıcı** veya **kapsayıcı/tam sunucu** seçeneği.

1. Seçin **etkin belge kapsayıcı** onay kutusu.

1. **Son**'a tıklayın.

1. MFC Uygulama Sihirbazı uygulama ürettikten sonra Çözüm Gezgini'ni kullanarak aşağıdaki dosyaları açın:

   - *MyProjview.cpp*

1. İçinde *MyProjview.cpp*, aşağıdaki değişiklikleri yapın:

   - İçinde `CMyProjView::OnPreparePrinting`, işlev içeriğini aşağıdaki kodla değiştirin:

     [!code-cpp[NVC_MFCDocView#56](../mfc/codesnippet/cpp/creating-an-active-document-container-application_1.cpp)]

   `OnPreparePrinting` yazdırma desteği sağlar. Bu kodu değiştirir `DoPreparePrinting`, varsayılan yazdırma hazırlık olduğu.

   Etkin belge kapsaması geliştirilmiş bir yazdırma düzeni sağlar:

   - Etkin belgeyi ile ilk çağırabilirsiniz kendi `IPrint` arabirim ve, IOleCommandTarget komutunu söyleyin. Bu, kapsayıcı olan bir yazıcı üzerine kapsanan öğesinin görüntüsünü işlemek önceki OLE kapsayıcı farklıdır `CDC` nesne.

   - Başarısız olursa, kendisi aracılığıyla yazdırmak için kapsanan öğe bildirmek, `IOleCommandTarget` arabirimi

   - Bu başarısız olursa, öğenin kendi işleme olun.

   Statik üye işlevleri `COleDocObjectItem::OnPrint` ve `COleDocObjectItem::OnPreparePrinting`, önceki kod içinde uygulandığı şekilde bu geliştirilmiş yazdırma düzeni tanıtıcı.

1. Herhangi bir uygulamasını ekleyin ve uygulamayı derleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Etkin Belge Kapsaması](../mfc/active-document-containment.md)
