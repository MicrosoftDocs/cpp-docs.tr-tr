---
title: "Belge görünüm mimarisinin alternatifleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], applications without
- CDocument class [MFC], space requirements
- views [MFC], applications without
ms.assetid: 2c22f352-a137-45ce-9971-c142173496fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 459383474c9ffed9a7ad6cefe01ea21626cb23b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="alternatives-to-the-documentview-architecture"></a>Belge/Görünüm Mimarisinin Alternatifleri
MFC uygulamaları, belge/görünüm mimarisinin normalde bilgiler, dosya biçimlerini ve görsel veri kullanıcılarına yönetmek için kullanın. Masaüstü uygulamaları çoğunluğu için belge/görünüm mimarisinin bir uygun ve etkili uygulama mimarisidir. Bu mimari veri görüntüleme ve, çoğu durumda ayıran, uygulamanızı kolaylaştırır ve gereksiz kod azaltır.  
  
 Ancak, belge/görünüm mimarisinin bazı durumlar için uygun değil. Bu örnekler göz önünde bulundurun:  
  
-   Windows için C yazılmış bir uygulama bağlantı noktası oluşturma, uygulamanıza belge/görünüm destek eklemeden önce bağlantı noktası tamamlamak isteyebilirsiniz.  
  
-   Basit bir yardımcı programı yazıyorsanız, belge/görünüm mimarisinin yapabileceğiniz bulabilirsiniz.  
  
-   Özgün kodunuzu zaten veri yönetimi verileriyle karıştırır iki ayrı gerekir çünkü görüntüleme, taşıma belge/görünüm modeli koda çabalara değildir. Kod olarak bırakmak tercih edebilirsiniz.  
  
 Belge/görünüm mimarisinin kullanmayan bir uygulama oluşturmak için temizleyin **belge/görünüm mimarisi desteği** MFC Uygulama Sihirbazı'nın 1. adımda onay kutusu. Bkz: [MFC Uygulama Sihirbazı'nı](../mfc/reference/mfc-application-wizard.md) Ayrıntılar için.  
  
> [!NOTE]
>  MFC Uygulama Sihirbazı tarafından üretilen iletişim tabanlı uygulamalar belge/görünüm mimarisinin kullanmayın böylece **belge/görünüm mimarisi desteği** iletişim uygulama türü seçerseniz onay kutusunu devre dışı.  
  
 Tıpkı başka sihirbaz tarafından oluşturulan bir uygulama ile olduğu gibi kaynak ve iletişim düzenleyicileri yanı sıra, Visual C++ sihirbazları oluşturulan uygulaması ile çalışırsınız. Uygulama araç çubukları, kaydırma çubukları ve durum çubuğu destekleyebilir ve sahip bir **hakkında** kutusu. Uygulamanız herhangi bir belge şablon kaydedilmiyor ve belge sınıfı içermez.  
  
 Oluşturulan uygulamanız bir görünüm sınıfı sahip olduğuna dikkat edin **CChildView**, türetilmiş `CWnd`. MFC oluşturur ve görünüm sınıfının bir örneği, uygulamanız tarafından oluşturulan çerçeve pencereleri içinde yerleştirir. Konumlandırma ve uygulama içeriğinin yönetme basitleştirir çünkü MFC hala bir Görünüm penceresi kullanarak zorlar. Boyama kod ekleyebilirsiniz `OnPaint` Bu sınıf üyesi. Kodunuzu scrollbars görünümü yerine çerçeve eklemeniz gerekir.  
  
 MFC tarafından sağlanan belge/görünüm mimarisinin bir uygulamanın temel özelliklerin çoğunu gerçekleştirmek için sorumlu olduğu için uygulamanızın birçok önemli özellikleri uygulamak için sorumlu yokluğu projenizdeki anlamına gelir:  
  
-   MFC Uygulama Sihirbazı tarafından sağlanan gibi uygulamanız için menüyü yalnızca içeren `New` ve `Exit` komutlarını **dosya** menüsü. ( `New` Komut yalnızca MDI uygulamaları için desteklenir, belge/görünüm olmadan SDI uygulamaları destekler.) Oluşturulan menü kaynağı (en son kullanılan) MRU listesini desteklemez.  
  
-   İşleyici işlevleri ve uygulamaları dahil olmak üzere, uygulamanızın destekleyecek herhangi bir komut için eklemelisiniz **açık** ve **kaydetmek** üzerinde **dosya** menüsü. MFC normalde bu özellikleri destekleyecek kodu destek sıkı bir şekilde belge/görünüm mimarisinin bağlı ancak sağlar.  
  
-   Biri, istenen araç, uygulamanız için en az olur.  
  
 Sihirbaz doğru bir MFC mimarisi güvence altına alır çünkü MFC Uygulama Sihirbazı'nı belge/görünüm mimarisinin olmadan uygulamaları oluşturmak için kullanmanız önerilir. Ancak, sihirbaz kullanmaktan kaçının gerekir, kodunuzda belge/görünüm mimarisinin atlayarak için çeşitli yaklaşımlar şunlardır:  
  
-   Belge kullanılmayan bir appendage kabul eder ve veri yönetimi kodunuzu view sınıfında, yukarıda önerilen olarak uygulayın. Belge için ek yükü oldukça düşüktür. Tek bir [CDocument](../mfc/reference/cdocument-class.md) nesne tek başına ek yükü artı küçük yükü az miktarda doğurur **CDocument**ait temel sınıflar, [CCmdTarget](../mfc/reference/ccmdtarget-class.md) ve [ CObject](../mfc/reference/cobject-class.md). İkinci sınıfların her ikisi de küçük.  
  
     Bildirilen **CDocument**:  
  
    -   İki `CString` nesneleri.  
  
    -   Üç **BOOL**s.  
  
    -   Bir `CDocTemplate` işaretçi.  
  
    -   Bir `CPtrList` belgenin görünümleri listesini içeren nesne.  
  
     Ayrıca, belgenin belge nesnesi, görünüm nesnelerini, çerçeve penceresi ve bir belge şablonu nesnesi oluşturmak için süre miktarını gerektirir.  
  
-   Belge ve görünüm kullanılmayan appendages kabul eder. Veri Yönetimi ve çizim kodunu çerçeve penceresi görünümü yerine koyun. Bu yaklaşım C dili programlama modeli daha yakın olur.  
  
-   Belge ve hiç oluşturma ortadan kaldırmak için Görünüm oluşturma MFC çerçevesi bölümlerini geçersiz kılar. Belge oluşturma işlemi için bir çağrı ile başlayan `CWinApp::AddDocTemplate`. Bu uygulama sınıfınızın çağrısından ortadan `InitInstance` üye işlev ve bunun yerine, bir çerçeve penceresinde oluşturun `InitInstance` kendiniz. Veri Yönetimi kodunuzu çerçeve penceresi sınıfında yerleştirin. Belge/görünüm oluşturma işlemi gösterilmiştir [belge/görünüm oluşturma](../mfc/document-view-creation.md). Bu daha fazla iş ve framework'ün daha derin bir anlayış gerektirir, ancak tamamen belge/görünüm yükü serbest bırakır.  
  
 Makaleyi [MFC: olmadan veritabanı sınıflarını belgeleri kullanarak ve görünümleri](../data/mfc-using-database-classes-without-documents-and-views.md) veritabanı uygulamaları bağlamında belge/görünüm alternatifleri daha somut örnekleri verir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

