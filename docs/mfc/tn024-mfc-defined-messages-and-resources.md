---
title: 'TN024: MFC tanımlı iletiler ve kaynaklar | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- resources [MFC]
- Windows messages [MFC], MFC-defined
- messages [MFC], MFC
- TN024
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4dd403693dd860966cfcca42eacc909b01eb513b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385618"
---
# <a name="tn024-mfc-defined-messages-and-resources"></a>TN024: MFC Tanımlı İletiler ve Kaynaklar
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 MFC tarafından kullanılan kaynak biçimlerini ve iç Windows iletileri bu not açıklar. Bu bilgiler uygulama framework'ün açıklar ve uygulamanızın hatalarını ayıklama yardımcı olacaktır. Bu bilgiler resmi olarak desteklenmeyen olsa bile adventurous için bu bilgilerin bazıları Gelişmiş uygulamalar için kullanabilirsiniz.  
  
 Bu Not MFC özel uygulama ayrıntılarını içerir; tüm içeriği değiştirilebilir gelecekte olduğundan. MFC özel Windows iletileri yalnızca bir uygulama kapsamında anlama sahip ancak gelecekte sistem genelinde iletileri içerecek şekilde değişir.  
  
 Kaynak türleri ve aralığı, MFC özel Windows iletilerini ayrılmış "Sistem" aralığında kenara Microsoft Windows tarafından ayarlanır. Aralıkları şu anda tüm sayılar kullanılır ve yeni numaraları aralığında gelecekte kullanılabilir. Şu anda kullanılan sayıları değiştirilebilir.  
  
 MFC özel Windows iletileri 0x360 aralığındadır 0x37F ->.  
  
 MFC özel kaynak türleri 0xF0 aralığındadır 0xFF ->.  
  
 **MFC özel Windows iletileri**  
  
 Bu Windows iletilerini görece gevşek bağlantı pencere nesneleri arasındaki ve burada C++ sanal işlev uygun olmayacaktır gerekli olduğu C++ sanal işlevleri yerine kullanılır.  
  
 Bu özel Windows iletileri ve ilişkili parametre yapıları MFC özel üst bilgi bildirilir ' AFXPRIV. H'. Bu üst bilgiyi içeren kodunuzu hiçbirini belgelenmemiş davranış ve büyük olasılıkla sonu gelecekte MFC sürümleri bağlı olduğunu uyarılmak.  
  
 Bu iletiler birini işlemek ihtiyacı nadir durumlarda, kullanmanız gereken `ON_MESSAGE` ileti eşlemesi makrosu ve genel WPARAM/LRESULT/LPARAM biçiminde ileti işleme.  
  
 **WM_QUERYAFXWNDPROC**  
  
 Bu ileti oluşturuluyor bir pencere için gönderilir. Bu çok erken oluşturma işleminde WndProc ise belirleme yöntemi olarak gönderilen **AfxWndProc. AfxWndProc** 1 döndürür.  
  
|||  
|-|-|  
|wParam|Kullanılan değil|  
|lParam|Kullanılan değil|  
|dizisi|tarafından işlenen 1 **AfxWndProc**|  
  
 **WM_SIZEPARENT**  
  
 Bu iletiyi yeniden boyutlandırma sırasında bir çerçeve pencere tarafından hemen alt gönderilen (**CFrameWnd::OnSize** çağrıları `CFrameWnd::RecalcLayout` çağıran `CWnd::RepositionBars`) çerçeve tarafında geçici denetim çubukları yeniden konumlandırmak için. **AFX_SIZEPARENTPARAMS** yapısı çağırmak, geçerli kullanılabilir istemci dikdörtgenin üst ve (aynı NULL olabilir) bir HDWP içeren `DeferWindowPos` yeniden çizerken en aza indirmek için.  
  
|||  
|-|-|  
|wParam|Kullanılan değil|  
|lParam|Adres bir **AFX_SIZEPARENTPARAMS** yapısı|  
|dizisi|(0) kullanılmıyor|  
  
 İleti yoksayılıyor penceresi düzende bölümü almaz gösterir.  
  
 **WM_SETMESSAGESTRING**  
  
 Bu ileti durum çubuğundaki ileti satırı güncelleştirmek için sormak için bir çerçeve penceresinde gönderilir. Dize kimliği ya da bir LPCSTR belirtilmelidir (ancak ikisi birden değil) olabilir.  
  
|||  
|-|-|  
|wParam|Kimliği (veya sıfır) dize|  
|lParam|LPCSTR dize (veya NULL)|  
|dizisi|(0) kullanılmıyor|  
  
 **WM_IDLEUPDATECMDUI**  
  
 Bu ileti, güncelleştirme komutu UI işleyicileri boşta kalma süresi güncelleştirmeyi uygulamak için boşta kalma süresi gönderilir. Pencerenin (genellikle bir denetim çubuğu) iletiyi işleyen, oluşturduğu bir `CCmdUI` (veya türetilmiş bir sınıf, nesne) ve arama **CCmdUI::DoUpdate** her penceresinde "öğesi". Bu sırayla denetler bir `ON_UPDATE_COMMAND_UI` komut işleyici zinciri içindeki nesneler için işleyici.  
  
|||  
|-|-|  
|wParam|BOOL bDisableIfNoHandler|  
|lParam|(0) kullanılmıyor|  
|dizisi|(0) kullanılmıyor|  
  
 *bDisableIfNoHandler* varsa ne UI nesne devre dışı bırakmak için sıfır olmayan olan bir `ON_UPDATE_COMMAND_UI` ya da bir `ON_COMMAND` işleyicisi.  
  
 **WM_EXITHELPMODE**  
  
 Bu ileti için gönderilen bir `CFrameWnd` bağlama duyarlı çıkmak için Yardım modu. Bu iletinin alınması, başlatan kalıcı döngü sona erer **CFrameWnd::OnContextHelp.**  
  
|||  
|-|-|  
|wParam|(0) kullanılmıyor|  
|lParam|(0) kullanılmıyor|  
|dizisi|Kullanılan değil|  
  
 **WM_INITIALUPDATE**  
  
 Bunları kendi ilk güncelleştirme yapmak güvenli olduğunda bu iletiyi bir çerçeve penceresinde tüm bağımlı öğelerini belge şablonu tarafından gönderilir. Çağrı eşlendiği `CView::OnInitialUpdate` ancak diğer kullanılabilir `CWnd`-türetilmiş sınıfları diğer tek adımda güncelleştirmek için.  
  
|||  
|-|-|  
|wParam|(0) kullanılmıyor|  
|lParam|(0) kullanılmıyor|  
|dizisi|(0) kullanılmıyor|  
  
 **WM_RECALCPARENT**  
  
 Bu ileti bir görünüm tarafından kendi üst penceresi gönderilir (aracılığıyla elde `GetParent`) düzenini yeniden hesaplama zorlamak için (üst genellikle çağıracak `RecalcLayout`). OLE sunucu uygulamaları çerçeve görünümün toplam boyutu büyüdükçe boyutları büyürken gerekli olduğu kullanılır.  
  
 Üst pencere bu ileti işlediğinde, TRUE döndürür ve istemci alanının yeni boyutuyla lParam geçirilen RECT doldurun. Bu kullanılan `CScrollView` scrollbars (sonra eklendiklerinde penceresi dışındaki bir yerde) düzgün bir şekilde işlemek için bir sunucu nesnesi olduğunda yerinde etkinleştirildi.  
  
|||  
|-|-|  
|wParam|(0) kullanılmıyor|  
|lParam|LPRECT rectClient NULL olabilir|  
|dizisi|TRUE yeni istemci dikdörtgen döndürülen FALSE Aksi takdirde|  
  
 **WM_SIZECHILD**  
  
 Bu ileti tarafından gönderilen `COleResizeBar` onun sahibi penceresine (aracılığıyla `GetOwner`) kullanıcının yeniden boyutlandırma yeniden boyutlandırma çubuğunda ne zaman yeniden boyutlandırır. `COleIPFrameWnd` Bu ileti kullanıcının istediği gibi çerçeve penceresi yeniden konumlandırmak deneyerek yanıt verir.  
  
 Yeniden boyutlandırma çubuğunu içeren çerçeve penceresi göre istemci koordinatlar verilen dikdörtgenin yeni adresindeki lParam tarafından verilir.  
  
|||  
|-|-|  
|wParam|(0) kullanılmıyor|  
|lParam|LPRECT rectNew|  
|dizisi|(0) kullanılmıyor|  
  
 **WM_DISABLEMODAL**  
  
 Bu iletiyi devre dışı bırakılıyor bir çerçeve penceresinde tarafından sahip olunan tüm açılır pencereleri gönderilir. Çerçeve penceresi sonucu açılır penceresi devre dışı gerekip gerekmediğini belirlemek için kullanır.  
  
 Bu çerçeve kalıcı durumuna girdiğinde açılır pencerede özel işlem gerçekleştirmek için veya belirli açılır pencereleri devre dışı tutmak için kullanabilirsiniz. Araç ipuçları çerçeve penceresi örneğin kalıcı bir duruma geçtiğinde kendilerini yok etmek için bu iletiyi kullanın.  
  
|||  
|-|-|  
|wParam|(0) kullanılmıyor|  
|lParam|(0) kullanılmıyor|  
|dizisi|Sıfır dışı **değil** penceresi devre dışı bırakmak, 0 gösteren pencereyi devre dışı bırakılacak|  
  
 **WM_FLOATSTATUS**  
  
 Bu ileti çerçeve etkinleştirilmiş veya başka bir üst düzey çerçeve penceresi tarafından devre dışı bir çerçeve pencere tarafından ait tüm açılır pencereleri gönderilir. Bu uygulama tarafından kullanılan **MFS_SYNCACTIVE** içinde `CMiniFrameWnd`, bu açılır pencereleri etkinleştirme üst düzey çerçeve penceresi etkinleştirme ile eşitlenmiş tutmak için.  
  
|||  
|-|-|  
|wParam|Aşağıdaki değerlerden biri:<br /><br /> **FS_SHOW**<br /><br /> **FS_HIDE**<br /><br /> **FS_ACTIVATE**<br /><br /> **FS_DEACTIVATE**<br /><br /> **FS_ENABLEFS_DISABLE**<br /><br /> **FS_SYNCACTIVE**|  
|lParam|(0) kullanılmıyor|  
  
 Dönüş değeri sıfır olmalıdır, **FS_SYNCACTIVE** ve pencere bölmeye kendi üst çerçeve etkinleştirmede topluluğudur. `CMiniFrameWnd` Stil ayarlandığında sıfır verir **MFS_SYNCACTIVE.**  
  
 Daha fazla bilgi için bkz: `CMiniFrameWnd`.  
  
## <a name="wmactivatetoplevel"></a>WM_ACTIVATETOPLEVEL  
 Kendi "üst düzey grup" penceresinde da etkinleştirilmiş devre dışı ya da bu iletiyi üst düzey bir pencere için gönderilir. Bir pencere, üst düzey bir pencere (üst veya sahibi) ise veya böyle bir pencereye ait en üst düzey bir grubun parçası olan. Bu ileti kullanmak için benzer **WM_ACTIVATEAPP,** ancak burada farklı işlemler ait windows karma (OLE uygulamalarında ortak) tek bir pencere hiyerarşideki durumlarda çalışır.  
  
## <a name="wmcommandhelp-wmhelphittest-wmexithelpmode"></a>WM_COMMANDHELP, WM_HELPHITTEST, WM_EXITHELPMODE  
 Bu iletiler bağlama duyarlı Yardım uygulamasında kullanılır. Lütfen [Teknik Not 28](../mfc/tn028-context-sensitive-help-support.md) daha fazla bilgi için.  
  
## <a name="mfc-private-resource-formats"></a>MFC özel kaynak biçimleri  
 Şu anda iki özel kaynak biçimlerini MFC tanımlar: **RT_TOOLBAR** ve **RT_DLGINIT**.  
  
## <a name="rttoolbar-resource-format"></a>RT_TOOLBAR kaynağı biçimi  
 AppWizard tarafından sağlanan varsayılan araç dayalı bir **RT_TOOLBAR** MFC 4. 0'tanıtılan özel kaynak. Araç çubuğu Düzenleyicisi'ni kullanarak bu kaynak düzenleyebilirsiniz.  
  
## <a name="rtdlginit-resource-format"></a>RT_DLGINIT kaynak biçimi  
 Bir MFC özel kaynak biçimi ek iletişim başlatma bilgileri depolamak için kullanılır. Bu, açılan kutuda depolanan ilk dizeleri içerir. Bu kaynak biçimi el ile düzenlenmek üzere tasarlanmamıştır, ancak Visual C++ tarafından işlenir.  
  
 Visual C++ ve bu **RT_DLGINIT** kaynak API alternatif kaynak bilgileri kullanarak olduğundan MFC ilgili özelliklerini kullanmak için gerekli değildir. Visual C++ kullanarak çok yazma, korumanıza ve uygulamanızı uzun vadede Çevir kolaylaştırır.  
  
 Temel yapısını bir **RT_DLGINIT** kaynak aşağıdaki gibidir:  
  
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
  
 İleti göndermek için denetim kimliği yinelenen bir bölüm içeren ileti gönder (normal bir Windows ileti) ve değişken uzunlukta veri #. Windows ileti bir formda gönderilir:  
  
```  
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);
```  
  
 Windows iletileri ve veri içeriği izin vererek çok genel bir biçim budur. Visual C++ kaynak düzenleyici ve MFC Windows iletilerini sınırlı bir alt kümesinde yalnızca destekler: ilk liste seçenekleri (verileri olan bir metin dizesi) birleşik giriş kutuları için CB_ADDSTRING.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

