---
title: 'TN017: Pencere nesnelerini yok etme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.objects
dev_langs:
- C++
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd7b8e9882d682d3e7a9b9162f1f2f84675cd590
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951540"
---
# <a name="tn017-destroying-window-objects"></a>TN017: Pencere Nesnelerini Yok Etme
Bu Not kullanımını açıklar [CWnd::PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) yöntemi. Özelleştirilmiş ayrılması yapmak istiyorsanız bu yöntemi kullanın `CWnd`-türetilmiş nesneleri. Bu Not ayrıca neden kullanmanız açıklar [CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) yerine C++ Windows nesnesi yok etmek için **silmek** işleci.  
  
 Bu konudaki yönergeleri izleyin, birkaç temizleme sorunları yüklemeniz gerekir. Bu sorunları silme/C++ bellek gibi sistem kaynaklarını serbest işlerle serbest işlerle gibi sorunlardan sonuçlanabilir `HWND`s veya birden çok kez nesneleri serbest bırakma.  
  
## <a name="the-problem"></a>Sorun  
 Her windows nesne (nesne sınıfının türetilen `CWnd`) hem bir C++ nesneyi temsil eder ve bir `HWND`. C++ nesneleri, uygulamanın yığınında ayrılır ve `HWND`s sistem kaynakları Pencere Yöneticisi tarafından ayrılır. Bir pencere nesnesi yok etmek için çeşitli yollar olduğundan, sistem engelleme kuralları kümesi sağlamanız gerekir kaynak veya bellek sızıntıları. Bu kurallar da nesneleri ve Windows tanıtıcıları birden fazla kez yok engellemeniz gerekir.  
  
## <a name="destroying-windows"></a>Pencereleri yok etme  
 Bir Windows nesnesi yok etmek için iki izin verilen yollar şunlardır:  
  
-   Çağırma `CWnd::DestroyWindow` ya da Windows API `DestroyWindow`.  
  
-   İle açıkça silme **silmek** işleci.  
  
 İlk olarak şu ana kadar en yaygın bir durumdur. Kodunuzu çağrılmayan olsa bile bu durum geçerlidir `DestroyWindow` doğrudan. Kullanıcının doğrudan bir çerçeve penceresi kapanır, bu eylem WM_CLOSE iletisini oluşturur ve bu ileti varsayılan yanıt çağırmaktır `DestroyWindow.` üst pencere bozulduğunda Windows çağırır `DestroyWindow` tüm alt gruplar için.  
  
 İkinci durumda, kullanımını **silmek** Windows nesneler üzerinde operatör nadir. Bazı durumlarda kullanarak burada aşağıdaki olan **silmek** doğru seçimdir.  
  
## <a name="auto-cleanup-with-cwndpostncdestroy"></a>Otomatik temizleme CWnd::PostNcDestroy ile  
 Bir Windows pencere sistemin bozar penceresine gönderilen son Windows ileti WM_NCDESTROY olur. Varsayılan `CWnd` ileti işleyicisi [CWnd::OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy). `OnNcDestroy` detach `HWND` C++ içinden nesne ve sanal işlev çağrısı `PostNcDestroy`. Bazı sınıflar C++ nesnesini silmek için bu işlevi geçersiz.  
  
 Varsayılan uygulaması `CWnd::PostNcDestroy` hiçbir şey, yığın çerçevesi ayrıldı veya diğer nesneleri katıştırılmış pencere nesneleri için uygun olduğu yapmaz. Bu diğer nesneleri olmadan yığında ayrılacak tasarlanan pencere nesneleri için uygun değildir. Diğer bir deyişle, diğer C++ nesneleri gömülü olmayan pencere nesneleri için uygun değil.  
  
 Tek başına yığında ayrılmış için tasarlanmış bu sınıfların geçersiz kılma `PostNcDestroy` yapmak için yöntemi bir **bu silme**. Bu bildirimi C++ nesneyle ilişkilendirilmiş bellek boşaltır. Olsa bile varsayılan `CWnd` yıkıcı çağrıları `DestroyWindow` varsa *m_hWnd* olan tanıtıcı temizleme aşamasında ayrılmış ve NULL olacağı için NULL olmayan, bu sonsuz özyinelemeye neden olmaz.  
  
> [!NOTE]
>  Sistem genellikle çağırır `CWnd::PostNcDestroy` Windows WM_NCDESTROY iletisini işledikten sonra ve `HWND` ve C++ pencere nesnesi artık bağlı. Sistem ayrıca çağırma `CWnd::PostNcDestroy` çoğu uygulamasında [CWnd::Create](../mfc/reference/cwnd-class.md#create) hatası oluşursa, çağırır. Otomatik temizleme kuralları, bu konunun ilerleyen bölümlerinde açıklanmıştır.  
  
## <a name="auto-cleanup-classes"></a>Otomatik temizleme sınıfları  
 Aşağıdaki sınıflar otomatik temizleme için tasarlanmamıştır. Diğer C++ nesneleri veya yığında katıştırılmış genellikle:  
  
-   Tüm standart Windows denetimleri (`CStatic`, `CEdit`, `CListBox`, vb.).  
  
-   Tüm alt öğe pencerelerini doğrudan türetilmiş `CWnd` (örneğin, özel denetimleri).  
  
-   Bölümlendirici pencereler (`CSplitterWnd`).  
  
-   Varsayılan Denetim çubukları (türetilmiş sınıfları `CControlBar`, bkz: [Teknik Not 31](../mfc/tn031-control-bars.md) denetim çubuğu nesneleri için otomatik silmeyi etkinleştirme için).  
  
-   İletişim kutuları (`CDialog`) yığın çerçevesinde kalıcı iletişim kutuları için tasarlanmıştır.  
  
-   Tüm standart iletişim kutuları dışında `CFindReplaceDialog`.  
  
-   ClassWizard tarafından oluşturulan varsayılan iletişim kutuları.  
  
 Aşağıdaki sınıflar otomatik temizleme için tasarlanmıştır. Bunlar genellikle kendi kendilerine yığında ayrılan:  
  
-   Ana çerçeve pencereleri (doğrudan veya dolaylı olarak türetilen `CFrameWnd`).  
  
-   Windows görüntüleme (doğrudan veya dolaylı olarak türetilen `CView`).  
  
 Bu kurallar bölün istiyorsanız, geçersiz kılmanız gerekir `PostNcDestroy` türetilmiş sınıfınızda yöntemi. Otomatik temizleme sınıfınıza eklemek için temel sınıfı arayın ve sonra yapın bir **bu silme**. Otomatik temizleme, sınıfından kaldırmak için arama `CWnd::PostNcDestroy` doğrudan yerine, `PostNcDestroy` doğrudan temel sınıfınız yöntemi.  
  
 Otomatik temizleme davranışı değiştirmenin en yaygın kullanımı, yığında ayrılan kalıcı olmayan bir iletişim oluşturmaktır.  
  
## <a name="when-to-call-delete"></a>Çağrı silinecek  
 Sizi aramasını öneririz `DestroyWindow` C++ yöntemi veya genel bir Windows nesnesi yok etmek için `DestroyWindow` API.  
  
 Genel çağırmayın `DestroyWindow` MDI alt pencere yok etme API. Sanal bir yöntem kullanması gereken `CWnd::DestroyWindow` yerine.  
  
 Otomatik temizleme gerçekleştirmeyin C++ pencere nesneleri için kullanarak **silmek** işleci çağırmaya çalıştığınızda bir bellek sızıntısı neden olabilir `DestroyWindow` içinde `CWnd::~CWnd` VTBL doğru türetilmiş bir sınıfa işaret etmiyorsa yıkıcı. Bu durum, sistem uygun çağrılacak yöntem destroy bulamıyor kaynaklanır. Kullanarak `DestroyWindow` yerine **silmek** bu sorunları ortadan kaldırır. Bu bir hafif hatası olabileceğinden, risk altında olduğunda hata ayıklama modunda derleme aşağıdaki uyarı oluşturur.  
  
```  
Warning: calling DestroyWindow in CWnd::~CWnd  
    OnDestroy or PostNcDestroy in derived class will not be called  
```  
  
 Otomatik temizleme işlemi gerçekleştirin C++ Windows nesneleri söz konusu olduğunda, çağırmalısınız `DestroyWindow`. Kullanırsanız **silmek** işleci doğrudan MFC tanılama bellek ayırıcısı sizi bilgilendireceğiz iki kez bellek boşaltma. İki ilk açık aramanız ve dolaylı çağrısı durumda **bu silme** otomatik temizleme uygulamasında `PostNcDestroy`.  
  
 Çağırdıktan sonra `DestroyWindow` otomatik temizleme nesnesinde C++ nesnesini geçici devam edebilir ancak *m_hWnd* NULL olacak. Çağırdıktan sonra `DestroyWindow` otomatik temizleme nesnede C++ nesnesini otomatik temizleme uygulamasında C++ delete işleci tarafından serbest, kaybolur `PostNcDestroy`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

