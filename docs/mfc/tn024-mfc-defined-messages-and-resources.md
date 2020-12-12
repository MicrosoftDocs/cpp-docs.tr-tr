---
description: 'Daha fazla bilgi edinin: TN024: MFC-Defined Iletileri ve kaynakları'
title: 'TN024: MFC Tanımlı İletiler ve Kaynaklar'
ms.date: 11/04/2016
helpviewer_keywords:
- resources [MFC]
- Windows messages [MFC], MFC-defined
- messages [MFC], MFC
- TN024
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
ms.openlocfilehash: 7ead4d72588b9acae125cbe90be67d1e03230de8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215761"
---
# <a name="tn024-mfc-defined-messages-and-resources"></a>TN024: MFC Tanımlı İletiler ve Kaynaklar

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, MFC tarafından kullanılan iç Windows iletileri ve kaynak biçimleri açıklanmaktadır. Bu bilgiler Framework 'ün uygulamasını açıklar ve uygulamanızda hata ayıklamanıza yardımcı olur. Adventurous için, tüm bu bilgiler resmi olarak desteklenmese de, bu bilgilerin bazılarını gelişmiş uygulamalar için kullanabilirsiniz.

Bu notta MFC özel uygulama ayrıntıları vardır; tüm içerikler gelecekte değişikliğe tabidir. MFC özel Windows iletilerinin anlamı yalnızca bir uygulama kapsamındadır, ancak gelecekte sistem genelinde iletileri içerecek şekilde değişecektir.

MFC özel Windows iletileri ve kaynak türleri aralığı, Microsoft Windows tarafından ayrılan ayrılmış "sistem" aralığıdır. Şu anda aralıklardaki sayıların hepsi kullanılmaz ve gelecekte aralıktaki yeni sayılar kullanılabilir. Şu anda kullanılan sayılar değiştirilebilir.

MFC özel Windows iletileri 0x360->0x37F aralığındadır.

MFC özel kaynak türleri 0xF0->0xFF aralığındadır.

**MFC özel Windows Iletileri**

Bu Windows iletileri, bir C++ sanal işlevinin uygun olmadığı ve pencere nesneleri arasında görece gevşek bir kuponun olması gereken C++ sanal işlevlerinin yerine kullanılır.

Bu özel Windows iletileri ve ilişkili parametre yapıları, ' AFXPRIV ' MFC özel üstbilgisinde bildirilmiştir. H '. Bu üstbilgiyi içeren kodunuzun herhangi birinin belgelenmemiş davranışa bağlı olabileceğini ve büyük olasılıkla MFC 'nin gelecek sürümlerinde kesintiye uğraamayacaklarını unutmayın.

Bu iletilerden birini işlemeye ihtiyaç duyan nadir durumlarda, ON_MESSAGE ileti eşleme makrosunu kullanmanız ve iletiyi genel LRESULT/WPARAM/LPARAM biçiminde işlemeniz gerekir.

**WM_QUERYAFXWNDPROC**

Bu ileti oluşturulmakta olan bir pencereye gönderilir. Bu, WndProc 'ın AfxWndProc olup olmadığını belirleme yöntemi olarak oluşturma sürecinde çok erken gönderilir **. AfxWndProc** 1 döndürür.

| Parametreler ve dönüş değeri | Açıklama |
|-|-|
|wParam|Kullanılmıyor|
|lParam|Kullanılmıyor|
|dizisi|**AfxWndProc** tarafından işlendiğinde 1|

**WM_SIZEPARENT**

Bu ileti, bir çerçeve penceresi tarafından, yeniden boyutlandırma sırasında ( `CFrameWnd::OnSize` `CFrameWnd::RecalcLayout` hangi çağrıları çağırır `CWnd::RepositionBars` ), çerçevenin yanındaki denetim çubuklarının konumunu yeniden konumlandırmak için bir çerçeve penceresi tarafından gönderilir. AFX_SIZEPARENTPARAMS yapısı, üst öğenin kullanılabilir geçerli istemci dikdörtgenini ve bir HDWP (NULL olabilir) ve yeniden `DeferWindowPos` boyanmanın en aza indirilmesine yönelik çağrı içerir.

| Parametreler ve dönüş değeri | Açıklama |
|-|-|
|wParam|Kullanılmıyor|
|lParam|AFX_SIZEPARENTPARAMS yapısının adresi|
|dizisi|Kullanılmıyor (0)|

İletiyi yoksaymak pencerenin mizanpajda bir parçası olmayacağını gösterir.

**WM_SETMESSAGESTRING**

Bu ileti, durum çubuğundaki ileti satırını güncelleştirmesini istemek için bir çerçeve penceresine gönderilir. Dize KIMLIĞI veya bir LPCSTR belirtilebilir (her ikisi birden değil).

| Parametreler ve dönüş değeri | Açıklama |
|-|-|
|wParam|Dize KIMLIĞI (veya sıfır)|
|lParam|Dize için LPCSTR (veya NULL)|
|dizisi|Kullanılmıyor (0)|

**WM_IDLEUPDATECMDUI**

Bu ileti, Update-Command UI işleyicilerinin boşta kalma süresi güncelleştirmesini uygulamak için boşta zamanlı olarak gönderilir. Pencere (genellikle bir denetim çubuğu) iletiyi işlediğinde, bu, `CCmdUI` penceredeki bir nesne (ya da türetilmiş bir sınıfın nesnesi) ve `CCmdUI::DoUpdate` her bir "öğe" için çağrı oluşturur. Bu, komut işleyici zincirindeki nesneler için bir ON_UPDATE_COMMAND_UI işleyicisini denetler.

| Parametreler ve dönüş değeri | Açıklama |
|-|-|
|wParam|BOOL bDisableIfNoHandler|
|lParam|Kullanılmıyor (0)|
|dizisi|Kullanılmıyor (0)|

ON_UPDATE_COMMAND_UI veya ON_COMMAND işleyicisi yoksa, UI nesnesini devre dışı bırakmak için *Bdisableifnohandler* sıfır dışında bir değer.

**WM_EXITHELPMODE**

Bu ileti, `CFrameWnd` bağlama duyarlı yardım modundan çıkmak için bir öğesine gönderilir. Bu iletinin alınması, tarafından başlatılan kalıcı döngüyü sonlandırır `CFrameWnd::OnContextHelp` .

| Parametre ve dönüş değeri | Açıklama |
|-|-|
|wParam|Kullanılmıyor (0)|
|lParam|Kullanılmıyor (0)|
|dizisi|Kullanılmıyor|

**WM_INITIALUPDATE**

Bu ileti, belge şablonu tarafından, ilk güncelleştirmesini yapmak için güvenli olduğunda bir çerçeve penceresinin tüm alt öğeleri tarafından gönderilir. Bir çağrısıyla eşleşir `CView::OnInitialUpdate` , ancak başka `CWnd` bir görüntü güncelleştirme için diğer türetilmiş sınıflarda kullanılabilir.

| Parametreler ve dönüş değeri | Açıklama |
|-|-|
|wParam|Kullanılmıyor (0)|
|lParam|Kullanılmıyor (0)|
|dizisi|Kullanılmıyor (0)|

**WM_RECALCPARENT**

Bu ileti, `GetParent` bir düzen yeniden hesaplamasının (genellikle üst öğe çağrılır) zorlamak için üst penceresine (aracılığıyla elde edilen) bir görünüm tarafından gönderilir `RecalcLayout` . Bu, görünümün toplam boyutu büyüdükçe Çerçevenin boyutunu büyüdüğü, OLE sunucu uygulamalarında kullanılır.

Üst pencere bu iletiyi işliyorsa, doğru döndürmelidir ve lParam içinde geçirilen RECT öğesini istemci alanının yeni boyutuyla doldurmanız gerekir. Bu, `CScrollView` bir sunucu nesnesi yerinde etkinleştirildiğinde kaydırma çubuklarını doğru bir şekilde işlemek için (eklendiğinde pencerenin dışına yerleştir) kullanılır.

| Parametreler ve dönüş değeri | Açıklama |
|-|-|
|wParam|Kullanılmıyor (0)|
|lParam|LPRECT rectClient, NULL olabilir|
|dizisi|Yeni istemci dikdörtgeni döndürülürse TRUE, aksi takdirde FALSE|

**WM_SIZECHILD**

Bu ileti, `COleResizeBar` `GetOwner` Kullanıcı yeniden boyutlandırma tutamaçlarını yeniden boyutlandırma tutamaçlarıyla yeniden boyutlandırdığında, sahibi penceresine (aracılığıyla) gönderilir. `COleIPFrameWnd` Kullanıcı istediği için çerçeve penceresini yeniden konumlandırmaya çalışırken bu iletiye yanıt verir.

Yeniden boyutlandırma çubuğunu içeren çerçeve penceresine göre istemci koordinatlarıyla verilen yeni dikdörtgen, lParam tarafından belirlenir.

| Parametreler ve dönüş değeri | Açıklama |
|-|-|
|wParam|Kullanılmıyor (0)|
|lParam|LPRECT rectNew|
|dizisi|Kullanılmıyor (0)|

**WM_DISABLEMODAL**

Bu ileti, devre dışı bırakılmakta olan bir çerçeve penceresi tarafından sahip olunan tüm açılır pencerelere gönderilir. Çerçeve penceresi, açılır pencerenin devre dışı bırakılıp başlatılmayacağını belirleme sonucunu kullanır.

Bu, çerçeve kalıcı bir duruma girdiğinde veya belirli açılır pencerelerin devre dışı bırakılmasına izin vermek için açılır pencerenize özel işlem yapmak için kullanabilirsiniz. Araç ipuçları bu iletiyi, çerçeve penceresi örneğin bir kalıcı duruma geçtiğinde yok etmek için kullanır.

| Parametreler ve dönüş değeri | Açıklama |
|-|-|
|wParam|Kullanılmıyor (0)|
|lParam|Kullanılmıyor (0)|
|dizisi|Sıfır olmayan pencere devre dışı **bırakılmayacak** , 0 pencerenin devre dışı bırakılacağını gösterir|

**WM_FLOATSTATUS**

Bu ileti, çerçeve bir başka üst düzey çerçeve penceresi tarafından etkinleştirildiğinde veya devre dışı bırakıldığında bir çerçeve penceresi tarafından sahip olunan tüm açılır pencerelere gönderilir. Bu `CMiniFrameWnd` açılır pencerelerin etkinleştirilmesini, en üst düzey çerçeve penceresinin etkinleştirilmesiyle eşitlenmiş halde tutmak için, ' de MFS_SYNCACTIVE uygulanması tarafından kullanılır.

| Parametreler | Açıklama |
|-|-|
|wParam|Aşağıdaki değerlerden biridir:<br /><br /> FS_SHOW<br /><br /> FS_HIDE<br /><br /> FS_ACTIVATE<br /><br /> FS_DEACTIVATE<br /><br /> FS_ENABLEFS_DISABLE<br /><br /> FS_SYNCACTIVE|
|lParam|Kullanılmıyor (0)|

FS_SYNCACTIVE ayarlandıysa ve pencere etkinleştirmeyi üst kareyle eşitler, dönüş değeri sıfır dışında bir değer olmalıdır. `CMiniFrameWnd` Stil MFS_SYNCACTIVE olarak ayarlandığında sıfır dışında bir değer döndürür.

Daha fazla bilgi için uygulamasının uygulamasına bakın `CMiniFrameWnd` .

## <a name="wm_activatetoplevel"></a>WM_ACTIVATETOPLEVEL

Bu ileti, "üst düzey grubundaki" bir pencere etkinleştirildiğinde veya devre dışı bırakıldığında en üst düzey pencereye gönderilir. Bir pencere, üst düzey bir pencere (üst veya sahip olmadan) veya böyle bir pencereye ait olan üst düzey grubun bir parçasıdır. Bu ileti WM_ACTIVATEAPP için kullanımda benzerdir, ancak farklı işlemlere ait pencerelerin tek bir pencere hiyerarşisinde (OLE uygulamalarında ortak) karışmakta olduğu durumlarda çalışıyor.

## <a name="wm_commandhelp-wm_helphittest-wm_exithelpmode"></a>WM_COMMANDHELP, WM_HELPHITTEST, WM_EXITHELPMODE

Bu iletiler, bağlama duyarlı Yardım uygulamasında kullanılır. Daha fazla bilgi için lütfen [Teknik notun 28](../mfc/tn028-context-sensitive-help-support.md) bölümüne bakın.

## <a name="mfc-private-resource-formats"></a>MFC özel kaynak biçimleri

Şu anda MFC iki özel kaynak biçimi tanımlıyor: RT_TOOLBAR ve RT_DLGINIT.

## <a name="rt_toolbar-resource-format"></a>RT_TOOLBAR kaynak biçimi

AppWizard tarafından sağlanan varsayılan araç çubuğu MFC 4,0 ' de tanıtılan RT_TOOLBAR özel bir kaynağı temel alır. Bu kaynağı araç çubuğu düzenleyicisini kullanarak düzenleyebilirsiniz.

## <a name="rt_dlginit-resource-format"></a>RT_DLGINIT kaynak biçimi

Bir MFC özel kaynak biçimi, ek iletişim kutusu başlatma bilgilerini depolamak için kullanılır. Bu, Birleşik giriş kutusunda depolanan ilk dizeleri içerir. Bu kaynağın biçimi el ile düzenlenecek şekilde tasarlanmamıştır, ancak Visual C++ tarafından işlenir.

Visual C++ ve kaynaktaki bilgileri kullanmanın API alternatifi olduğundan, bu RT_DLGINIT kaynak MFC 'nin ilgili özelliklerini kullanmak için gerekli değildir. Visual C++ kullanmak, uzun çalıştırmada uygulamanızı yazmayı, bakımını ve çevirmenizi çok daha kolay hale getirir.

RT_DLGINIT kaynağın temel yapısı aşağıdaki gibidir:

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

Yinelenen bir bölümde iletinin gönderileceği denetim KIMLIĞI, gönderme Iletisi (normal bir Windows iletisi) ve değişken veri uzunluğu bulunur. Windows iletisi bir biçimde gönderilir:

```
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);
```

Bu, tüm Windows iletilerine ve veri içeriğine izin veren çok genel bir biçimdir. Visual C++ kaynak Düzenleyicisi ve MFC yalnızca sınırlı bir Windows iletileri alt kümesini destekler: Birleşik giriş kutuları için CB_ADDSTRING (veriler bir metin dizesidir).

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
