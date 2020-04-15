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
ms.openlocfilehash: 37c3a15c281018260e65508dee3799ab0011dbfe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370300"
---
# <a name="tn031-control-bars"></a>TN031: Denetim Çubukları

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu not, MFC'deki denetim çubuğu sınıflarını açıklar: genel [CControlBar](#_mfcnotes_ccontrolbar), [CStatusBar](#_mfcnotes_cstatusbar), [CToolBar](#_mfcnotes_ctoolbar), [CDialogBar](#_mfcnotes_cdialogbar), ve `CDockBar`.

## <a name="ccontrolbar"></a><a name="_mfcnotes_ccontrolbar"></a>Ccontrolbar

A, `ControlBar` `CWnd`türetilmiş bir sınıftır:

- Çerçeve penceresinin üst veya alt bölümüne hizalanır.

- HWND `CDialogBar`tabanlı denetimler (örneğin, ) veya temeli`HWND` olmayan öğeler (örneğin, `CToolBar` `CStatusBar`,

Denetim çubukları ek stilleri destekler:

- CBRS_TOP (Varsayılan) denetim çubuğunu en üste sabitler.

- CBRS_BOTTOM Kontrol çubuğunu en alta sabitle.

- CBRS_NOALIGN Üst öğe yeniden boyutlandırıldığında denetim çubuğunu yeniden konumlandırmayın.

Daha ilginç `CControlBar` uygulamalar sağlamak türetilen sınıflar:

- `CStatusBar`Durum çubuğu, öğeler metin içeren durum çubuğu bölmeleridir.

- `CToolBar`Bir araç çubuğu, öğeler bir satır da hizalanmış bitmap düğmeleri vardır.

- `CDialogBar`Standart pencere denetimleri içeren araç çubuğu benzeri bir çerçeve (iletişim şablonu kaynağından oluşturulmuştur).

- `CDockBar`Diğer `CControlBar` türetilmiş nesneler için genelleştirilmiş bir yerleştirme alanı. Bu sınıfta bulunan belirli üye işlevler ve değişkenler, gelecek sürümlerde büyük olasılıkla değişecektir.

Tüm denetim çubuğu nesneleri/pencereleri bazı üst çerçeve penceresinin alt pencereleri olacaktır. Bunlar genellikle çerçevenin istemci alanına kardeş olarak eklenir (örneğin, bir MDI İstemci veya görünüm). Denetim çubuğunun alt pencere kimliği önemlidir. Denetim çubuğunun varsayılan düzeni yalnızca AFX_IDW_CONTROLBAR_LAST AFX_IDW_CONTROLBAR_FIRST aralığında ki iD'leri olan denetim çubukları için çalışır. 256 denetim çubuğu iD'si aralığı olmasına rağmen, bu denetim çubuğu idilerin ilk 32'sinin doğrudan yazdırma önizleme mimarisi tarafından desteklendikleri için özel olduğunu unutmayın.

Sınıf `CControlBar` için standart uygulama verir:

- Denetim çubuğunu çerçevenin üst, alt veya her iki tarafına hizalama.

- Denetim öğesi dizilerini ayırma.

- Türemiş sınıfların uygulanmasını destekleme.

C++ denetim çubuğu nesneleri genellikle türetilmiş `CFrameWnd` bir sınıfın üyesi olarak katıştırılır ve üst `HWND` öğe ve nesne yok edildiğinde temizlenir. Yığına bir denetim çubuğu nesnesi ayırmanız gerekiyorsa, *m_bAutoDestruct* üyesini , denetim çubuğu "**bu**" `HWND` yok edildiğinde yapmak için **TRUE** olarak ayarlayabilirsiniz.

> [!NOTE]
> MFC'nin `CControlBar`türetilmiş sınıflarından birini kullanmak yerine kendi türetilmiş `CStatusBar` `CToolBar`sınıfınızı `CDialogBar`oluşturursanız, m_dwStyle *veri* üyesini ayarlamanız gerekir. Bu geçersiz kılma `Create`yapılabilir:

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

**Denetim Çubuğu Düzen Algoritması**

Denetim çubuğu düzen algoritması çok basittir. Çerçeve penceresi, denetim çubuğu aralığındaki tüm çocuklara WM_SIZEPARENT bir ileti gönderir. Bu iletiyle birlikte, üst öğenin istemci dikdörtgenine bir işaretçi geçirilir. Bu ileti z-sırayla çocuklara gönderilir. Denetim çubuğu alt kendilerini konumlandırmak ve üst istemci alanının boyutunu azaltmak için bu bilgileri kullanın. Normal istemci alanı (daha az denetim çubukları) için bırakılan son dikdörtgen, ana istemci penceresini (genellikle bir MDI istemcisi, görünüm veya ayırıcı pencere) konumlandırmak için kullanılır.

Bakın `CWnd::RepositionBars` `CFrameWnd::RecalcLayout` ve daha fazla bilgi için.

WM_SIZEPARENT dahil olmak üzere MFC özel Windows iletileri [Teknik Not 24'te](../mfc/tn024-mfc-defined-messages-and-resources.md)belgelenmiştir.

## <a name="cstatusbar"></a><a name="_mfcnotes_cstatusbar"></a>Cstatusbar

Durum çubuğu, metin çıktısı bölmeleri satırı olan bir denetim çubuğudur. Metin çıktıbölmelerini kullanmanın iki yaygın yolu vardır:

- İleti satırı olarak

     (örneğin, standart menü yardım ileti satırı). Bunlara genellikle 0 tabanlı dizinlenmiş

- Durum göstergeleri olarak

     (örneğin, CAP, NUM ve SCRL göstergeleri). Bunlara genellikle string/command ID ile erişilir.

Durum çubuğunun yazı tipi 10 noktalı MS Sans Serif'tir (Windows Arabirimi Uygulama Tasarım Kılavuzu veya 10 noktalı İsviçre orantılı yazı tipinin yazı tipi mappers en iyi eşleşmesi tarafından dikte edilir). Japonca sürüm gibi windows'un belirli sürümlerinde seçilen yazı tipleri farklıdır.

Durum çubuğunda kullanılan renkler, Windows Arabirimi Uygulama Tasarım Kılavuzu'nun önerisiyle de uyumlu. Bu renkler sabit kodlanmış değildir ve Denetim Masası'ndaki kullanıcı özelleştirmesine yanıt olarak dinamik olarak değiştirilir.

|Öğe|Windows COLOR değeri|Varsayılan RGB|
|----------|-------------------------|-----------------|
|Durum çubuğu arka planı|COLOR_BTNFACE|RGB(192, 192, 192)|
|Durum çubuğu metni|COLOR_BTNTEXT|RGB(000, 000, 000)|
|Durum çubuğu üst/sol kenarlar|COLOR_BTNHIGHLIGHT|RGB(255, 255, 255)|
|Durum çubuğu botu/sağ kenarları|COLOR_BTNSHADOW|RGB (128, 128, 128)|

**CStatusBar için CCmdUI Desteği**

Göstergelerin genellikle güncellenme şekli ON_UPDATE_COMMAND_UI mekanizmasından geçer. Boşta kalan saatte durum çubuğu, gösterge bölmesinin dize kimliğine sahip ON_UPDATE_COMMAND_UI işleyicisini çağırır.

ON_UPDATE_COMMAND_UI işleyicisi arayabilirsiniz:

- `Enable`: Bölmeyi etkinleştirmek veya devre dışı kılabilir. Devre dışı bırakılmış bölme tam olarak etkin bir bölmeye benzer, ancak metin görünmezdir (diğer bir deyişle, metin göstergesini kapatır).

- `SetText`: Metni değiştirmek için. Bölme otomatik olarak yeniden boyutlandırılmayacak, çünkü bunu kullanırsanız dikkatli olun.

Oluşturma ve özelleştirme API'leri hakkındaki `CStatusBar` ayrıntılar için Sınıf *Kitaplığı Başvurusu'ndaki* [CStatusBar](../mfc/reference/cstatusbar-class.md) sınıfına bakın. Durum çubuğunun çoğu özelleştirme, durum çubuğu ilk olarak görünür hale getirilmeden önce yapılmalıdır.

Durum çubuğu yalnızca bir esnek bölmeyi, genellikle ilk bölmeyi destekler. O bölmenin boyutu gerçekten minimum boyutta. Durum çubuğu tüm bölmelerin minimum boyutundan büyükse, herhangi bir ek genişlik esnek bölmeye verilir. Durum çubuğuna sahip varsayılan uygulama, ilk bölme esnek olduğundan CAP, NUM ve SCRL için doğru hizalanmış göstergelere sahiptir.

## <a name="ctoolbar"></a><a name="_mfcnotes_ctoolbar"></a>Ctoolbar

Araç çubuğu, ayırıcılar içerebilecek biteşmbazı düğmeleri içeren bir denetim çubuğudur. İki düğme stili desteklenir: düğmeler ve onay kutusu düğmeleri. Radyo grubu işlevselliği onay kutusu düğmeleri ve ON_UPDATE_COMMAND_UI ile oluşturulabilir.

Araç çubuğundaki tüm bitmap düğmeleri tek bir bit eşmesinden alınır. Bu bit eşlemi, her düğme için bir görüntü veya glifler içermelidir. Genellikle bit eşlemindeki görüntülerin/gliflerin sırası, ekrana çizilecekleri sırayla aynıdır. (Bu özelleştirme API'leri kullanılarak değiştirilebilir.)

Her düğme aynı boyutta olmalıdır. Varsayılan standart 24x22 pikseldir. Her görüntü/glyph aynı boyutta olmalı ve bit haritasında yan yana olmalıdır. Varsayılan görüntü/glyph boyutu 16x15 pikseldir. Bu nedenle, 10 düğmeli bir araç çubuğu (standart boyutları kullanarak) için 160 piksel genişliğinde ve 15 piksel yüksekliğinde bir bit eşlemi gerekir.

Her düğmenin bir ve tek bir görüntüsü/glyph'i vardır. Farklı düğme durumları ve stilleri (örneğin, basılı, yukarı, aşağı, devre dışı bırakılmış, devre dışı bırakılmış, belirsiz) bu görüntü/glyph'den algoritmik olarak oluşturulur. Herhangi bir renk bitmap veya DIB teoride kullanılabilir. Özgün görüntü grinin tonları ise, farklı düğme durumlarını oluşturma algoritması en iyi şekilde çalışır. Örnekler için MFC Genel örnek [CLIPART'ta](../overview/visual-cpp-samples.md) sağlanan standart araç çubuğu düğmelerine ve araç çubuğu düğmesi klibine bakın.

Araç çubuğunda kullanılan renkler, Windows Arabirimi Uygulama Tasarım Kılavuzu'nun önerisiyle de uyumlu. Bu renkler sabit kodlanmış değildir ve Denetim Masası'ndaki kullanıcı özelleştirmesine yanıt olarak dinamik olarak değiştirilir.

|Öğe|Windows COLOR değeri|Varsayılan RGB|
|----------|-------------------------|-----------------|
|Araç Çubuğu arka planı|COLOR_BTNFACE|RGB (192.192.192)|
|Araç Çubuğu düğmeleri üst/sol kenarlar|COLOR_BTNHIGHLIGHT|RGB(255.255.255)|
|ToolBar düğmeleri bot/sağ kenarlar|COLOR_BTNSHADOW|RGB (128.128.128)|

Buna ek olarak, araç çubuğu bitmap düğmeleri standart Windows düğmesi denetimleri gibi yeniden renklenir. Bu yeniden renklendirme, bit eşlemi kaynaktan yüklendiğinde ve Denetim Masası'ndaki kullanıcı özelleştirmesine yanıt olarak sistem renklerinde yapılan bir değişikliğe yanıt olarak oluşur. Araç çubuğu bit eşlemindeki aşağıdaki renkler otomatik olarak yeniden renklendirilecek, bu nedenle dikkatli kullanılmalıdır. Bit haritanızın bir bölümünün yeniden renklendirmesini istemiyorsanız, eşlenen RGB değerlerinden birine yakından benzeyen bir renk kullanın. Eşleme tam RGB değerlerine göre yapılır.

|RGB değeri|Dinamik eşlenen COLOR değeri|
|---------------|------------------------------------|
|RGB(000, 000, 000)|COLOR_BTNTEXT|
|RGB (128, 128, 128)|COLOR_BTNSHADOW|
|RGB(192, 192, 192)|COLOR_BTNFACE|
|RGB(255, 255, 255)|COLOR_BTNHIGHLIGHT|

Oluşturma ve özelleştirme API'leri hakkında ayrıntılar `CToolBar` için [CToolBar](../mfc/reference/ctoolbar-class.md) *sınıfısınıf kitaplığı başvurusuna* bakın. Araç çubuğu ilk olarak görünür hale getirilmeden önce araç çubuklarının çoğu özelleştirme yapılmalıdır.

Özelleştirme API'leri düğme kimliklerini, stillerini, spacer genişliğini ve hangi düğme için hangi görüntü/gph'nin kullanıldığını ayarlamak için kullanılabilir. Varsayılan olarak bu API'leri kullanmanız gerekmez.

## <a name="ccmdui-support-for-ctoolbar"></a>CToolBar için CCmdUI Desteği

Araç çubuğu düğmelerinin her zaman güncellenme şekli ON_UPDATE_COMMAND_UI mekanizmasından geçer. Boşta kalan saatte araç çubuğu, bu düğmenin komut kimliğiyle ON_UPDATE_COMMAND_UI işleyicisini arar. ON_UPDATE_COMMAND_UI ayırıcılar için çağrılmaz, ancak düğmeler ve onay kutusu düğmeleri için çağrılır.

ON_UPDATE_COMMAND_UI işleyicisi arayabilirsiniz:

- `Enable`: Düğmeyi etkinleştirmek veya devre dışı etmek için. Bu, düğmeler ve onay kutusu düğmeleri için eşit şekilde çalışır.

- `SetCheck`: Bir düğmenin denetim durumunu ayarlamak için. Bunu araç çubuğu düğmesi için çağırmak, düğmeyi onay kutusu düğmesine dönüştürür. `SetCheck`0 (işaretlenmemiş), 1 (kontrol edilmiş) veya 2 (belirsiz) olabilecek bir parametre alır

- `SetRadio`: Stenoiçin `SetCheck`.

Onay kutusu düğmeleri "AUTO" onay kutusu düğmeleridir; diğer bir de, kullanıcı bunları bastığında durum hemen değişecektir. Kontrol aşağı veya depresif durumdur. Bir düğmeyi "belirsiz" duruma dönüştürmek için yerleşik kullanıcı arabirimi yolu yoktur; kod yoluyla yapılmalıdır.

Özelleştirme API'leri belirli bir araç çubuğu düğmesinin durumunu değiştirmenize izin verir, tercihen araç çubuğu düğmesinin temsil edeceği komut için ON_UPDATE_COMMAND_UI işleyicisinde bu durumları değiştirmeniz gerekir. Boşta işleme ON_UPDATE_COMMAND_UI işleyicisi ile araç çubuğu düğmelerinin durumunu değiştireceğini unutmayın, böylece SetButtonStyle üzerinden yapılan bu eyaletlerde yapılan değişiklikler bir sonraki boşta sonra kaybolabilir.

Araç çubuğu düğmeleri normal düğmeler veya menü öğeleri gibi WM_COMMAND iletileri gönderir ve normalde ON_UPDATE_COMMAND_UI işleyicisini sağlayan aynı sınıftaki ON_COMMAND işleyicisi tarafından işlenir.

Görüntü durumları için kullanılan dört Araç Çubuğu düğmesi stili (TBBS_ değerleri) vardır:

- TBBS_CHECKED: Onay kutusu şu anda işaretli (aşağı).

- TBBS_INDETERMINATE: Onay kutusu şu anda belirsizdir.

- TBBS_DISABLED: Düğme şu anda devre dışı.

- TBBS_PRESSED: Şu anda düğmeye basıldı.

Altı resmi Windows Arabirimi Uygulama Tasarım Kılavuzu düğmesi stilleri aşağıdaki TBBS değerleri ile temsil edilir:

- Yukarı = 0

- Fare Aşağı = TBBS_PRESSED (&#124; başka bir stil)

- Devre Dışı / TBBS_DISABLED

- Aşağı = TBBS_CHECKED

- Aşağı Devre Dışı = TBBS_CHECKED &#124; TBBS_DISABLED

- Belirsiz = TBBS_INDETERMINATE

## <a name="cdialogbar"></a><a name="_mfcnotes_cdialogbar"></a>Cdialogbar

İletişim çubuğu, standart Windows denetimleri içeren bir denetim çubuğudur. Denetimleri içerdiği ve aralarındasekleme yi destekleyen bir iletişim kutusu gibi davranır. Ayrıca, çubuğu temsil etmek için bir iletişim şablonu kullandığı bir iletişim kutusu gibi davranır.

A, `CDialogBar` standart basma düğmesi denetimleri içeren yazdırma önizleme araç çubuğu için kullanılır.

A `CDialogBar` kullanmak, bir `CFormView`. İletişim çubuğu için bir iletişim şablonu tanımlamanız ve WS_CHILD hariç tüm stilleri kaldırmanız gerekir. İletişim kutusunun görünür olmaması gerektiğini unutmayın.

A `CDialogBar` için denetim bildirimleri denetim çubuğunun üst bölümüne gönderilir (araç çubuğu düğmeleri gibi).

## <a name="ccmdui-support-for-cdialogbar"></a>CDialogBar için CCmdUI Desteği

İletişim çubuğu düğmeleri ON_UPDATE_COMMAND_UI işleyici mekanizması aracılığıyla güncelleştirilmelidir. Boşta olduğu anda iletişim çubuğu, >= 0x8000 (komut kimlikleri aralığında) kimlik >olan tüm düğmelerin komut kimliğine sahip ON_UPDATE_COMMAND_UI işleyicisini çağırır.

ON_UPDATE_COMMAND_UI işleyicisi arayabilirsiniz:

- Enable: düğmeyi etkinleştirmek veya devre dışı kılabilir.

- SetText: düğmenin metnini değiştirmek için.

Özelleştirme standart pencere yöneticisi API'leri üzerinden yapılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
