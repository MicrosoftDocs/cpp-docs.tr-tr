---
title: 'TN024: MFC Tanımlı İletiler ve Kaynaklar'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.messages
helpviewer_keywords:
- resources [MFC]
- Windows messages [MFC], MFC-defined
- messages [MFC], MFC
- TN024
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
ms.openlocfilehash: 26f6effbafd8136661f0b1dc9a6b22138a23e547
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639640"
---
# <a name="tn024-mfc-defined-messages-and-resources"></a>TN024: MFC Tanımlı İletiler ve Kaynaklar

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, iç Windows iletileri ve MFC tarafından kullanılan kaynak biçimleri açıklanır. Bu bilgiler, uygulama framework'ün açıklar ve uygulamanızı hata ayıklamaya yardımcı olur. Bu bilgiler resmi olarak desteklenmeyen olsa bile kaşif için bu bilgilerin bazıları Gelişmiş uygulamalar için kullanabilirsiniz.

Bu Not, MFC özel uygulama ayrıntılarını içerir. tüm içeriği gelecekte değişikliğe tabi olduğu. MFC özel Windows iletileri yalnızca bir uygulama kapsamında bir anlamı yoktur, ancak gelecekte sistem genelinde iletileri içerecek şekilde değiştirir.

Kaynak türleri ve aralığı MFC özel Windows iletileri ayrılmış "Sistem" aralığında kenara Microsoft Windows tarafından ayarlanır. Şu anda tüm sayılar aralıkları kullanılır ve gelecekte yeni numaraları aralığında kullanılabilir. Şu anda kullanılan sayıları değiştirilebilir.

MFC özel Windows iletileri 0x360 aralığındadır 0x37F ->.

0xFF -> MFC özel kaynak türleri 0xF0 aralığındadır.

**MFC özel Windows iletileri**

Bu Windows iletileri, nispeten gevşek bağ modelini pencere nesneleri arasında ve burada bir C++ sanal işlev uygun olmayacaktır gerekli olduğu C++ sanal işlevleri yerine kullanılır.

Bu özel Windows iletileri ve ilişkili parametre yapıları MFC özel üstbilgisinde bildirilen ' AFXPRIV. H'. Bu üst bilgiyi içeren kodunuzu hiçbirini belgelenmemiş davranışı ve bitinden gelecekte sürümlerdeki MFC sağlayacağına, uyarı.

Bu iletilerden biri işleme gerek kalmadan, nadir durumlarda ON_MESSAGE ileti eşlemesi makroyu kullanın ve genel LRESULT/WPARAM/LPARAM biçimde iletisini işlemek gerekir.

**WM_QUERYAFXWNDPROC**

Bu ileti, oluşturulan bir pencereye gönderilir. Bu oluşturma işleminin başında çok WndProc olup olmadığını belirleyen bir yöntem olarak gönderilen **AfxWndProc. AfxWndProc** 1 döndürür.

|||
|-|-|
|wParam|Kullanılan değil|
|lParam|Kullanılan değil|
|dizisi|1 tarafından işlenen **AfxWndProc**|

**WM_SIZEPARENT**

Bu iletiyi yeniden boyutlandırma sırasında bir çerçeve penceresi tarafından hemen alt gönderilen (`CFrameWnd::OnSize` çağrıları `CFrameWnd::RecalcLayout` çağıran `CWnd::RepositionBars`) denetim çubukları çerçevenin yanında etrafında yeniden konumlandırmak için. Çağırmak, üst ve (hangi NULL olabilir) HDWP geçerli kullanılabilen istemci dikdörtgeni AFX_SIZEPARENTPARAMS yapısı içerir `DeferWindowPos` yeniden çizerken en aza indirmek için.

|||
|-|-|
|wParam|Kullanılan değil|
|lParam|Adres AFX_SIZEPARENTPARAMS yapısı|
|dizisi|(0) kullanılmıyor|

İletiyi yoksaymakla pencere düzeninde bölümü almaz gösterir.

**WM_SETMESSAGESTRING**

Bu ileti, durum çubuğundaki ileti satırı güncelleştirmek için sormak için bir çerçeve penceresi için gönderilir. Dize kimliği ya da bir LPCSTR belirtilen (ancak ikisi birden değil) olabilir.

|||
|-|-|
|wParam|Dize kimliği (veya sıfır)|
|lParam|LPCSTR dize (veya NULL)|
|dizisi|(0) kullanılmıyor|

**WM_IDLEUPDATECMDUI**

Bu ileti, komut güncelleştirme kullanıcı Arabirimi işleyicileri boşta kalma süresi güncelleştirmeyi uygulamak için boşta kalma süresi gönderilir. Pencerenin (genellikle denetim çubuğu) iletiyi işleyen, oluşturduğu bir `CCmdUI` (veya türetilmiş bir sınıfın nesne) ve çağrı `CCmdUI::DoUpdate` penceresinde "öğelerin" her biri için. Bu komut işleyici zincirindeki nesneleri on_update_command_uı işleyicisini sırayla denetler.

|||
|-|-|
|wParam|BOOL bDisableIfNoHandler|
|lParam|(0) kullanılmıyor|
|dizisi|(0) kullanılmıyor|

*bDisableIfNoHandler* bir on_update_command_uı ne ON_COMMAND işleyici ise kullanıcı Arabirimi nesnesi devre dışı bırakmak için sıfır değil.

**WM_EXITHELPMODE**

Bu ileti için gönderilen bir `CFrameWnd` modu, bağlama duyarlı çıkmak için yardımcı olur. Bu iletinin alınması başlatan kalıcı döngüyü sonlandırır `CFrameWnd::OnContextHelp`.

|||
|-|-|
|wParam|(0) kullanılmıyor|
|lParam|(0) kullanılmıyor|
|dizisi|Kullanılan değil|

**WM_INITIALUPDATE**

Bunları kendi ilk güncelleştirme yapmak güvenli olduğunda bu ileti bir çerçeve penceresi tüm alt öğeleri belge şablon tarafından gönderilir. Bir çağrı eşlendiği `CView::OnInitialUpdate` ancak diğer kullanılabilir `CWnd`-türetilmiş sınıflar için diğer kesin güncelleştiriliyor.

|||
|-|-|
|wParam|(0) kullanılmıyor|
|lParam|(0) kullanılmıyor|
|dizisi|(0) kullanılmıyor|

**WM_RECALCPARENT**

Bu ileti bir görünüm tarafından üst pencereye gönderilir (aracılığıyla elde edilen `GetParent`) bir düzen yeniden hesaplama zorlamak için (genellikle üst çağıracak `RecalcLayout`). Bu görünümün toplam boyutu büyüdükçe boyutları büyürken çerçevesinin için gerekli olduğu OLE sunucu uygulamalarında kullanılır.

Üst pencere bu ileti işlediğinde, TRUE döndürür ve istemci alanını yeni boyutu ile lParam geçirilen RECT doldurun. Bu kullanılan `CScrollView` kaydırma çubukları (ardından olduklarında penceresinin dışına getirin) düzgün bir şekilde işlemek için bir sunucu nesnesi olduğunda yerinde etkinleştirildi.

|||
|-|-|
|wParam|(0) kullanılmıyor|
|lParam|LPRECT rectClient NULL olabilir|
|dizisi|Yeni, doğru istemci dikdörtgeni döndürülen, yanlış Aksi takdirde|

**WM_SIZECHILD**

Tarafından gönderilen bu ileti `COleResizeBar` , sahip penceresine (aracılığıyla `GetOwner`) kullanıcı yeniden boyutlandırma tutamaçlarını yeniden boyutlandırma çubuğuyla ne zaman yeniden boyutlandırır. `COleIPFrameWnd` Bu ileti, kullanıcının istendiği çerçeve penceresi yeniden konumlandırmak deneyerek yanıt verir.

Göre yeniden boyutlandırma çubuğu içeren bir çerçeve penceresinin istemci koordinatlar cinsinden verilen yeni bir dikdörtgen adresindeki lParam tarafından verilir.

|||
|-|-|
|wParam|(0) kullanılmıyor|
|lParam|LPRECT rectNew|
|dizisi|(0) kullanılmıyor|

**WM_DISABLEMODAL**

Bu ileti, devre dışı bir çerçeve penceresi tarafından sahip olunan tüm açılır pencere gönderilir. Çerçeve penceresi sonucu açılır penceresi devre dışı gerekip gerekmediğini belirlemek için kullanır.

Bu çerçeve kalıcı bir duruma girdiğinde, açılır pencerede özel işleme gerçekleştirmek için veya devre dışı belirli açılır pencereleri tutmak için kullanabilirsiniz. Araç ipuçları bu ileti çerçeve penceresi örneğin bir kalıcı duruma geçtiğinde kendilerine yok etmek için kullanın.

|||
|-|-|
|wParam|(0) kullanılmıyor|
|lParam|(0) kullanılmıyor|
|dizisi|Sıfır olmayan **değil** penceresi devre dışı bırakmak, 0 gösterir penceresi devre dışı bırakılacak|

**WM_FLOATSTATUS**

Bu ileti, çerçeve etkinleştirilmiş veya başka bir üst düzey bir çerçeve penceresi tarafından devre dışı bir çerçeve penceresi tarafından sahip olunan tüm açılır pencere gönderilir. Bu içinde MFS_SYNCACTIVE uygulaması tarafından kullanılan `CMiniFrameWnd`, bu açılır pencereleri etkinleştirilmesinden en üst düzey çerçeve penceresinin etkinleştirme ile eşitlenmiş halde tutun.

|||
|-|-|
|wParam|Aşağıdaki değerlerden biri:<br /><br /> FS_SHOW<br /><br /> FS_HIDE<br /><br /> FS_ACTIVATE<br /><br /> FS_DEACTIVATE<br /><br /> FS_ENABLEFS_DISABLE<br /><br /> FS_SYNCACTIVE|
|lParam|(0) kullanılmıyor|

Dönüş değeri FS_SYNCACTIVE kendi etkinleştirmeyle kümesi ve pencere bölmeye ise sıfır olmayan olmalıdır üst çerçeve. `CMiniFrameWnd` stili için MFS_SYNCACTIVE olarak ayarlandığında sıfır döndürür.

Daha fazla bilgi için bkz: `CMiniFrameWnd`.

## <a name="wmactivatetoplevel"></a>WM_ACTIVATETOPLEVEL

Bu ileti, "üst düzey grup" penceresinde ya da etkinleştirmek veya etkinliğini sonlandırmak için üst düzey bir pencere gönderilir. Bir üst düzey bir grubun parçası (üst veya sahibi) en üst düzey bir penceresi olan ya da böyle bir pencere tarafından sahip olunan penceredir. Bu ileti için WM_ACTIVATEAPP kullanımda benzer, ancak windows farklı işlemler için ait olduğu durumda çalışır (OLE uygulamalarında yaygındır) tek bir pencere hiyerarşideki karma.

## <a name="wmcommandhelp-wmhelphittest-wmexithelpmode"></a>WM_COMMANDHELP, WM_HELPHITTEST, WM_EXITHELPMODE

Bu iletiler, bağlama duyarlı Yardım uygulamasında kullanılır. Lütfen [Teknik Not 28](../mfc/tn028-context-sensitive-help-support.md) daha fazla bilgi için.

## <a name="mfc-private-resource-formats"></a>MFC özel kaynak biçimleri

Şu anda, MFC, iki özel kaynak biçimlerini tanımlar: RT_TOOLBAR ve RT_DLGINIT.

## <a name="rttoolbar-resource-format"></a>RT_TOOLBAR kaynağı biçimi

AppWizard tarafından sağlanan varsayılan araç MFC 4. 0'da sunulan bir RT_TOOLBAR özel kaynak, temel alır. Araç çubuğu Düzenleyicisi'ni kullanarak bu kaynak düzenleyebilirsiniz.

## <a name="rtdlginit-resource-format"></a>RT_DLGINIT kaynak biçimi

Bir MFC özel kaynak biçimi ek iletişim başlatma bilgileri depolamak için kullanılır. Bu, açılan kutuda depolanan ilk dizeleri içerir. Bu kaynak biçimi el ile düzenlenmesi için tasarlanmamıştır, ancak Visual C++ tarafından işlenir.

Visual C++ ve bu RT_DLGINIT kaynak kaynak bilgileri kullanarak API alternatif olduğundan MFC ilgili özellikleri kullanmak için gerekli değildir. Visual C++ kullanarak yazma, koruma ve uzun vadede, uygulamanızın çevirmek kolaylaşır.

RT_DLGINIT kaynak temel yapısı şöyledir:

```
+---------------+    \
| Control ID    |   UINT             |
+---------------+    |
| Message #     |   UINT             |
+---------------+    |
|length of data |   DWORD            |
+---------------+    |   Repeated
|   Data        |   Variable Length  |   for each control
|   ...         |   and Format       |   and message
+---------------+    /
|     0         |   BYTE
+---------------+
```

Denetim kimliği, ileti göndermek için yinelenen bir bölüm içeren ileti gönder (normal bir Windows iletisi) ve bir değişken uzunluklu veri #. Windows ileti içinde bir formun gönderilir:

```
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);
```

Tüm Windows iletilerini ve veri içeriğini sağlayan bir çok genel biçim budur. MFC ve Visual C++ kaynak Düzenleyicisi yalnızca sınırlı bir alt kümesinde Windows iletileri destekler: birleşik giriş kutuları (verileri bir metin dizesi olan) için ilk ve liste tercihlerinin CB_ADDSTRING.

## <a name="see-also"></a>Ayrıca Bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

