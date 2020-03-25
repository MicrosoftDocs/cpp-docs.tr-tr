---
title: Web Tarayıcısı Stilinde MFC Uygulaması Oluşturma
ms.date: 06/25/2018
f1_keywords:
- vc.appwiz.mfcweb.project
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications [MFC], creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
ms.openlocfilehash: e02e928f65ab4cd918e730135abc62ed3237decf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215130"
---
# <a name="creating-a-web-browser-style-mfc-application"></a>Web Tarayıcısı Stilinde MFC Uygulaması Oluşturma

Web tarayıcı stili bir uygulama, Internet 'ten (HTML veya etkin belgeler) veya bir intranet 'e ait bilgilere ve yerel dosya sisteminde ve bir ağdaki klasörlere erişebilir. Uygulamanın görünüm sınıfını [CHtmlView](../../mfc/reference/chtmlview-class.md)öğesinden türeterek, uygulamayı WebBrowser denetimiyle görünümü sağlayarak bir Web tarayıcısı olarak yaparsınız.

## <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>MFC belge/görünüm mimarisine dayalı bir Web tarayıcı uygulaması oluşturmak için

1. [MFC uygulaması oluşturma](../../mfc/reference/creating-an-mfc-application.md)yönergelerini izleyin.

1. MFC Uygulama Sihirbazı [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında, **belge/görünüm mimarisi** kutusunun seçili olduğundan emin olun. ( **Tek belge** veya **birden çok belge**seçebilirsiniz, ancak **iletişim temelli**değildir.)

1. [Oluşturulan sınıfları gözden geçir](../../mfc/reference/generated-classes-mfc-application-wizard.md) sayfasında, `CHtmlView`seçmek için **temel sınıf** açılan menüsünü kullanın.

1. Çatı uygulamasına yerleşik olarak kullanmak istediğiniz diğer seçenekleri seçin.

1. **Finish (Son)** düğmesine tıklayın.

WebBrowser denetimi köprüler ve Tekdüzen Kaynak Bulucu (URL) gezintisi aracılığıyla Web 'e gözatmayı destekler. Denetim, kullanıcının önceden gözatılan siteler, klasörler ve belgeler boyunca İleri ve geri göz atmasına izin veren bir geçmiş listesi tutar. Denetim doğrudan gezinti, köprüler, geçmiş listeleri, Sık Kullanılanlar ve güvenlik ' i işler. Uygulamalar, etkin belgeleri de barındırmak için WebBrowser denetimini etkin bir belge kapsayıcısı olarak kullanabilir. Bu nedenle, Microsoft Excel elektronik tabloları veya Word belgeleri gibi zengin biçimli belgeler, WebBrowser denetimi içinden yerinde açılabilir ve düzenlenebilir. WebBrowser denetimi aynı zamanda herhangi bir ActiveX denetimini barındırasağlayan bir ActiveX denetim kapsayıcısıdır.

> [!NOTE]
> WebBrowser ActiveX denetimi (ve bu nedenle `CHtmlView`) yalnızca Internet Explorer 4,0 veya sonraki bir sürümünün yüklendiği Windows sürümleri altında çalışan uygulamalarda kullanılabilir.

`CHtmlView` yalnızca Microsoft Web tarayıcısı denetimini uyguladığından, yazdırma desteği diğer [CView](../../mfc/reference/cview-class.md)ile türetilmiş sınıflar gibi değildir. Bunun yerine, WebBrowser denetimi Yazıcı Kullanıcı arabirimini ve yazdırmayı uygular. Sonuç olarak, `CHtmlView` baskı önizlemeyi desteklemez ve Framework diğer yazdırma desteği işlevlerini sağlamaz: Örneğin, [CView:: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting), [CView:: OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)ve [CView](../../mfc/reference/cview-class.md#onendprinting):: OnEndPrinting, diğer MFC uygulamalarında kullanılabilir.

`CHtmlView` Web tarayıcısı denetimi için bir sarmalayıcı işlevi görür. Bu, uygulamanıza bir Web veya HTML sayfası üzerinde bir görünüm sağlar. Sihirbaz, Microsoft Visual C++ Web sitesine gezinti bağlantısı sağlayan görünüm sınıfındaki [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) işlevinde bir geçersiz kılma oluşturur:

```cpp
void CWebView::OnInitialUpdate()
{
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.
    Navigate2(_T("http://www.docs.microsoft.com/"),
        NULL,
        NULL);
}
```

Bu siteyi kendi kendinize değiştirebilir veya [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource) üye işlevini, projenin kaynak komut dosyasında görünüm için varsayılan içerik olarak bulunan bir HTML sayfasını açmak için kullanabilirsiniz. Örneğin:

```cpp
void CWebView::OnInitialUpdate()
{
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.
    LoadFromResource(IDR_HTML1);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek MFCıE](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/internet)<br/>
[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)<br/>
[Derleyici ve derleme özelliklerini ayarlama](../../build/working-with-project-properties.md)<br/>
[Özellik Sayfaları](../../build/reference/property-pages-visual-cpp.md)<br/>
[Derleyici ve derleme özelliklerini ayarlama](../../build/working-with-project-properties.md)
