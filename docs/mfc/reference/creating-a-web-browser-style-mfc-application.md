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
ms.openlocfilehash: 207a6e162da6bc14e27c575ac163b160ab8e1ac1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265603"
---
# <a name="creating-a-web-browser-style-mfc-application"></a>Web Tarayıcısı Stilinde MFC Uygulaması Oluşturma

Bir Web tarayıcısı stilinde uygulaması bilgilere (örneğin, HTML veya etkin belgeler) Internet veya intranet, yanı klasör yerel dosya sistemi ve ağ üzerinde erişebilirsiniz. Uygulamanın görünümü sınıftan türetme tarafından [CHtmlView](../../mfc/reference/chtmlview-class.md), etkili bir şekilde WebBrowser denetimi ile görünüm sağlayarak uygulama bir Web tarayıcısı olun.

### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>MFC belge/görünüm mimarisi hakkında temel bir Web tarayıcı uygulaması oluşturmak için

1. Bölümündeki yönergeleri izleyin [MFC uygulaması oluşturma](../../mfc/reference/creating-an-mfc-application.md).

1. MFC Uygulama Sihirbazı'nda [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında, belirli olun **belge/görünüm mimarisi** kutusu seçilidir. (Ya da tercih edebilirsiniz **tek belge** veya **birden çok belge**, ama **iletişim kutusu tabanlı**.)

1. Üzerinde [gözden geçirme oluşturulan sınıflar](../../mfc/reference/generated-classes-mfc-application-wizard.md) sayfasında **temel sınıfı** seçmek için aşağı açılan menüsünü `CHtmlView`.

1. Yerleşik çatı uygulamasına istediğiniz diğer seçenekleri belirleyin.

1. **Son**'a tıklayın.

WebBrowser denetimi, köprüler ve Tekdüzen Kaynak Konum Belirleyicisi (URL) gezinti aracılığıyla gözatmayı destekler. İleriye göz atmak kullanıcıya izin veren geçmiş listesi denetimi korur ve geri önceden siteler, klasörler ve belgeler göz. Denetim, gezinti, köprüler, geçmiş listeleri, Sık Kullanılanlar ve güvenlik doğrudan işler. Uygulamaları WebBrowser denetimi de etkin belgeler konak için bir etkin belge kapsayıcısı olarak kullanabilir. Bu nedenle, Microsoft Excel elektronik tablolar gibi zengin biçimli belgeler veya Word belgeleri açılabilir ve WebBrowser denetimi içinde yerinde düzenlenebilir. WebBrowser denetimi ayrıca herhangi bir ActiveX denetimi barındıran bir ActiveX denetimi kapsayıcısı var.

> [!NOTE]
>  WebBrowser ActiveX denetimi (ve bu nedenle `CHtmlView`) yalnızca Windows sürümlerinde hangi Internet Explorer 4.0 altında çalışan uygulamalar için kullanılabilir veya üzeri yüklü.

Çünkü `CHtmlView` yazdırma gibi diğer değil yalnızca Microsoft Web tarayıcı denetimi desteği uygulayan [CView](../../mfc/reference/cview-class.md)-türetilmiş sınıflar. Bunun yerine, yazıcı kullanıcı arabirimi ve yazdırma WebBrowser denetimi uygular. Sonuç olarak, `CHtmlView` mu desteklemediği Baskı Önizleme ve framework için yazdırma diğer destek işlevlerini sağlamaz: Örneğin, [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting), [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting), ve [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting), olan diğer MFC uygulamalarında kullanılabilir.

`CHtmlView` Uygulamanız bir Web veya HTML sayfasından bir görünümde sunan Web tarayıcı denetimi için bir sarmalayıcı olarak görev yapar. Bir geçersiz kılma için sihirbazın oluşturduğu [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) Microsoft Visual C++ Web sitesine gezinme bağlantısı sağlama görünüm sınıfı, işlev:

```cpp
void CWebView::OnInitialUpdate()
{
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.
    Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),
        NULL,
        NULL);
}
```

Bu site kendi biriyle değiştirebilirsiniz ya da kullanabileceğinizi [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource) görünümü için varsayılan içerik olarak projenin kaynak komut dosyasında yer alan bir HTML sayfasını açmak için üye işlevi. Örneğin:

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

[MFC örnek MFCIE](https://github.com/Microsoft/VCSamples)<br/>
[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)<br/>
[Proje Özellikleriyle Çalışma](../../ide/working-with-project-properties.md)<br/>
[Özellik Sayfaları](../../ide/property-pages-visual-cpp.md)<br/>
[Proje Özellikleriyle Çalışma](../../ide/working-with-project-properties.md)
