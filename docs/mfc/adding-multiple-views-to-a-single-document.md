---
title: "Tek bir belgeye birden çok görünüm ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aea707a208e9642b5847b17a8f37a4a5f77f145e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-multiple-views-to-a-single-document"></a>Tek Bir Belgeye Birden Çok Görünüm Ekleme
Microsoft Foundation Class (MFC) kitaplığı ile oluşturulan bir tek belge arabirimi (SDI) uygulamasında her belge türü tek bir görünüm türü ile ilişkilidir. Bazı durumlarda, yeni bir görünüm geçerli görünümüyle belgenin geçme özelliğine sahip önerilir.  
  
> [!TIP]
>  Tek bir belgenin birden çok görünüm uygulama ek yordamlar için bkz: [CDocument::AddView](../mfc/reference/cdocument-class.md#addview) ve [TOPLAMAK](../visual-cpp-samples.md) MFC örnek.  
  
 Yeni bir ekleyerek bu işlevselliği uygulayabilirsiniz `CView`-türetilmiş sınıf ve görünümler varolan bir MFC uygulamasına dinamik geçiş için ek kod.  
  
 Adımlar aşağıdaki gibidir:  
  
-   [Mevcut uygulama sınıfını değiştirme](#vcconmodifyexistingapplicationa1)  
  
-   [Oluşturma ve yeni görünüm sınıfı değiştirme](#vcconnewviewclassa2)  
  
-   [Oluşturun ve yeni görünüm ekleyin](#vcconattachnewviewa3)  
  
-   [Geçiş işlevini uygulayın](#vcconswitchingfunctiona4)  
  
-   [Görünüm geçmek için desteği ekleme](#vcconswitchingtheviewa5)  
  
 Bu konunun geri kalanında aşağıdakileri varsayar:  
  
-   Adını `CWinApp`-türetilen nesne `CMyWinApp`, ve `CMyWinApp` bildirilir ve MYWINAPP tanımlanmış. H ve MYWINAPP. CPP.  
  
-   `CNewView`Yeni adı `CView`-nesne, türetilmiş ve `CNewView` bildirilir ve yeni görünüm tanımlanmış. H ve yeni görünüm. CPP.  
  
##  <a name="vcconmodifyexistingapplicationa1"></a>Mevcut uygulama sınıfını değiştirme  
 Uygulamanın görünümleri arasında geçiş yapmak için görünümleri ve bunları geçiş yapmak için bir yöntem depolamak için üye değişkenleri ekleyerek uygulama sınıfı değiştirmeniz gerekir.  
  
 Bildirimi için aşağıdaki kodu ekleyin `CMyWinApp` MYWINAPP içinde. Y:  
  
 [!code-cpp[NVC_MFCDocViewSDI#1](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]  
  
 Yeni üye değişkenleri `m_pOldView` ve `m_pNewView`, geçerli görünümü ve yeni oluşturulan bir noktası. Yeni yöntemi (`SwitchView`) kullanıcı tarafından istendiğinde görünümleri geçer. Yönteminin gövdesi, bu konunun ilerleyen bölümlerinde açıklanan [geçiş işlevi uygulamak](#vcconswitchingfunctiona4).  
  
 Windows ileti tanımlayan yeni bir üst bilgi dosyasını dahil olmak üzere uygulama sınıfı son değiştirilme gerektirir (**WM_INITIALUPDATE**) geçiş işlevinde kullanılır.  
  
 MYWINAPP INCLUDE bölümünde aşağıdaki satırı ekleyin. CPP:  
  
 [!code-cpp[NVC_MFCDocViewSDI#2](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]  
  
 Yaptığınız değişiklikleri kaydedin ve sonraki adıma devam edin.  
  
##  <a name="vcconnewviewclassa2"></a>Oluşturma ve yeni görünüm sınıfı değiştirme  
 Yeni Görünüm sınıfı oluşturma yapılan kolay kullanarak **yeni sınıf** komutunu sınıfı görünümünden kullanılabilir. Yalnızca bu sınıf için öğesinden türetilen gereksinimdir `CView`. Bu yeni sınıf uygulamaya ekleyin. Projeye yeni bir sınıf ekleme ile ilgili ayrıntılı bilgi için bkz: [sınıf ekleme](../ide/adding-a-class-visual-cpp.md).  
  
 Projeye sınıfı ekledikten sonra bazı görünüm sınıfı üyeleri erişilebilirliğini değiştirmek gerekir.  
  
 NEWVIEW değiştirin. Gelen erişim belirticisi değiştirerek H `protected` için **ortak** yıkıcı ve Oluşturucusu. Bu, oluşturulan ve dinamik olarak yok ve görünür hale gelmeden önce Görünüm görünümünü değiştirmek için sınıf sağlar.  
  
 Yaptığınız değişiklikleri kaydedin ve sonraki adıma devam edin.  
  
##  <a name="vcconattachnewviewa3"></a>Oluşturun ve yeni görünüm ekleyin  
 Değiştirmenize gerek oluşturmak ve yeni görünüm eklemek için `InitInstance` uygulama sınıfınızın işlevi. Yeni bir görünüm nesnesi ve ardından başlatır hem oluşturur Yeni kod değişikliği ekler `m_pOldView` ve `m_pNewView` nesnelerle iki varolan görünümü.  
  
 İçinde yeni görünüm oluşturulduğundan `InitInstance` işlevi, yeni ve mevcut görünümleri uygulama ömrü boyunca kalır. Ancak, uygulama yeni görünüm kolayca dinamik olarak oluşturabilir.  
  
 Çağrısından sonra bu kodu ekleyin `ProcessShellCommand`:  
  
 [!code-cpp[NVC_MFCDocViewSDI#3](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]  
  
 Yaptığınız değişiklikleri kaydedin ve sonraki adıma devam edin.  
  
##  <a name="vcconswitchingfunctiona4"></a>Geçiş işlevini uygulayın  
 Önceki adımda oluşturulan ve yeni bir görünüm nesnesi başlatılmadı kodu eklendi. Son ana anahtarlama yöntemi uygulamak için parçasıdır `SwitchView`.  
  
 Uygulamanız için uygulama dosya sonunda (MYWINAPP. sınıfı CPP), aşağıdaki yöntemi ekleyin:  
  
 [!code-cpp[NVC_MFCDocViewSDI#4](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]  
  
 Yaptığınız değişiklikleri kaydedin ve sonraki adıma devam edin.  
  
##  <a name="vcconswitchingtheviewa5"></a>Görünüm geçmek için desteği ekleme  
 Çağıran kodu ekleyerek son adım içerir `SwitchView` uygulama görünümleri arasında geçiş yapma gerektiğinde yöntemi. Bu çeşitli şekillerde yapılabilir: seçmek kullanıcı için yeni menü öğesi ekleme ya da belirli koşullar karşılandığında görünüm dahili olarak geçiş tarafından.  
  
 Yeni menü öğeleri ve komut işleyici işlevleri ekleme hakkında daha fazla bilgi için bkz: [komutlar ve denetim bildirimleri için işleyiciler](../mfc/handlers-for-commands-and-control-notifications.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

