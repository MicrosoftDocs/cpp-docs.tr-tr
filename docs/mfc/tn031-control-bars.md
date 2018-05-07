---
title: 'TN031: Denetim çubukları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.controls.bars
dev_langs:
- C++
helpviewer_keywords:
- control bars [MFC], styles
- CStatusBar class [MFC], Tech Note 31 usage
- CControlBar class [MFC], Tech Note 31 usage
- CControlBar class [MFC], deriving from
- control bars [MFC], classes [MFC]
- CDialogBar class [MFC], Tech Note 31 usage
- CToolBar class [MFC], Tech Note 31 usage
- TN031
- styles [MFC], control bars
ms.assetid: 8cb895c0-40ea-40ef-90ee-1dd29f34cfd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1d5cc113177a9653e709c14f66682959276e7ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tn031-control-bars"></a>TN031: Denetim Çubukları
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 MFC içinde denetim çubuğu sınıfları bu not açıklar: Genel [CControlBar](#_mfcnotes_ccontrolbar), [CStatusBar](#_mfcnotes_cstatusbar), [CToolBar](#_mfcnotes_ctoolbar), [CDialogBar](#_mfcnotes_cdialogbar)ve  **CDockBar**.  
  
## <a name="_mfcnotes_ccontrolbar"></a> CControlBar 
  
 A **ControlBar** olan bir `CWnd`-türetilen, sınıf:  
  
-   Üst veya alt çerçeve penceresi hizalanır.  
  
-   Her iki HWND tabanlı denetimler alt öğeler içerebilir (örneğin, `CDialogBar`) olmayan veya -`HWND` öğeleri alan (örneğin, `CToolBar`, `CStatusBar`).  
  
 Denetim çubukları ek stillerini destekler:  
  
- `CBRS_TOP` (Varsayılan) üst denetim çubuğuna Sabitle.  
  
- `CBRS_BOTTOM` Denetim çubuğu altına sabitleyin.  
  
- `CBRS_NOALIGN` Denetim çubuğu üst yeniden boyutlandırır olduğunda yeniden konumlandırmak değil.  
  
 Türetilmiş sınıflar `CControlBar` daha ilginç uygulamaları sağlayın:  
  
- `CStatusBar` Durum çubuğu metni içeren durum çubuğu bölmeleri öğelerdir.  
  
- `CToolBar` Araç, bir satırda hizalı bit eşlem düğmeler öğelerdir.  
  
- `CDialogBar` Standart windows içeren bir araç benzeri çerçevesi denetimleri (bir iletişim şablonunu kaynaktan oluşturulur).  
  
- **CDockBar** genelleştirilmiş bir yerleştirme alanında diğer `CControlBar` türetilmiş nesneleri. Özel üye işlevleri ve değişkenler bu sınıfta kullanılabilir gelecek sürümlerde değişmesi olasılığı olan.  
  
 Tüm denetim çubuğu nesneleri/windows bazı üst çerçeve penceresinin alt öğe pencerelerini olacaktır. Bunlar genellikle bir eşdüzeyi (örneğin, bir MDI istemci veya Görünüm) çerçeve istemci alanına eklenir. Denetim çubuğu alt pencere Kimliğini önemlidir. Denetim çubuğu varsayılan düzenini yalnızca aralığında denetim çubukları kimlikleri için çalışır **AFX_IDW_CONTROLBAR_FIRST** için **AFX_IDW_CONTROLBAR_LAST**. 256 denetimi aralığını olsa bile unutmayın doğrudan Baskı Önizleme mimarisi tarafından desteklenen beri kimlikleri, bu denetim çubuğunun ilk 32 kimlikleri özel.  
  
 `CControlBar` Sınıfı için standart uygulaması sağlar:  
  
-   Denetim çubuğu üst, alt ya da her iki yanına çerçevenin hizalama.  
  
-   Denetim öğesi diziler ayrılıyor.  
  
-   Türetilen sınıflar uyarlamasını destekleme.  
  
 C++ denetim çubuğu genellikle katıştırılmış nesneler üye olarak bir `CFrameWnd` türetilmiş sınıf ve zaman temizlenecek üst `HWND` ve nesnesi kaybolur. Denetim çubuğu nesnesi yığınındaki ayırma ihtiyacınız varsa, sadece ayarlayabileceğiniz **m_bAutoDestruct** üyesine **TRUE** denetim çubuğu yapmak için "**bu silme**" olduğunda `HWND` yok.  
  
> [!NOTE]
>  Kendi oluşturursanız `CControlBar`-yerine MFC'nin birini kullanarak türetilmiş gibi sınıfları, türetilmiş sınıf, `CStatusBar`, `CToolBar`, veya `CDialogBar`, ayarlamanız gerekir `m_dwStyle` veri üyesi. Bu geçersiz kılma yapılabilir **oluşturma**:  
  
```  
// CMyControlBar is derived from CControlBar  
BOOL CMyControlBar::Create(CWnd* pParentWnd,
    DWORD dwStyle,
    UINT nID)  
{  
    m_dwStyle = dwStyle;  
 
 .  
 .  
 .  
}  
```  
  
 **Denetim çubuğu düzeni algoritmasını**  
  
 Denetim çubuğu düzeni algoritmasını çok kolaydır. Çerçeve penceresi ileti gönderir **WM_SIZEPARENT** denetim çubuğu aralığındaki tüm alt öğeleri için. Bu ileti yanı sıra, üst öğenin istemci dikdörtgen bir işaretçi geçirilir. Bu ileti Z düzeninde alt gönderilir. Denetim çubuğu alt kendilerini getirin ve üst öğenin istemci alanının boyutunu azaltmak için bu bilgileri kullanın. (Daha az denetim çubukları) normal istemci alanı için sol son dikdörtgen ana istemci pencerede (genellikle bir MDI istemci, görünümü veya Bölümlendirici pencere) yerleştirmek için kullanılır.  
  
 Bkz: `CWnd::RepositionBars` ve `CFrameWnd::RecalcLayout` daha fazla ayrıntı için.  
  
 Dahil olmak üzere MFC özel Windows iletiler, **WM_SIZEPARENT**, belgelenmiştir [Teknik Not 24](../mfc/tn024-mfc-defined-messages-and-resources.md).  
  
## <a name="_mfcnotes_cstatusbar"></a>  CStatusBar  
  
 Durum çubuğu metni çıkış bölmeleri satırının olan denetim çubuğu ' dir. Metin çıktısı bölmeleri kullanmak için iki genel yolu vardır:  
  
-   İleti satırı  
  
     (örneğin, standart menü Yardım iletisi satırı). Bunlar genellikle 0 tabanlı bir tarafından dizine erişilen  
  
-   Durum göstergeleri  
  
     (örneğin, büyük harf, sayı ve SCRL göstergeleri). Bunlar genellikle dize/komut kimliği tarafından erişilen  
  
 Durum çubuğu yazı tipini 10 noktası MS Sans Serif (Windows arabirimi uygulama Tasarım Kılavuzu'na veya 10 noktası İsviçre orantılı yazı tipinin yazı tipi mappers en iyi eşleşmeyi tarafından belirlenir) olur. Belirli Windows sürümlerinde, Japonca sürümü gibi seçmiş olduğunuz yazı tiplerini farklıdır.  
  
 Durum çubuğunda da kullanılan renkleri, aynı zamanda Windows arabirimi uygulama tasarım kılavuzu öneri ile tutarlı değil. Bu renkleri olmayan sabit kodlanmış ve yanıt olarak Denetim Masası'ndaki kullanıcı özelleştirme dinamik olarak değiştirilebilir.  
  
|Öğe|Windows renk değeri|Varsayılan RGB|  
|----------|-------------------------|-----------------|  
|Durum çubuğu arka plan|**COLOR_BTNFACE**|RGB (192, 192, 192)|  
|Durum çubuğu metni|**COLOR_BTNTEXT**|RGB (000 000, 000)|  
|Durum çubuğu sol üst kenarları|**COLOR_BTNHIGHLIGHT**|RGB (255 255, 255)|  
|Durum çubuğu bot/sağ kenarları|**COLOR_BTNSHADOW**|RGB (128, 128, 128)|  
  
 **CStatusBar Ccmduı desteği**  
  
 Göstergeleri genellikle güncelleştirilmiş yolunu `ON_UPDATE_COMMAND_UI` mekanizması. Boşta kalma süresi üzerinde durum çubuğu çağıracak `ON_UPDATE_COMMAND_UI` işleyici gösterge bölmesindeki dize kimliği.  
  
 `ON_UPDATE_COMMAND_UI` İşleyici çağırabilirsiniz:  
  
- **Etkinleştirme**: etkinleştirme veya devre dışı bölmesi. Devre dışı bırakılmış bir bölme tam olarak bir etkin bölmesi gibi görünüyor, ancak metin görünmezdir (diğer bir deyişle, metin göstergesi devre dışı bırakır).  
  
- **SetText**: metni değiştirmek için. Bölmesinde değil otomatik olarak yeniden boyutlandırılır çünkü bu kullanırsanız, dikkatli olun.  
  
 Sınıfa başvurmak [CStatusBar](../mfc/reference/cstatusbar-class.md) içinde *sınıf kitaplığı başvurusu* hakkındaki ayrıntılar için `CStatusBar` oluşturma ve özelleştirme API'leri. Durum çubukları çoğu özelleştirmesini durum çubuğu başlangıçta görünür hale gelir önce yapılmalıdır.  
  
 Durum çubuğu yalnızca bir stretchy bölmesi, genellikle ilk destekler. Bu bölme gerçekten en küçük boyut boyutudur. Durum çubuğu tüm bölmeleri minimum boyuttan daha büyükse, herhangi bir ek genişlik stretchy bölmesine verilir. Birinci bölmesi stretchy olduğundan durum çubuğu varsayılan uygulamayla sağa hizalı göstergeleri büyük harf, sayı ve SCRL sahiptir.  
  
## <a name="_mfcnotes_ctoolbar"></a>  CToolBar  
  
 Bir araç çubuğu denetim çubuğu satır ayırıcı içerebilir bit eşlem düğmelerini bulunur. İki stili düğmelerinin desteklenir: pushbuttons ve onay kutusu düğmeler. Radyo Grup işlevlerini onay kutusunu düğmeleriyle oluşturulabilir ve `ON_UPDATE_COMMAND_UI`.  
  
 Araç çubuğundaki tüm bit eşlem düğmeleri bir bit eşlem alınır. Bu bit eşlemi bir görüntü veya her düğme için karakter içermelidir. Genellikle bit eşlem görüntüleri/metindeki ekranda düzenleneceği aynı sırada sırasıdır. (Bu özelleştirme API'leri kullanılarak değiştirilebilir.)  
  
 Her düğme aynı boyutta olmalıdır. Standart 24 x 22 piksel varsayılandır. Her görüntü/karakter aynı boyutta olmalıdır ve yan yana olmalıdır bit eşlemde. Varsayılan görüntü/simge boyutu 16 x 15 pikseldir. İçin bir araç çubuğu (standart boyutları kullanarak) 10 düğmelerle, bu nedenle, 160 piksel genişliğinde ve 15 piksel yüksek bir bit eşlem gerekir.  
  
 Her düğme tek bir görüntü/karakter var. Farklı bir düğmeyi durumları ve stilleri (basılı, yukarı, örneğin, aşağı, devre dışı, aşağı, belirsiz devre dışı) tek bir görüntü/karakter algorithmically oluşturulur. Herhangi bir renk bit eşlem veya DIB teorik olarak kullanılabilir. Özgün görüntüsüne gri ise farklı bir düğmeyi oluşturmak için algoritma works en iyi belirtir. Standart araç çubuğu düğmeleri ve MFC genel örnek sağlanan araç çubuğu düğmesi küçük resim bakın [küçük resim](../visual-cpp-samples.md) örnekleri için.  
  
 Araç çubuğunda kullanılan renkleri ayrıca Windows arabirimi uygulama tasarım kılavuzu öneri ile tutarlı değil. Bu renkleri olmayan sabit kodlanmış ve yanıt olarak Denetim Masası'ndaki kullanıcı özelleştirme dinamik olarak değiştirilebilir.  
  
|Öğe|Windows renk değeri|Varsayılan RGB|  
|----------|-------------------------|-----------------|  
|Araç çubuğu arka plan|**COLOR_BTNFACE**|RGB(192,192,192)|  
|Sol üst kenarları araç çubuğu düğmeleri|**COLOR_BTNHIGHLIGHT**|RGB(255,255,255)|  
|Bot/sağ kenarları araç çubuğu düğmeleri|**COLOR_BTNSHADOW**|RGB(128,128,128)|  
  
 Ayrıca, standart Windows düğmesi denetimleri gibi davranarak bit eşlem düğmeler nasıl. Bit eşlem kaynaktan ve yanıt sistem renkleri Denetim Masası'ndaki kullanıcı özelleştirme yanıtta bir değişiklik olarak yüklendiğinde bu yeniden renklendirme oluşur. Dikkatli kullanılması gereken şekilde araç bit eşlem aşağıdaki renkleri otomatik olarak nasıl. Bir kısmı nasıl, bit eşlem olmasını istemiyorsanız yakından eşlenen RGB değerleri birini benzeyen bir renk kullanın. Eşleme RGB değerleri tam göre yapılır.  
  
|RGB değeri|Dinamik olarak eşlenmiş renk değeri|  
|---------------|------------------------------------|  
|RGB (000 000, 000)|COLOR_BTNTEXT|  
|RGB (128, 128, 128)|COLOR_BTNSHADOW|  
|RGB (192, 192, 192)|COLOR_BTNFACE|  
|RGB (255 255, 255)|COLOR_BTNHIGHLIGHT|  
  
 Sınıfa başvurmak [CToolBar](../mfc/reference/ctoolbar-class.md) *sınıf kitaplığı başvurusu* hakkındaki ayrıntılar için `CToolBar` oluşturma ve özelleştirme API'leri. Çoğu araç çubuklarını özelleştirme araç başlangıçta görünür hale gelir önce yapılmalıdır.  
  
 API, kimlikleri, stiller, düğme ayarlamak için kullanılabilir özelleştirme ayırıcı genişlik ve hangi görüntü/karakter hangi düğmesi için kullanılır. Varsayılan olarak bu API'leri kullanın gerekmez.  
  
## <a name="ccmdui-support-for-ctoolbar"></a>CToolBar Ccmduı desteği  
 Araç çubuğu düğmeleri her zaman güncel yolunu `ON_UPDATE_COMMAND_UI` mekanizması. Boşta kalma süresi üzerinde araç çağıracak `ON_UPDATE_COMMAND_UI` işleyici bu düğme komut kimliği. `ON_UPDATE_COMMAND_UI` Ayırıcılar için çağrılmaz ancak pushbuttons ve onay kutusu düğmeleri için çağrılır.  
  
 `ON_UPDATE_COMMAND_UI` İşleyici çağırabilirsiniz:  
  
- **Etkinleştirme**: etkinleştirmek veya düğmesi devre dışı bırakmak için. Bu eşit pushbuttons ve onay kutusu düğmeleri için çalışır.  
  
- `SetCheck`: Bir düğme onay durumunu ayarlamak için. Bu araç çubuğu düğmesi için çağrılırken bir onay kutusu düğmesinde açar. `SetCheck` (işaretli) 0, 1 (işaretli) veya 2 (belirsiz) olabilen bir parametre alır  
  
- `SetRadio`: İçin toplu `SetCheck`.  
  
 Onay kutusu düğmelerinin "AUTO" onay kutusunu düğme vardır; kullanıcı bunları bastığında diğer bir deyişle, bunlar hemen durumu değişir. Aşağı veya basılı durumu denetlenir. Bir düğme "belirsiz" durumuna değiştirmek için yerleşik kullanıcı arabirimi yolu yoktur; Bu kod yapılmalıdır.  
  
 API özelleştirme verilen araç çubuğu düğmesi durumunu değiştirmenize izin verecek, bu durumda tercihen değiştirmelisiniz `ON_UPDATE_COMMAND_UI` araç çubuğu düğmesi nesnesini temsil eden komutu için işleyici. Unutmayın, boşta işleme araç çubuğu düğmeleri ile durumunu değiştirir `ON_UPDATE_COMMAND_UI` SetButtonStyle yapılan bu durumu değişiklikleri sonra sonraki kayıp alabilirsiniz şekilde işleyici boş.  
  
 Araç çubuğu düğmeleri gönderecek **WM_COMMAND** iletileri normal düğmeleri veya menü öğeleri gibi ve normal şekilde tarafından işlenen bir `ON_COMMAND` sağlayan aynı sınıf işleyicisinde `ON_UPDATE_COMMAND_UI` işleyicisi.  
  
 Görüntü durumları için kullanılan dört araç çubuğu düğmesi stilleri (TBBS_ değerler) vardır:  
  
-   TBBS_CHECKED: onay kutusunu (aşağı) şu anda denetlenir.  
  
-   TBBS_INDETERMINATE: onay kutusunu şu anda belirsiz.  
  
-   TBBS_DISABLED: Şu anda düğmesi devre dışıdır.  
  
-   TBBS_PRESSED: Şu anda düğmesine basıldığında.  
  
 Altı resmi Windows arabirimi uygulama tasarım kılavuzu düğme stilleri aşağıdaki TBBS değerlerle gösterilir:  
  
-   En fazla = 0  
  
-   Fare aşağı TBBS_PRESSED = (&#124; başka bir stil)  
  
-   Devre dışı TBBS_DISABLED =  
  
-   Aşağı TBBS_CHECKED =  
  
-   TBBS_CHECKED = devre dışı &#124; TBBS_DISABLED  
  
-   Belirsiz TBBS_INDETERMINATE =  
  
##  <a name="_mfcnotes_cdialogbar"></a> CDialogBar  
 Bir iletişim çubuğu standart Windows denetimleri içeren denetim çubuğu ' dir. Denetimleri içerir ve bunlar arasında sekmeyle gitmeyi destekleyen bir iletişim kutusu gibi davranır. Çubuğunu göstermek için bir iletişim şablonunu kullanır, ayrıca bir iletişim kutusu gibi davranır.  
  
 A `CDialogBar` standart basma düğmesi denetimleri içeren Baskı Önizleme araç için kullanılır.  
  
 Kullanarak bir `CDialogBar` kullanmaktır gibi bir `CFormView`. İletişim çubuğu için bir iletişim şablonunu tanımlayın ve dışındaki tüm stilleri kaldırmak **WS_CHILD**. İletişim kutusu görünür olmamalıdır unutmayın.  
  
 Denetim bildirimleri için bir `CDialogBar` (gibi araç çubuğu düğmeleri) denetim çubuğunun üst gönderilir.  
  
## <a name="ccmdui-support-for-cdialogbar"></a>CDialogBar Ccmduı desteği  
 İletişim kutusu çubuğu düğmelerini aracılığıyla güncelleştirilmesi gerektiğini `ON_UPDATE_COMMAND_UI` işleyici mekanizması. Boşta kalma zaman iletişim çubuğu çağıracak `ON_UPDATE_COMMAND_UI` komut Kimliğini bir Kimliğe sahip tüm düğmelerini işleyiciyle > = 0x8000 (diğer bir deyişle, komut kimlikleri aralığındaki).  
  
 `ON_UPDATE_COMMAND_UI` İşleyici çağırabilirsiniz:  
  
-   Etkinleştirme: için etkinleştirme veya devre dışı bırakma düğmesi.  
  
-   SetText: düğme metni değiştirmek için.  
  
 Özelleştirme standart Pencere Yöneticisi API'leri yapılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

