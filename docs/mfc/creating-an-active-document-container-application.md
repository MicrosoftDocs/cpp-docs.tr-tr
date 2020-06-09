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
ms.openlocfilehash: 860a8531a96a0671c808dba13523b492026eafe0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616349"
---
# <a name="creating-an-active-document-container-application"></a>Etkin Belge Kapsayıcı Uygulaması Oluşturma

Etkin bir belge kapsayıcısı uygulaması oluşturmanın en basit ve en kolay yolu, MFC Uygulama Sihirbazı 'Nı kullanarak bir MFC EXE kapsayıcı uygulaması oluşturmaktır, ardından uygulamayı etkin belge kapsamayı destekleyecek şekilde değiştirmektir.

#### <a name="to-create-an-active-document-container-application"></a>Etkin bir belge kapsayıcısı uygulaması oluşturmak için

1. **Dosya** menüsünde, **Yeni** alt menüden **Proje**' ye tıklayın.

1. Sol bölmeden **Visual C++** proje türü ' ne tıklayın.

1. Sağ bölmeden **MFC uygulaması** ' nı seçin.

1. Projeyi *myproj*olarak adlandırın, **Tamam**' a tıklayın.

1. **Birleşik belge desteği** sayfasını seçin.

1. **Kapsayıcı** veya **kapsayıcı/tam sunucu** seçeneğini belirleyin.

1. **Etkin belge kapsayıcısı** onay kutusunu seçin.

1. **Son**'a tıklayın.

1. MFC Uygulama Sihirbazı uygulamayı oluşturmayı bitirdiğinde aşağıdaki dosyaları Çözüm Gezgini kullanarak açın:

   - *MyProjview. cpp*

1. *MyProjview. cpp*içinde aşağıdaki değişiklikleri yapın:

   - İçinde `CMyProjView::OnPreparePrinting` , işlev içeriğini şu kodla değiştirin:

     [!code-cpp[NVC_MFCDocView#56](codesnippet/cpp/creating-an-active-document-container-application_1.cpp)]

   `OnPreparePrinting`yazdırma desteği sağlar. Bu kod `DoPreparePrinting` , varsayılan yazdırma hazırlığı olan ' nin yerini alır.

   Etkin belge kapsama, gelişmiş bir yazdırma düzeni sağlar:

   - İlk olarak etkin belgeyi `IPrint` arabiriminden çağırıp kendisini yazdırmasını söyleyebilirsiniz. Bu, kapsayıcının içerilen öğenin bir görüntüsünü yazıcı nesnesi üzerinde işlemesi gereken önceki OLE kapsamadan farklıdır `CDC` .

   - Bu başarısız olursa, içerilen öğenin kendi arabirimi aracılığıyla kendisini yazdırmasını söyleyin `IOleCommandTarget`

   - Başarısız olursa, öğenin kendi işlemesini yapın.

   Statik üye işlevleri `COleDocObjectItem::OnPrint` ve `COleDocObjectItem::OnPreparePrinting` Önceki kodda uygulandığı gibi bu gelişmiş yazdırma düzenini işler.

1. Kendi uygulamasını ekleyin ve uygulamayı derleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Etkin belge kapsama](active-document-containment.md)
