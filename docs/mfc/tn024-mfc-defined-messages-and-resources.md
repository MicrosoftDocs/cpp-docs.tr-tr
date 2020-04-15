---
title: 'TN024: MFC Tanımlı İletiler ve Kaynaklar'
ms.date: 11/04/2016
helpviewer_keywords:
- resources [MFC]
- Windows messages [MFC], MFC-defined
- messages [MFC], MFC
- TN024
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
ms.openlocfilehash: 24bcacd46b839babe9c9c89facb1cc56d18c0ee5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370360"
---
# <a name="tn024-mfc-defined-messages-and-resources"></a>TN024: MFC Tanımlı İletiler ve Kaynaklar

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu not, MFC tarafından kullanılan dahili Windows iletilerini ve kaynak biçimlerini açıklar. Bu bilgiler çerçevenin uygulanmasını açıklar ve uygulamanızın hata ayıklamasında size yardımcı olur. Maceracı için, tüm bu bilgiler resmi olarak desteklenmese de, bu bilgilerin bazılarını gelişmiş uygulamalar için kullanabilirsiniz.

Bu not, MFC özel uygulama ayrıntılarını içerir; tüm içerikler gelecekte değişebilir. MFC özel Windows iletileri yalnızca tek bir uygulama kapsamında bir anlam vardır, ancak gelecekte sistem genelinde iletiler içerecek şekilde değişecektir.

MFC özel Windows iletileri ve kaynak türleri aralığı, Microsoft Windows tarafından ayrılmış ayrılmış "sistem" aralığındadır. Şu anda aralıklarda tüm sayılar kullanılmaz ve gelecekte, aralıktaki yeni sayılar kullanılabilir. Şu anda kullanılan numaralar değiştirilebilir.

MFC özel Windows iletileri 0x360->0x37F aralığındadır.

MFC özel kaynak türleri 0xF0->0xFF aralığındadır.

**MFC Özel Windows İletileri**

Bu Windows iletileri, pencere nesneleri arasında göreceli olarak gevşek bağlantı gerektiren ve C++ sanal işlevinin uygun olmadığı C++ sanal işlevleriyerine kullanılır.

Bu özel Windows iletileri ve ilişkili parametre yapıları MFC özel üstbilgi 'AFXPRIV'de beyan edilir. H'. Bu üstbilgiyi içeren kodunuzdan herhangi birinin belgesiz davranışa güvenebileceği ve büyük olasılıkla MFC'nin gelecekteki sürümlerinde kırılacağı konusunda uyarılır.

Bu iletilerden birini işlemek için gereken nadir durumda, ON_MESSAGE ileti haritası nı kullanmalı ve iletiyi genel LRESULT/WPARAM/LPARAM biçiminde işlemelisiniz.

**WM_QUERYAFXWNDPROC**

Bu ileti oluşturulan bir pencereye gönderilir. Bu wndProc AfxWndProc olup olmadığını belirleme yöntemi olarak oluşturma sürecinde çok erken **gönderilir. AfxWndProc** 1 döndürür.

|||
|-|-|
|Wparam|Kullanılmıyor|
|Lparam|Kullanılmıyor|
|dizisi|**AfxWndProc** tarafından işlenirse 1|

**WM_SIZEPARENT**

Bu ileti, çerçevenin yan tarafındaki denetim çubuklarını`CFrameWnd::OnSize` yeniden `CFrameWnd::RecalcLayout` konumlandırmak için yeniden boyutlandırma sırasında (çağrıları çağıran `CWnd::RepositionBars`çağrılar) yakın çocuklarına bir çerçeve penceresi tarafından gönderilir. AFX_SIZEPARENTPARAMS yapısı, yeniden boyamayı en aza indirmek için çağrılacak `DeferWindowPos` bir ÜST öğenin geçerli istemci dikdörtgenini ve bir HDWP'yi (NULL olabilir) içerir.

|||
|-|-|
|Wparam|Kullanılmıyor|
|Lparam|AFX_SIZEPARENTPARAMS bir yapının adresi|
|dizisi|Kullanılmaz (0)|

İletiyi yok saymak, pencerenin düzende yer almadığını gösterir.

**WM_SETMESSAGESTRING**

Bu ileti, durum çubuğundaki ileti satırını güncelleştirmesini istemek için bir çerçeve penceresine gönderilir. Dize kimliği veya LPCSTR belirtilebilir (ancak her ikisi birden belirtilmez).

|||
|-|-|
|Wparam|String ID (veya sıfır)|
|Lparam|Dize için LPCSTR (veya NULL)|
|dizisi|Kullanılmaz (0)|

**WM_IDLEUPDATECMDUI**

Bu ileti, güncelleştirme komutu Kullanıcı Arabirimi işleyicilerinin boşta zaman güncelleştirmesini uygulamak için boşta zamanda gönderilir. Pencere (genellikle bir denetim çubuğu) iletiyi işlerse, bir `CCmdUI` nesne (veya türetilmiş bir sınıfın nesnesi) oluşturur ve penceredeki "öğelerin" her biri için çağrıda bulundu. `CCmdUI::DoUpdate` Bu sırayla komut işleyicisi zincirindeki nesneler için bir ON_UPDATE_COMMAND_UI işleyicisi için kontrol edecektir.

|||
|-|-|
|Wparam|BOOL bDisableIfNoHandler|
|Lparam|Kullanılmaz (0)|
|dizisi|Kullanılmaz (0)|

*bDisableIfNoHandler,* ON_UPDATE_COMMAND_UI veya ON_COMMAND işleyicisi yoksa UI nesnesini devre dışı etmek için sıfır değildir.

**WM_EXITHELPMODE**

Bu ileti, içeriğe duyarlı yardım modundan çıkmak için bir `CFrameWnd` iletiye nakledilir. Bu iletinin alınması tarafından başlatılan modal `CFrameWnd::OnContextHelp`döngü sona erer.

|||
|-|-|
|Wparam|Kullanılmaz (0)|
|Lparam|Kullanılmaz (0)|
|dizisi|Kullanılmıyor|

**WM_INITIALUPDATE**

Bu ileti, belge şablonu tarafından, ilk güncelleştirmelerini yapmaları güvenli olduğunda, bir çerçeve penceresinin tüm torunlarına gönderilir. Bir çağrıyla `CView::OnInitialUpdate` eşler, ancak diğer `CWnd`tek çekim güncelleştirme için diğer türetilmiş sınıflarda kullanılabilir.

|||
|-|-|
|Wparam|Kullanılmaz (0)|
|Lparam|Kullanılmaz (0)|
|dizisi|Kullanılmaz (0)|

**WM_RECALCPARENT**

Bu ileti, bir düzen yeniden hesaplamasını `GetParent`zorlamak için (genellikle üst öğe çağırır) `RecalcLayout`üst penceresine (üzerinden elde edilen) bir görünüm tarafından gönderilir. Bu, görünümün toplam boyutu büyüdükçe çerçevenin boyutunun büyümesi için gerekli olan OLE sunucu uygulamalarında kullanılır.

Üst pencere bu iletiyi işlerse TRUE döndürmelidir ve lParam'da geçen RECT'yi istemci alanının yeni boyutuyla doldurmalıdır. Bu, bir `CScrollView` sunucu nesnesi yerinde etkinleştirildiğinde kaydırma çubuklarını düzgün bir şekilde işlemek için (eklendiğinde pencerenin dışına yerleştirin) kullanılır.

|||
|-|-|
|Wparam|Kullanılmaz (0)|
|Lparam|LPRECT rectClient, NULL olabilir|
|dizisi|Yeni istemci dikdörtgeni döndürülürse DOĞRU, FALSE aksi takdirde|

**WM_SIZECHILD**

Bu ileti, `COleResizeBar` kullanıcı yeniden boyutlandırma `GetOwner`tutamaçlarıyla yeniden boyutlandırma çubuğunu yeniden boyutlandırdığında sahibi nin penceresine (üzerinden) gönderilir. `COleIPFrameWnd`çerçeve penceresini kullanıcının istediği gibi yeniden konumlandırmaya çalışarak bu iletiyi yanıtlar.

Yeniden boyutlandırma çubuğunu içeren çerçeve penceresine göre istemci koordinatlarında verilen yeni dikdörtgen, lParam tarafından işaret edilir.

|||
|-|-|
|Wparam|Kullanılmaz (0)|
|Lparam|LPRECT rectYeni|
|dizisi|Kullanılmaz (0)|

**WM_DISABLEMODAL**

Bu ileti, devre dışı bırakılan bir çerçeve penceresine ait tüm açılır pencerelere gönderilir. Çerçeve penceresi, açılır pencereyi devre dışı bilip devre dışı bilip devre dışı bilip değiştirmeyeceğini belirlemek için sonucu kullanır.

Çerçeve modal durumuna girdiğinde açılır pencerenizde özel işleme gerçekleştirmek veya belirli açılır pencerelerin devre dışı kalmasını sağlamak için bunu kullanabilirsiniz. Araç ipuçları, çerçeve penceresi bir modal durumuna girdiğinde, örneğin kendilerini yok etmek için bu iletiyi kullanır.

|||
|-|-|
|Wparam|Kullanılmaz (0)|
|Lparam|Kullanılmaz (0)|
|dizisi|Sıfır olmayan **not** penceresi devre dışı, 0 pencere devre dışı olacağını gösterir|

**WM_FLOATSTATUS**

Bu ileti, çerçeve başka bir üst düzey çerçeve penceresi tarafından etkinleştirildiğinde veya devre dışı bırakıldığında, çerçeve penceresine ait tüm açılır pencerelere gönderilir. Bu, bu açılır pencerelerin `CMiniFrameWnd`etkinleştirme üst düzey çerçeve penceresinin aktivasyonu ile senkronize tutmak için MFS_SYNCACTIVE uygulaması tarafından kullanılır.

|||
|-|-|
|Wparam|Aşağıdaki değerlerden biridir:<br /><br /> FS_SHOW<br /><br /> FS_HIDE<br /><br /> FS_ACTIVATE<br /><br /> FS_DEACTIVATE<br /><br /> FS_ENABLEFS_DISABLE<br /><br /> FS_SYNCACTIVE|
|Lparam|Kullanılmaz (0)|

FS_SYNCACTIVE ayarlanmışsa ve pencere etkinleştirmesini ana çerçeveyle eşitlerse, iade değeri sıfırsız olmalıdır. `CMiniFrameWnd`stil MFS_SYNCACTIVE ayarlandığında sıfır sızzı döndürür.

Daha fazla bilgi için, `CMiniFrameWnd`uygulama bakın.

## <a name="wm_activatetoplevel"></a>WM_ACTIVATETOPLEVEL

Bu ileti, "üst düzey grubu" içinde bir pencere etkinleştirildiğinde veya devre dışı bırakıldığında üst düzey bir pencereye gönderilir. Pencere, üst düzey bir pencere (üst veya sahip yoksa) veya böyle bir pencereye aitse, üst düzey bir grubun parçasıdır. Bu ileti WM_ACTIVATEAPP için kullanılan benzer, ancak farklı işlemlere ait pencerelertek bir pencere hiyerarşisinde karışık olduğu durumlarda çalışır (OLE uygulamalarında yaygın).

## <a name="wm_commandhelp-wm_helphittest-wm_exithelpmode"></a>WM_COMMANDHELP, WM_HELPHITTEST, WM_EXITHELPMODE

Bu iletiler, içeriğe duyarlı Yardım'ın uygulanmasında kullanılır. Daha fazla bilgi için lütfen [Teknik Not 28'e](../mfc/tn028-context-sensitive-help-support.md) bakın.

## <a name="mfc-private-resource-formats"></a>MFC Özel Kaynak Biçimleri

Şu anda, MFC iki özel kaynak biçimi tanımlar: RT_TOOLBAR ve RT_DLGINIT.

## <a name="rt_toolbar-resource-format"></a>RT_TOOLBAR Kaynak Biçimi

AppWizard tarafından sağlanan varsayılan araç çubuğu, MFC 4.0'da tanıtılan RT_TOOLBAR özel bir kaynağa dayanır. Bu kaynağı Araç Çubuğu düzenleyicisini kullanarak edinebilirsiniz.

## <a name="rt_dlginit-resource-format"></a>RT_DLGINIT Kaynak Biçimi

Bir MFC özel kaynak biçimi, ek iletişim başlatma bilgilerini depolamak için kullanılır. Bu, açılan bir kutuda depolanan ilk dizeleri içerir. Bu kaynağın biçimi el ile düzenlenecek şekilde tasarlanmaz, ancak Visual C++ tarafından işlenir.

Kaynaktaki bilgileri kullanmak için API alternatifi olduğundan, Visual C++ ve bu RT_DLGINIT kaynağının MFC'nin ilgili özelliklerini kullanması gerekmez. Visual C++ kullanmak, uzun vadede uygulamanızı yazmayı, bakımını ve çevirisini çok daha kolay hale getirir.

RT_DLGINIT kaynağının temel yapısı aşağıdaki gibidir:

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

Yinelenen bir bölüm, iletiyi göndermek için denetim kimliği, gönderilecek İleti # (normal bir Windows iletisi) ve değişken bir veri uzunluğunu içerir. Windows iletisi bir biçimde gönderilir:

```
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);
```

Bu, windows iletilerine ve veri içeriğine izin veren çok genel bir biçimdir. Visual C++ kaynak düzenleyicisi ve MFC yalnızca sınırlı bir Windows ileti alt kümesini destekler: açılan kutular için ilk liste seçenekleri için CB_ADDSTRING (veriler bir metin dizesidir).

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
