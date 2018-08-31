---
title: Bir Web tarayıcısı stilinde MFC uygulaması oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcweb.project
dev_langs:
- C++
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications [MFC], creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71312a1dfa70ca3fd83242f6f706654c08a4973c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217673"
---
# <a name="creating-a-web-browser-style-mfc-application"></a>Web Tarayıcısı Stilinde MFC Uygulaması Oluşturma
Bir Web tarayıcısı stilinde uygulaması bilgilere (örneğin, HTML veya etkin belgeler) Internet veya intranet, yanı klasör yerel dosya sistemi ve ağ üzerinde erişebilirsiniz. Uygulamanın görünümü sınıftan türetme tarafından [CHtmlView](../../mfc/reference/chtmlview-class.md), etkili bir şekilde WebBrowser denetimi ile görünüm sağlayarak uygulama bir Web tarayıcısı olun.  
  
### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>MFC belge/görünüm mimarisi hakkında temel bir Web tarayıcı uygulaması oluşturmak için  
  
1.  Bölümündeki yönergeleri izleyin [MFC uygulaması oluşturma](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  MFC Uygulama Sihirbazı'nda [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında, belirli olun **belge/görünüm mimarisi** kutusu seçilidir. (Ya da tercih edebilirsiniz **tek belge** veya **birden çok belge**, ama **iletişim kutusu tabanlı**.)  
  
3.  Üzerinde [gözden geçirme oluşturulan sınıflar](../../mfc/reference/generated-classes-mfc-application-wizard.md) sayfasında **temel sınıfı** seçmek için aşağı açılan menüsünü `CHtmlView`.  
  
4.  Yerleşik çatı uygulamasına istediğiniz diğer seçenekleri belirleyin.  
  
5.  **Son**'a tıklayın.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MFCIE](https://msdn.microsoft.com/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)   
 [Proje özellikleriyle çalışma](../../ide/working-with-project-properties.md)   
 [Özellik sayfaları](../../ide/property-pages-visual-cpp.md)   
 [Proje özellikleriyle çalışma](../../ide/working-with-project-properties.md)   
 [Uygulamaları dağıtma](https://msdn.microsoft.com/4ff8881d-0daf-47e7-bfe7-774c625031b4)

