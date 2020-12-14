---
description: 'Hakkında daha fazla bilgi edinin: TN031: denetim çubukları'
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
ms.openlocfilehash: 42dddf1afabdf2ab04ba8441208e7109eeacbd65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215553"
---
# <a name="tn031-control-bars"></a>TN031: Denetim Çubukları

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, MFC 'deki denetim çubuğu sınıfları açıklanmaktadır: genel [CControlBar](#_mfcnotes_ccontrolbar), [CStatusBar](#_mfcnotes_cstatusbar), [CToolBar](#_mfcnotes_ctoolbar), [CDialogBar](#_mfcnotes_cdialogbar)ve `CDockBar` .

## <a name="ccontrolbar"></a><a name="_mfcnotes_ccontrolbar"></a> CControlBar

`ControlBar`, Tarafından `CWnd` türetilmiş bir sınıftır:

- , Bir çerçeve penceresinin üst veya alt kısmına hizalanır.

- HWND tabanlı denetimler (örneğin, `CDialogBar` ) ya da `HWND` tabanlı olmayan öğeler (örneğin,,) olan alt öğeler içerebilir `CToolBar` `CStatusBar` .

Denetim çubukları ek stilleri destekler:

- CBRS_TOP (varsayılan) denetim çubuğunu en üste sabitleyin.

- Denetim çubuğunu en alta sabitle CBRS_BOTTOM.

- Üst üste boyutlandırdığında denetim çubuğunu yeniden konumlandırmayın CBRS_NOALIGN.

Öğesinden türetilen sınıflar `CControlBar` daha ilginç uygulamalar sağlar:

- `CStatusBar` Bir durum çubuğu, öğeler metin içeren durum çubuğu bölmelerdir.

- `CToolBar` Bir araç çubuğu, öğeler bir satırda hizalanmış bit eşlem düğmelerdir.

- `CDialogBar` Standart Windows denetimlerini içeren bir araç çubuğu benzeri çerçeve (bir iletişim kutusu şablon kaynağından oluşturulur).

- `CDockBar` Diğer türetilmiş nesneler için genelleştirilmiş bir yerleştirme alanı `CControlBar` . Bu sınıfta bulunan belirli üye işlevleri ve değişkenler gelecekteki sürümlerde değişebilir.

Tüm denetim çubuğu nesneleri/pencereleri, bazı üst çerçeve penceresinin alt pencereleri olacaktır. Genellikle çerçevenin istemci alanına eşdüzey olarak eklenir (örneğin, bir MDI Istemcisi veya görünümü). Bir denetim çubuğunun alt pencere KIMLIĞI önemlidir. Denetim çubuğunun varsayılan düzeni yalnızca AFX_IDW_CONTROLBAR_LAST AFX_IDW_CONTROLBAR_FIRST aralığındaki kimlik olan denetim çubukları için geçerlidir. 256 denetim çubuğu kimliği aralığı olsa da, bu denetim çubuğu kimliklerinin ilk 32 ' nin, baskı önizleme mimarisi tarafından doğrudan desteklendiğinden emin olduğunu unutmayın.

`CControlBar`Sınıfı için standart uygulama sağlar:

- Denetim çubuğunu çerçevenin en üst, alt veya iki tarafına hizalama.

- Denetim öğesi dizileri ayrılıyor.

- Türetilmiş sınıfların uygulanmasını destekleme.

C++ denetim çubuğu nesneleri genellikle türetilmiş bir sınıfın üyeleri olarak gömülecektir `CFrameWnd` ve üst `HWND` ve nesne yok edildiğinde temizlenir. Yığında bir denetim çubuğu nesnesi ayırmanız gerekiyorsa, yok edildiğinde "**bunu Sil**" Denetim çubuğunu yapmak için *m_bAutoDestruct* üyesini **true** olarak ayarlamanız yeterlidir `HWND` .

> [!NOTE]
> ,, Veya gibi, `CControlBar` MFC 'nin türetilmiş sınıflarından birini kullanmak yerine kendi türetilmiş sınıfınızı oluşturursanız, `CStatusBar` `CToolBar` `CDialogBar` *m_dwStyle* veri üyesini ayarlamanız gerekecektir. Bu, geçersiz kılmada yapılabilir `Create` :

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

**Denetim çubuğu düzen algoritması**

Denetim çubuğu düzen algoritması çok basittir. Çerçeve penceresi, denetim çubuğu aralığındaki tüm alt öğelere WM_SIZEPARENT bir ileti gönderir. Bu iletiyle birlikte, üst öğenin istemci dikdörtgeninin bir işaretçisi geçirilir. Bu ileti, alt öğelerine Z düzeninde gönderilir. Denetim çubuğu alt öğeleri, bu bilgileri kendilerini konumlandırmak ve üst öğenin istemci alanının boyutunu azaltmak için kullanır. Ana istemci penceresini (genellikle bir MDI istemcisi, görünüm veya ayırıcı pencere) konumlandırmak için, normal istemci alanı (daha az denetim çubukları) için bırakılan son dikdörtgen kullanılır.

`CWnd::RepositionBars` `CFrameWnd::RecalcLayout` Daha fazla ayrıntı için bkz. ve.

WM_SIZEPARENT dahil olmak üzere MFC özel Windows iletileri, [teknik notta 24](../mfc/tn024-mfc-defined-messages-and-resources.md)' te belgelenmiştir.

## <a name="cstatusbar"></a><a name="_mfcnotes_cstatusbar"></a> CStatusBar

Durum çubuğu, bir metin çıkış bölmesi satırı olan bir denetim çubuğudur. Metin çıkış bölmelerini kullanmanın iki yaygın yolu vardır:

- İleti satırı olarak

     (örneğin, standart menü yardım iletisi satırı). Bunlara genellikle 0 tabanlı bir dizinli dizine erişilir

- Durum göstergeleri olarak

     (örneğin, CAP, NUM ve SCRL göstergeleri). Bunlara genellikle dize/komut KIMLIĞI tarafından erişilir.

Durum çubuğunun yazı tipi 10 noktalı MS Sans Serif (Windows arabirimi uygulaması tasarım kılavuzu tarafından dikte edilen veya 10 puntoluk Isviçre orantılı yazı tipi maptems en iyi eşleşmesi tarafından dikte edilir). Windows 'un Japonca sürümü gibi bazı sürümlerinde, seçilen yazı tipleri farklıdır.

Durum çubuğunda kullanılan renkler, Windows arabirimi uygulaması tasarım kılavuzunun önerisi ile de tutarlıdır. Bu renkler sabit olarak kodlanmaz ve Denetim Masası 'ndaki Kullanıcı özelleştirmesine yanıt olarak dinamik olarak değiştirilir.

|Öğe|Windows renk değeri|Varsayılan RGB|
|----------|-------------------------|-----------------|
|Durum çubuğu arka planı|COLOR_BTNFACE|RGB (192, 192, 192)|
|Durum çubuğu metni|COLOR_BTNTEXT|RGB (000, 000, 000)|
|Durum çubuğu üst/sol kenarlar|COLOR_BTNHIGHLIGHT|RGB (255, 255, 255)|
|Durum çubuğu bot/sağ kenarlar|COLOR_BTNSHADOW|RGB (128, 128, 128)|

**CStatusBar için CCmdUI desteği**

Göstergeler genellikle ON_UPDATE_COMMAND_UI mekanizması aracılığıyla güncelleştirilir. Boşta kalma süresi boyunca, durum çubuğu ON_UPDATE_COMMAND_UI işleyicisini gösterge bölmesinin dize KIMLIĞIYLE çağırır.

ON_UPDATE_COMMAND_UI işleyicisi şu şekilde çağırabilir:

- `Enable`: Bölmesi etkinleştirmek veya devre dışı bırakmak için. Devre dışı bırakılmış bir bölme tamamen etkin bir bölme gibi görünür, ancak metin görünmez (yani, metin göstergesini kapatır).

- `SetText`: Metni değiştirmek için. Bölmesi otomatik olarak yeniden boyutlandırmayacak olduğundan bunu kullanırsanız dikkatli olun.

Oluşturma ve özelleştirme API 'Leri hakkındaki ayrıntılar için *sınıf kitaplığı başvurusunda* [CStatusBar](../mfc/reference/cstatusbar-class.md) sınıfına bakın `CStatusBar` . Durum çubuğu, ilk başta görünür hale gelmeden önce, durum çubuklarının çoğu özelleştirmesi yapılmalıdır.

Durum çubuğu, genellikle ilk bölme olan yalnızca bir ayarlayıcı bölmesini destekler. Bu bölmenin boyutu gerçekten en küçük boyutdir. Durum çubuğu tüm bölmelerin en düşük boyutundan daha büyükse, en fazla bir genişlik bölmesi, tüm ek genişlikler bölmesine verilir. Durum çubuğu olan varsayılan uygulama, ilk bölme uygun olduğundan, uç, NUM ve SCRL için sağa hizalanmış göstergeler içerir.

## <a name="ctoolbar"></a><a name="_mfcnotes_ctoolbar"></a> CToolBar

Bir araç çubuğu, ayırıcı içerebilen bir bit eşlem düğmesi satırı içeren bir denetim çubuğudur. İki düğme stili desteklenir: pushbuttons ve onay kutusu düğmeleri. Radyo Grubu işlevselliği, onay kutusu düğmeleri ve ON_UPDATE_COMMAND_UI oluşturulabilir.

Araç çubuğundaki tüm bit eşlem düğmeleri bir bit eşlemden alınır. Bu bit eşlem, her düğme için bir resim veya karakter içermelidir. Genellikle bit eşlemdeki görüntülerin/karakterlerin sırası, ekranda çizileceği sıralardır. (Bu, özelleştirme API 'Leri kullanılarak değiştirilebilir.)

Her düğme aynı boyutta olmalıdır. Varsayılan değer standart 24x22 pikseldir. Her görüntü/glif aynı boyutta olmalıdır ve bit eşlemde yan yana olmalıdır. Varsayılan görüntü/karakter boyutu 16x15 pikseldir. Bu nedenle, 10 tuşlu (Standart boyutları kullanarak) bir araç çubuğunda, 160 piksel genişliğinde ve 15 piksel yüksekliğinde bir bit eşleminiz olması gerekir.

Her düğmenin bir ve yalnızca bir resim/karakter vardır. Farklı düğme durumları ve stilleri (örneğin, basılmış, yukarı, aşağı, devre dışı, devre dışı), bu görüntüden/glifden algorithmically oluşturulur. Herhangi bir renk bit eşlem veya DIB, teorik olarak kullanılabilir. Farklı düğme durumlarını oluşturma algoritması, orijinal görüntünün gri tonu olması durumunda en iyi şekilde geçerlidir. Örnek olarak MFC genel örnek [küçük resim](../overview/visual-cpp-samples.md) bölümünde sunulan standart araç çubuğu düğmelerine ve araç çubuğu düğmesi clipart bölümüne bakın.

Araç çubuğunda kullanılan renkler, Windows arabirimi uygulaması tasarım kılavuzunun önerisi ile de tutarlıdır. Bu renkler sabit olarak kodlanmaz ve Denetim Masası 'ndaki Kullanıcı özelleştirmesine yanıt olarak dinamik olarak değiştirilir.

|Öğe|Windows renk değeri|Varsayılan RGB|
|----------|-------------------------|-----------------|
|Araç çubuğu arka planı|COLOR_BTNFACE|RGB (192192192)|
|Araç çubuğu düğmeleri üst/sol kenarlar|COLOR_BTNHIGHLIGHT|RGB (255255255)|
|Araç çubuğu düğmeleri bot/sağ kenarlar|COLOR_BTNSHADOW|RGB (128128128)|

Ayrıca, araç çubuğu bit eşlem düğmeleri standart Windows düğme denetimlermiş gibi yeniden renklendirilirler. Bu yeniden, bit eşlem kaynaktan yüklendiğinde ve Denetim Masası 'ndaki Kullanıcı özelleştirmesine yanıt olarak sistem renkleriyle bir değişikliğe yanıt olarak ortaya çıkar. Bir araç çubuğu bit eşlemdeki aşağıdaki renkler, dikkatli bir şekilde kullanılması için otomatik olarak yeniden renklendirilir. Bit eşlemizin yeniden renklendirmesi yapmak istemiyorsanız, eşlenmiş RGB değerlerinden birini yakından yaklaştırın bir renk kullanın. Eşleme, tam RGB değerlerine göre yapılır.

|RGB değeri|Dinamik olarak eşlenmiş renk değeri|
|---------------|------------------------------------|
|RGB (000, 000, 000)|COLOR_BTNTEXT|
|RGB (128, 128, 128)|COLOR_BTNSHADOW|
|RGB (192, 192, 192)|COLOR_BTNFACE|
|RGB (255, 255, 255)|COLOR_BTNHIGHLIGHT|

Oluşturma ve özelleştirme API 'Leri hakkındaki ayrıntılar için sınıf *kitaplığı başvurusu* sınıf [CToolBar](../mfc/reference/ctoolbar-class.md) ' a bakın `CToolBar` . Araç çubukları başlangıçta görünür hale gelmeden önce araç çubuklarının çoğu özelleştirmesi yapılmalıdır.

Özelleştirme API 'Leri, düğme kimliklerini, stilleri, ara değer genişliğini ve hangi düğme için kullanılan resim/glifi belirlemek için kullanılabilir. Varsayılan olarak, bu API 'Leri kullanmanız gerekmez.

## <a name="ccmdui-support-for-ctoolbar"></a>CToolBar için CCmdUI desteği

Araç çubuğu düğmelerinin her zaman güncelleştirilme şekli ON_UPDATE_COMMAND_UI mekanizmasıdır. Boş zamanlı olarak, araç çubuğu ON_UPDATE_COMMAND_UI işleyicisini o düğmenin komut KIMLIĞIYLE çağırır. Ayırıcılar için ON_UPDATE_COMMAND_UI çağrılmaz, ancak pushbuttons ve onay kutusu düğmeleri için çağırılır.

ON_UPDATE_COMMAND_UI işleyicisi şu şekilde çağırabilir:

- `Enable`: Düğmeyi etkinleştirmek veya devre dışı bırakmak için. Bu, itme düğmeleri ve onay kutusu düğmeleri için eşit olarak geçerlidir.

- `SetCheck`: Bir düğmenin denetim durumunu ayarlamak için. Bunu bir araç çubuğu düğmesi için çağırmak, bir onay kutusu düğmesine dönüştürür. `SetCheck` 0 (işaretli değil), 1 (işaretli) veya 2 (belirsiz) olabilen bir parametre alır

- `SetRadio`: İçin toplu değer `SetCheck` .

Onay kutusu düğmeleri "OTOMATIK" onay kutusu düğmelerdir; diğer bir deyişle, Kullanıcı bunlara bastığında hemen durumu değiştirir. Denetlenen veya aşağı doğru bir durumdur. Bir düğmeyi "belirsiz" durumuna dönüştürmek için yerleşik bir kullanıcı arabirimi yolu yoktur; Bu, kod aracılığıyla yapılmalıdır.

Özelleştirme API 'Leri, belirli bir araç çubuğu düğmesinin durumunu değiştirmenize izin verir, tercihen araç çubuğu düğmesinin temsil ettiği komut için ON_UPDATE_COMMAND_UI işleyicisinde bu durumları değiştirmelisiniz. Boşta işleminin, araç çubuğu düğmelerinin durumunu ON_UPDATE_COMMAND_UI işleyicisiyle değiştirecek olduğunu unutmayın. bu nedenle, Bu durumlardaki tüm değişiklikler bir sonraki boşta kaldıktan sonra kaybolabilir.

Araç çubuğu düğmeleri, normal düğmeler veya menü öğeleri gibi WM_COMMAND iletiler gönderir ve normalde ON_UPDATE_COMMAND_UI işleyicisini sağlayan aynı sınıftaki bir ON_COMMAND işleyicisi tarafından işlenir.

Görüntüleme durumları için kullanılan dört araç çubuğu düğme stili (TBBS_ değeri) vardır:

- TBBS_CHECKED: onay kutusu şu anda işaretlendi (aşağı).

- TBBS_INDETERMINATE: onay kutusu şu anda belirsiz.

- TBBS_DISABLED: düğme Şu anda devre dışı.

- TBBS_PRESSED: düğme Şu anda basılmış.

Altı resmi Windows arabirimi uygulaması tasarım kılavuzu düğme stilleri aşağıdaki TBBS değerleriyle temsil edilir:

- Yukarı = 0

- Fare tuşu = TBBS_PRESSED (diğer herhangi bir stil &#124;)

- Devre dışı = TBBS_DISABLED

- Aşağı = TBBS_CHECKED

- Devre dışı = TBBS_CHECKED &#124; TBBS_DISABLED

- Belirsiz = TBBS_INDETERMINATE

## <a name="cdialogbar"></a><a name="_mfcnotes_cdialogbar"></a> CDialogBar

İletişim çubuğu, standart Windows denetimlerini içeren bir denetim çubuğudur. Bu, denetimleri içermesi ve aralarında sekme denetimi desteklemekte bir iletişim kutusu gibi davranır. Ayrıca, çubuğu göstermek için bir iletişim kutusu şablonu kullanan bir iletişim kutusu gibi davranır.

`CDialogBar`Standart basma düğmesi denetimleri içeren Yazdır-Önizle araç çubuğu için kullanılır.

Kullanmak gibi bir kullanın `CDialogBar` `CFormView` . İletişim çubuğu için bir iletişim kutusu şablonu tanımlamanız ve WS_CHILD dışındaki tüm stilleri kaldırmanız gerekir. İletişim kutusunun görünür olmaması gerektiğini unutmayın.

A için denetim bildirimleri `CDialogBar` denetim çubuğunun üst öğesine (tıpkı araç çubuğu düğmeleri gibi) gönderilir.

## <a name="ccmdui-support-for-cdialogbar"></a>CDialogBar için CCmdUI desteği

İletişim çubuğu düğmeleri ON_UPDATE_COMMAND_UI işleyicisi mekanizması aracılığıyla güncelleştirilmeleri gerekir. Boş zamanlı olarak, iletişim çubuğu ON_UPDATE_COMMAND_UI işleyicisini KIMLIĞI >= 0x8000 olan tüm düğmelerin komut KIMLIĞIYLE (komut kimlikleri aralığında) çağırır.

ON_UPDATE_COMMAND_UI işleyicisi şu şekilde çağırabilir:

- Etkinleştir: düğmeyi etkinleştirmek veya devre dışı bırakmak için.

- SetText: düğmenin metnini değiştirmek için.

Özelleştirme, standart Pencere Yöneticisi API 'Leri aracılığıyla yapılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
