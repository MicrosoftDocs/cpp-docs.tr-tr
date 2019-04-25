---
title: 'TN031: Denetim Çubukları'
ms.date: 11/04/2016
f1_keywords:
- vc.controls.bars
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
ms.openlocfilehash: 39309408c6d1fc6cbb4223eda22c511865f14498
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305639"
---
# <a name="tn031-control-bars"></a>TN031: Denetim Çubukları

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, MFC denetim çubuğu sınıfları açıklar: Genel [CControlBar](#_mfcnotes_ccontrolbar), [CStatusBar](#_mfcnotes_cstatusbar), [CToolBar](#_mfcnotes_ctoolbar), [CDialogBar](#_mfcnotes_cdialogbar)ve `CDockBar`.

## <a name="_mfcnotes_ccontrolbar"></a> CControlBar

A `ControlBar` olduğu bir `CWnd`-türetilmiş sınıflar:

- Üst veya alt çerçeve penceresinin hizalanır.

- Her iki HWND tabanlı denetimler alt öğeleri içerebilir (örneğin, `CDialogBar`) olmayan veya -`HWND` bağlı öğeler (örneğin, `CToolBar`, `CStatusBar`).

Denetim çubukları ek stil desteği:

- (Varsayılan) CBRS_TOP PIN üst denetim çubuğu.

- CBRS_BOTTOM PIN altına denetim çubuğu.

- CBRS_NOALIGN yapmak değil konumunu denetim çubuğunun üst boyutlandırdığında.

Türetilen sınıflar `CControlBar` daha ilgi çekici uygulamaları belirtin:

- `CStatusBar` Bir durum çubuğu metni içeren bir durum çubuğu bölmeleri öğelerdir.

- `CToolBar` Bir araç çubuğu bit eşlem düğmeler bir satır hizalı öğelerdir.

- `CDialogBar` Standart windows içeren bir araç çubuğu benzeri çerçevesi (bir iletişim şablonunu kaynaktan oluşturulan) denetimleri.

- `CDockBar` Genelleştirilmiş bir yerleştirme alanında diğer `CControlBar` türetilmiş nesneler. Özel üye işlevleri ve değişkenler bu sınıfta kullanılabilir yayınlar gelecekte değiştirme olasılığı düşüktür.

Tüm denetim çubuğu nesneleri/windows alt pencereleri bazı ana çerçeve penceresinin olacaktır. Bunlar genellikle bir eşdüzeyi (örneğin, bir MDI istemci veya Görünüm) çerçevenin istemci alanının eklenir. Denetim çubuğu alt penceresi kimliği büyük/küçük harf önemlidir. Denetim çubuğu varsayılan düzenini yalnızca denetim çubukları aralığı AFX_IDW_CONTROLBAR_FIRST AFX_IDW_CONTROLBAR_LAST için kimlikleri ile çalışır. Bir dizi 256 denetim olsa bile unutmayın doğrudan bir baskı önizleme mimarisi tarafından desteklenen kimlikleri, bu denetim çubuğu ilk 32 kimlikleri özel olduğundan.

`CControlBar` Sınıfı için standart uygulaması sağlar:

- Üst, alt veya çerçevenin tarafındaki denetim çubuğuna hizalama.

- Denetim öğesi diziler ayrılıyor.

- Uygulaması türetilen sınıfların destekleme.

C++ denetim çubuğu genellikle katıştırılmış nesneleri üyesi olarak bir `CFrameWnd` türetilmiş bir sınıf ve ne zaman temizlenecek üst `HWND` ve nesne yok edilir. Bir denetim çubuğu nesne yığını üzerindeki ayrılacak gerekiyorsa ayarlayabilirsiniz *m_bAutoDestruct* üyesine **TRUE** denetim çubuğu yapmak için "**bu silme**" olduğunda `HWND` yok.

> [!NOTE]
>  Kendi oluşturursanız `CControlBar`-yerine sınıfları MFC'nin birini kullanarak gibi türetilmiş sınıfın, türetilmiş `CStatusBar`, `CToolBar`, veya `CDialogBar`, ayarlanacak ihtiyacınız olacak *m_dwStyle* veri üyesi. Bu geçersiz kılmasında yapılabilir `Create`:

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

**Denetim çubuğu yerleşimi algoritmasını**

Denetim çubuğu yerleşimi algoritmasını çok kolaydır. Çerçeve penceresi tüm alt denetim çubuğu aralıktaki WM_SIZEPARENT bir ileti gönderir. Bu ileti yanı sıra, üst öğenin istemci dikdörtgeni işaretçisi geçirilir. Bu ileti, öğenin alt öğelerine Z düzeninde gönderilir. Denetim çubuğu alt kendilerini getirin ve üst öğenin istemci alanının boyutunu azaltmak için bu bilgileri kullanın. Normal istemci alanını (daha az denetim çubukları) için sol nihai dikdörtgenin ana istemci penceresi (genellikle MDI istemci, görüntüleme ya da ayırıcı penceresine) yerleştirmek için kullanılır.

Bkz: `CWnd::RepositionBars` ve `CFrameWnd::RecalcLayout` daha fazla ayrıntı için.

WM_SIZEPARENT, dahil olmak üzere MFC özel Windows iletileri belgelenir [Teknik Not 24](../mfc/tn024-mfc-defined-messages-and-resources.md).

## <a name="_mfcnotes_cstatusbar"></a>  CStatusBar

Durum çubuğunda metin çıkış bölmeleri boyutunda bir satır içeren bir denetim çubuğu ' dir. Metin çıkış bölmeleri kullanmak için iki genel yolu vardır:

- Bir ileti satırı

     (örneğin, standart menü Yardım iletisi satır). Bunlar genellikle bir 0 tabanlı tarafından dizine erişilen

- Durum göstergesi olarak

     (örneğin, büyük harf, sayı ve SCRL göstergeleri). Bunlar, genellikle dize/komut kimliği ile erişilen

Durum çubuğu yazı tipini noktası 10 MS (Windows arabirimi uygulaması tasarım kılavuzu veya yazı tipi azaltıcının en iyi eşleşen 10 noktalı İsviçre orantılı yazı tipinin tarafından belirlenir) tırnaksız ' dir. Windows, belirli sürümlerinde Japonca sürümü gibi seçili yazı tipleri farklıdır.

Durum çubuğunda kullanılan renkleri de Windows arabirimi uygulaması Tasarım Kılavuzu önerisi ile tutarlı değil. Bu renklerin değil sabit kodlanmış ve yanıt olarak Denetim Masası'ndaki kullanıcı özelleştirme dinamik olarak değiştirilir.

|Öğe|Windows renk değeri|Varsayılan RGB|
|----------|-------------------------|-----------------|
|Durum çubuğu arka plan|COLOR_BTNFACE|RGB(192, 192, 192)|
|Durum çubuğu metni|COLOR_BTNTEXT|RGB (000 000, 000)|
|Durum çubuğu üst/sol kenarlar|COLOR_BTNHIGHLIGHT|RGB(255, 255, 255)|
|Durum çubuğu bot/sağ kenarlar|COLOR_BTNSHADOW|RGB(128, 128, 128)|

**CStatusBar Ccmduı desteği**

Göstergeleri genellikle güncelleştirilir on_update_command_uı mekanizma aracılığıyla yoludur. Boşta zamanında durum çubuğu gösterge bölmesini dize kimliği on_update_command_uı işleyici çağırır.

On_update_command_uı işleyici çağırabilirsiniz:

- `Enable`: Etkinleştirmek veya bölmesinde devre dışı bırakmak için. Devre dışı bırakılmış bir bölme tam olarak bir etkin bölmesi gibi görünüyor, ancak metni görünmezdir (diğer bir deyişle, metin göstergesi devre dışı bırakır).

- `SetText`: Metni değiştirmek için. Bölmesinde değil otomatik olarak yeniden boyutlandırılır çünkü bu kullanırsanız, dikkatli olun.

Sınıfa başvurmak [CStatusBar](../mfc/reference/cstatusbar-class.md) içinde *sınıf kitaplığı başvurusu* hakkındaki ayrıntılar için `CStatusBar` oluşturma ve özelleştirme API'leri. Durum çubukları çoğu özelleştirme, durum çubuğu başlangıçta görünür hale gelir önce yapılmalıdır.

Durum çubuğu, yalnızca bir stretchy bölmesi, genellikle ilk bölmesi destekler. Bu bölme boyutunu gerçekten en az bir boyutudur. Durum çubuğu tüm bölmeleri en düşük boyuttan daha büyük ise, herhangi bir fazladan genişliği stretchy bölmesine verilir. İlk bölmesinde stretchy olduğundan varsayılan uygulama durum çubuğu ile sağa hizalı göstergeleri için büyük harf, sayı ve SCRL sahiptir.

## <a name="_mfcnotes_ctoolbar"></a>  CToolBar

Denetim çubuğu ayırıcılar içerebilecek bir bit eşlem düğme ile bir araç çubuğudur. Düğmenin iki stilleri desteklenir: pushbuttons ve onay kutusu düğmeleri. Grup işlevleri radyo onay kutusu düğmeleri ve on_update_command_uı ile oluşturulabilir.

Bit eşlem düğmeleri araç çubuğunda bir bit eşlem alınır. Bu bit eşlemi, bir resim veya her düğme için karakter içermelidir. Genellikle görüntüleri/karakterlerin bit eşlem ekranda çizileceğini aynı sırada sırasıdır. (Bu API'leri özelleştirmesi kullanılarak değiştirilebilir.)

Her düğme aynı boyutta olması gerekir. Standart 24 x 22 piksel varsayılandır. Her görüntü/glif aynı boyutta olması gerekir ve yan yana olmalı, bit eşlem. Varsayılan görüntü/simge boyutu 16 x 15 pikseldir. Bu nedenle, 10 düğmeler (standart boyutlarını kullanarak) ile bir araç için 160 piksel genişliğinde ve 15 piksel yüksekliğinde bir bit eşlem gerekir.

Her bir düğme bir ve yalnızca bir görüntü/glif vardır. Farklı bir düğmeyi belirtir ve stilleri (basılı, örneğin, aşağı, devre dışı, aşağı, belirsiz devre dışı) bir o yansıma/glif algorithmically oluşturulur. Herhangi bir renk bit eşlem veya DIB teorik olarak kullanılabilir. Özgün Görüntü gri ise farklı bir düğmeyi oluşturmak için algoritma en iyi şekilde çalışır belirtir. Standart araç çubuğu düğmeleri ve MFC genel örnek sağlanan araç çubuğu düğmesi küçük bakın [küçük](../overview/visual-cpp-samples.md) örnekler.

Araç çubuğunda kullanılan renkleri de Windows arabirimi uygulaması Tasarım Kılavuzu önerisi ile tutarlı değil. Bu renklerin değil sabit kodlanmış ve yanıt olarak Denetim Masası'ndaki kullanıcı özelleştirme dinamik olarak değiştirilir.

|Öğe|Windows renk değeri|Varsayılan RGB|
|----------|-------------------------|-----------------|
|Araç çubuğu arka plan|COLOR_BTNFACE|RGB(192,192,192)|
|Üst/sol kenarlar araç çubuğu düğmeleri|COLOR_BTNHIGHLIGHT|RGB(255,255,255)|
|Bot/sağ kenarları araç çubuğu düğmeleri|COLOR_BTNSHADOW|RGB(128,128,128)|

Ayrıca, standart Windows düğme denetimleri gibi davranarak düğmeler bit eşlem renklendirilmiştir. Bit eşlem kaynaktan ve yanıt sistem renkleri yanıt olarak kullanıcı özelleştirme Denetim Masası'nda bir değişiklik olarak yüklendiğinde bu yeniden renklendirme gerçekleşir. Dikkatli kullanılmalıdır, böylece bir araç çubuğu bit eşlem aşağıdaki renkleri otomatik olarak renklendirilmiş. Ardından, bit eşlem renklendirilmiş bir kısmını olmasını istemiyorsanız, eşlenen RGB değerleri birini yakından benzeyen bir renk kullanın. Eşleme tam RGB değerleri göre yapılır.

|RGB değeri|Dinamik olarak eşlenen renk değeri|
|---------------|------------------------------------|
|RGB (000 000, 000)|COLOR_BTNTEXT|
|RGB(128, 128, 128)|COLOR_BTNSHADOW|
|RGB(192, 192, 192)|COLOR_BTNFACE|
|RGB(255, 255, 255)|COLOR_BTNHIGHLIGHT|

Sınıfa başvurmak [CToolBar](../mfc/reference/ctoolbar-class.md) *sınıf kitaplığı başvurusu* hakkındaki ayrıntılar için `CToolBar` oluşturma ve özelleştirme API'leri. Çoğu araç çubuklarını özelleştirme araç çubuğu başlangıçta görünür hale gelir önce yapılmalıdır.

API'leri, kimlikleri, stiller, düğmeyi ayarlamak için kullanılabilir özelleştirme ayırıcısının genişlik ve hangi görüntü/glif hangi düğme için kullanılır. Varsayılan olarak bu API'leri kullanın gerekmez.

## <a name="ccmdui-support-for-ctoolbar"></a>CToolBar Ccmduı desteği

Araç çubuğu düğmeleri her zaman güncelleştirilir on_update_command_uı mekanizma aracılığıyla yoludur. Boşta kalma süresi üzerinde araç komut kimliği söz konusu düğmenin on_update_command_uı işleyici çağırır. On_update_command_uı ayırıcılar için çağrılmaz ancak pushbuttons ve onay kutusu düğmeleri için çağrılır.

On_update_command_uı işleyici çağırabilirsiniz:

- `Enable`: Etkinleştirme veya düğmeyi devre dışı bırakma. Bu, eşit olarak pushbuttons ve onay kutusu düğmeleri için çalışır.

- `SetCheck`: Bir düğme denetimi durumunu ayarlamak için. Toolbar düğmesi için bunu çağıran bir onay kutusu düğmesi açar. `SetCheck` (işaretli) 0, 1 (işaretli) veya 2 (belirsiz) olabilecek bir parametre alır

- `SetRadio`: İçin Toplu özellik `SetCheck`.

Onay kutusu düğmeleri, "AUTO" onay kutusu düğmeleri değildir; kullanıcı bunları bastığında diğer bir deyişle, bunlar hemen durumu değişir. Aşağı ya da basılı durumu denetlenir. Bir düğmeyi "belirsiz" durumuna değiştirmek için yerleşik kullanıcı arabirimi bir yolu yoktur; Bu kod yapılmalıdır.

Özelleştirme API'leri, belirli bir araç çubuğu düğmesi durumunu değiştirmek için izin verir, tercihen on_update_command_uı işleyici araç çubuğu düğmesi nesnesini temsil eden komutu için şu durumlarda değiştirmeniz gerekir. Unutmayın, boşta işleme, araç on_update_command_uı işleyicisi düğmeleriyle durumunu değiştirecek, sonraki sonra bu durumları SetButtonStyle yapılan değişiklikleri kayıp alabilirsiniz için boş.

Araç çubuğu düğmeleri, normalde on_update_command_uı işleyici sağlayan aynı sınıftaki bir ON_COMMAND işleyici tarafından işlenir ve normal bir düğme veya menü öğeleri gibi WM_COMMAND iletileri gönderir.

Görüntü durumları için kullanılan dört araç çubuğu düğmesi stilleri (TBBS_ değerler) vardır:

- TBBS_CHECKED:   Onay kutusu, şu anda (basılı) denetlenir.

- TBBS_INDETERMINATE:   Onay kutusu, şu anda belirsiz.

- TBBS_DISABLED:   Düğmesi devre dışıdır.

- TBBS_PRESSED:   Şu anda, düğmeye basıldığında.

Altı resmi Windows arabirimi uygulaması Tasarım Kılavuzu düğme stilleri aşağıdaki TBBS değerlerle temsil edilir:

- Up = 0

- Fare aşağı TBBS_PRESSED = (&#124; başka bir stil)

- Devre dışı bırakılmış TBBS_DISABLED =

- Aşağı TBBS_CHECKED =

- = Devre dışı TBBS_CHECKED &#124; TBBS_DISABLED

- Belirsiz TBBS_INDETERMINATE =

##  <a name="_mfcnotes_cdialogbar"></a> CDialogBar

Bir iletişim çubuğu standart Windows denetimlerini içeren bir denetim çubuğudur. Denetimler içerir ve bunlar arasında sekmeyle gitmeyi destekler bir iletişim kutusu gibi davranır. Çubuğunu temsil etmek için bir iletişim şablonunu kullanır, ayrıca bir iletişim kutusu gibi davranır.

A `CDialogBar` standart pushbutton denetimleri içeren Baskı Önizleme araç için kullanılır.

Kullanarak bir `CDialogBar` kullanmak gibi bir `CFormView`. Bir iletişim şablonunu iletişim çubuğu tanımlayın ve WS_CHILD dışındaki tüm stiller kaldırmanız gerekir. İletişim kutusu görünür olmaması gerektiğini unutmayın.

Denetim bildirimleri için bir `CDialogBar` (olduğu gibi araç çubuğu düğmeleri) denetim çubuğunun üst gönderilir.

## <a name="ccmdui-support-for-cdialogbar"></a>CDialogBar Ccmduı desteği

On_update_command_uı işleyici mekanizma aracılığıyla iletişim çubuğu düğmelerinin güncelleştirilmelidir. Boşta kalma zaman iletişim çubuğu komut kimliği bir Kimliğe sahip tüm düğmeler on_update_command_uı işleyici çağırır > 0x8000 = (diğer bir deyişle, komut kimlikleri aralığında).

On_update_command_uı işleyici çağırabilirsiniz:

- Etkinleştir: için etkinleştirme veya devre dışı bırak düğmesi.

- SetText: düğmenin metni değiştirmek için.

Özelleştirme standart penceresi manager API'leri yapılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
