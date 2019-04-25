---
title: 'TN017: Pencere Nesnelerini Yok Etme'
ms.date: 11/04/2016
f1_keywords:
- vc.objects
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
ms.openlocfilehash: 9e52112bed0f583a3f5652f9213bd5049d543a80
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306161"
---
# <a name="tn017-destroying-window-objects"></a>TN017: Pencere Nesnelerini Yok Etme

Bu Not kullanımını açıklar [CWnd::PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) yöntemi. Özelleştirilmiş ayırma işlemi yapmak istiyorsanız bu yöntemi kullanın `CWnd`-türetilmiş nesneler. Bu Not, ayrıca neden kullanmanız gerektiğini açıklar [CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) yerine bir C++ Windows nesneyi yok etmek için **Sil** işleci.

Bu konu başlığı altındaki yönergeleri izleyin, birkaç temizleme sorunları yüklemeniz gerekir. Bu sorunları gibi sistem kaynaklarını serbest unutmak C++ bellek silme/serbest unutmak gibi sorunlardan sonuçlanabilir `HWND`s veya çok fazla kez nesneleri serbest bırakma.

## <a name="the-problem"></a>Sorun

Her windows nesnesi (sınıfından türetilen bir sınıfın nesne `CWnd`) hem bir C++ nesnesi temsil eder ve bir `HWND`. C++ nesneleri, uygulamanın yığında ayrılır ve `HWND`s sistem kaynakları Pencere Yöneticisi tarafından ayrılır. Pencere nesnesini yok etmek için çeşitli yollar olduğundan, sistem engelleyen kuralları kümesi sağlamanız gerekir kaynak veya bellek sızıntısı. Bu kurallar ayrıca nesneleri ve Windows tanıtıcıları birden fazla kez yok engellemelisiniz.

## <a name="destroying-windows"></a>Windows yok etme

Bir Windows nesneyi yok etmek için iki izin verilen yollar şunlardır:

- Çağırma `CWnd::DestroyWindow` ya da Windows API `DestroyWindow`.

- İle açıkça silme **Sil** işleci.

İlk şu ana kadar en yaygın bir durumdur. Bu durumda bile, kod arama geçerlidir `DestroyWindow` doğrudan. Kullanıcı doğrudan bir çerçeve penceresini kapatır, bu eylem WM_CLOSE iletisini oluşturur ve bu iletiye varsayılan yanıt çağırmaktır `DestroyWindow.` üst penceresine kaldırıldığında, bu Windows çağırır `DestroyWindow` tüm alt öğeleri için.

İkinci durumda, kullanımını **Sil** Windows nesneler üzerinde operatör seyrek olmalıdır. Bazı durumlarda kullanıldığında aşağıdaki öğeler **Sil** doğru seçimdir.

## <a name="auto-cleanup-with-cwndpostncdestroy"></a>Otomatik temizleme CWnd::PostNcDestroy ile

Sistemin Windows penceresini yok eder penceresine gönderilen son Windows ileti WM_NCDESTROY olur. Varsayılan `CWnd` için ileti işleyicisi [CWnd::OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy). `OnNcDestroy` ayırma `HWND` C++'tan nesne ve sanal işlev çağrısı `PostNcDestroy`. Bazı sınıflar C++ nesneyi silmek için bu işlevi geçersiz.

Varsayılan uygulaması `CWnd::PostNcDestroy` işlem, ayrılan yığın çerçevesini veya diğer nesneleri katıştırılmış pencere nesneleri için uygun olduğu gerçekleştirmez. Bu olmadan herhangi bir nesne yığını üzerindeki ayrılacak tasarlanan pencere nesneleri için uygun değildir. Diğer bir deyişle, diğer C++ nesneleri gömülü pencere nesneleri için uygun değil.

Tek başına yığında ayrılan için tasarlanan bu sınıfları geçersiz kılma `PostNcDestroy` gerçekleştirmek için yöntemi bir **bu silme**. Bu bildirimi, C++ nesneyle ilişkili herhangi bir bellek boşaltır. Olsa bile varsayılan `CWnd` yıkıcı çağrıları `DestroyWindow` varsa *m_hWnd* olan ayrılmış ve NULL temizleme aşamasında tanıtıcı olacağından NULL olmayan, bu sonsuz özyineleme durumuna yol neden olmaz.

> [!NOTE]
>  Sistem genellikle çağrıları `CWnd::PostNcDestroy` Windows WM_NCDESTROY iletisini işledikten sonra ve `HWND` ve C++ pencere nesnesi artık bağlı. Sistem ayrıca çağırma `CWnd::PostNcDestroy` çoğu uygulamada [CWnd::Create](../mfc/reference/cwnd-class.md#create) hata oluşması durumunda çağırır. Otomatik temizleme kuralları, bu konunun ilerleyen bölümlerinde açıklanmıştır.

## <a name="auto-cleanup-classes"></a>Otomatik temizleme sınıfları

Aşağıdaki sınıflar, otomatik temizleme için tasarlanmamıştır. Diğer C++ nesnelerinin veya yığın katıştırılmış genellikle:

- Tüm standart Windows denetimler (`CStatic`, `CEdit`, `CListBox`, vb.).

- Tüm alt pencereleri doğrudan türetilmiş `CWnd` (örneğin, özel denetimler).

- Bölümlendirici pencereler (`CSplitterWnd`).

- Varsayılan Denetim çubukları (türetilen sınıflar `CControlBar`, bkz: [Teknik Not 31](../mfc/tn031-control-bars.md) denetim çubuğu nesneler için otomatik silme etkinleştirmek için).

- İletişim kutuları (`CDialog`) yığın çerçevesinde kalıcı iletişim kutuları için tasarlanmıştır.

- Tüm standart iletişim kutuları dışında `CFindReplaceDialog`.

- ClassWizard tarafından oluşturulan varsayılan iletişim kutuları.

Aşağıdaki sınıflar, otomatik temizleme için tasarlanmıştır. Bunlar genellikle başlarına yığında ayrılır:

- Ana çerçeve pencereleri (doğrudan veya dolaylı olarak türetilmiş `CFrameWnd`).

- Windows görüntüleme (doğrudan veya dolaylı olarak türetilmiş `CView`).

Bu kuralı ihlal istiyorsanız, geçersiz kılmanız gerekir `PostNcDestroy` türetilmiş sınıfınızın yöntemi. Sınıfınıza otomatik temizleme eklemek için taban sınıfını çağırın ve ardından yapın bir **bu silme**. Otomatik temizleme sizin sınıfınızdan kaldırmak için çağrı `CWnd::PostNcDestroy` doğrudan yerine, `PostNcDestroy` doğrudan temel sınıfının yöntemi.

Otomatik temizleme davranışı değiştirmenin en yaygın kullanımı, yığında ayrılabilir modelsiz bir iletişim oluşturmaktır.

## <a name="when-to-call-delete"></a>Çağrı silinecek

Çağırmanızı öneririz `DestroyWindow` C++ yöntemi veya genel bir Windows nesneyi yok etmek için `DestroyWindow` API.

Genel çağırmayın `DestroyWindow` MDI alt penceresini yok etmek için API. Sanal yöntem `CWnd::DestroyWindow` yerine.

Otomatik temizleme gerçekleştirmeyin C++ pencere nesneleri için kullanarak **Sil** işleci, bir bellek sızıntısı açabilir, çağırmaya çalıştığınızda `DestroyWindow` içinde `CWnd::~CWnd` VTBL doğru türetilmiş sınıfa işaret etmiyorsa yıkıcı. Bu durum, sistem uygun destroy metodu çağırmak için bulamıyor kaynaklanır. Kullanarak `DestroyWindow` yerine **Sil** bu sorunları ortadan kaldırır. Bu hafif bir hata oluştu Bu nedenle, risk altında olup olmadığını hata ayıklama modunda derleme aşağıdaki uyarı oluşturur.

```
Warning: calling DestroyWindow in CWnd::~CWnd
    OnDestroy or PostNcDestroy in derived class will not be called
```

Otomatik temizleme işlemleri yapma C++ Windows nesneleri söz konusu olduğunda, çağırmalısınız `DestroyWindow`. Kullanırsanız **Sil** işleci doğrudan MFC tanılama bellek ayırıcısı bildirim gönderilir, iki kez bellek boşaltma. İlk açık aramanız ve dolaylı çağrı iki oluşumlar: **bu silme** otomatik temizleme uygulamasında `PostNcDestroy`.

Arama sonra `DestroyWindow` otomatik temizleme nesnesinde C++ nesne çevresinde, hala olacaktır ancak *m_hWnd* NULL olacaktır. Arama sonra `DestroyWindow` otomatik temizleme nesnesinde bir C++ nesnesi otomatik temizleme uygulamalarında C++ delete işleci ile serbest, kaybolur `PostNcDestroy`.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
