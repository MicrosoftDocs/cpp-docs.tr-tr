---
title: "Bir Web tarayıcısı stilinde MFC uygulaması oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfcweb.project
dev_langs: C++
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications [MFC], creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6c88ca61fb7dfdfbe90ed3b460c0fe9bc3a045ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-web-browser-style-mfc-application"></a>Web Tarayıcısı Stilinde MFC Uygulaması Oluşturma
Bir Web tarayıcısı stilinde uygulama bilgileri (örneğin, HTML veya etkin belgeler) Internet veya intranet yanı sıra klasörler yerel dosya sistemi ve ağ üzerinde erişebilir. Uygulamanın görünümü sınıfından türetilen tarafından [CHtmlView](../../mfc/reference/chtmlview-class.md), etkili bir şekilde WebBrowser denetimi ile görünümü sağlayarak uygulama bir Web tarayıcısı olun.  
  
### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>MFC belge/görünüm mimarisine bağlı bir Web tarayıcı uygulaması oluşturmak için  
  
1.  İçindeki yönergeleri izleyin [MFC uygulaması oluşturma](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  MFC Uygulama Sihirbazı'nda [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında, belirli olun **belge/görünüm mimarisinin** kutusu seçilidir. (Ya da seçebilirsiniz **tek bir belge** veya **birden çok belge**, ama **tabanlı iletişim**.)  
  
3.  Üzerinde [gözden geçirme oluşturulan sınıflar](../../mfc/reference/generated-classes-mfc-application-wizard.md) sayfasında, kullanmak **temel sınıfı** seçmek için aşağı açılan menüsünü `CHtmlView`.  
  
4.  İskelet uygulamasına yerleşik istediğiniz diğer seçenekleri seçin.  
  
5.  **Son**'a tıklayın.  
  
 WebBrowser denetimi köprüler ve Tekdüzen Kaynak Konum Belirleyicisi (URL) gezinti aracılığıyla Web'e gözatma destekler. Denetim İleri Gözat olanak tanır. geçmiş listesini tutar ve aracılığıyla geriye dönük önceden siteler, klasörler ve belgeler taranan. Denetim doğrudan Gezinti, köprüler, geçmiş listeleri, Sık Kullanılanlar ve güvenlik işler. Uygulamalar WebBrowser denetimi de etkin belgelerini barındıracak bir etkin belge kapsayıcısı olarak kullanabilirsiniz. Bu nedenle, Microsoft Excel elektronik tablolar gibi zengin biçimli belgeler veya Word belgelerini açılabilir ve WebBrowser denetimi içinde yerinde düzenlenemez. WebBrowser denetimi de herhangi bir ActiveX denetimi barındıran bir ActiveX denetimi kapsayıcıdır.  
  
> [!NOTE]
>  WebBrowser ActiveX denetimini (ve bu nedenle `CHtmlView`) yalnızca Windows sürümlerinde hangi Internet Explorer 4.0 altında çalışan uygulamalar için kullanılabilir veya sonraki sürümü yüklü.  
  
 Çünkü `CHtmlView` yazdırma gibi diğer değil yalnızca Microsoft Web tarayıcısı denetimi desteğini uygulayan [CView](../../mfc/reference/cview-class.md)-türetilmiş sınıfları. Bunun yerine, yazıcı kullanıcı arabirimi ve yazdırma WebBrowser denetimi uygular. Sonuç olarak, `CHtmlView` mu desteklemediğinden Baskı Önizleme ve framework için diğer yazdırma desteği işlevleri sağlamaz: Örneğin, [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting), [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting), ve [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting), diğer MFC uygulamalarında kullanılabilir olduğu.  
  
 `CHtmlView`Uygulamanızı bir Web veya HTML sayfası üzerine bir görünüm verir Web tarayıcısı denetimi için sarmalayıcı gibi davranır. Bir geçersiz kılma için sihirbazın oluşturduğu [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) Microsoft Visual C++ Web sitesine gezinme bağlantı sağlama view sınıfında, işlevi:  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),
    NULL,
    NULL);

} 
```  
  
 Bu site biriyle kendi değiştirebilir veya kullanabilirsiniz [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource) görünümü için varsayılan içerik olarak projenin kaynak komut dosyasında bulunan bir HTML sayfasını açmak için üye işlevi. Örneğin:  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    LoadFromResource(IDR_HTML1);

} 
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MFCIE](http://msdn.microsoft.com/en-us/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)   
 [Proje özellikleriyle çalışma](../../ide/working-with-project-properties.md)   
 [Özellik sayfaları](../../ide/property-pages-visual-cpp.md)   
 [Proje özellikleriyle çalışma](../../ide/working-with-project-properties.md)   
 [Uygulamaları dağıtma](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)

