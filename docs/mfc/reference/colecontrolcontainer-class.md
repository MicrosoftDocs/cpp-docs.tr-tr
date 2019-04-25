---
title: COleControlContainer sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleControlContainer
- AFXOCC/COleControlContainer
- AFXOCC/COleControlContainer::COleControlContainer
- AFXOCC/COleControlContainer::AttachControlSite
- AFXOCC/COleControlContainer::BroadcastAmbientPropertyChange
- AFXOCC/COleControlContainer::CheckDlgButton
- AFXOCC/COleControlContainer::CheckRadioButton
- AFXOCC/COleControlContainer::CreateControl
- AFXOCC/COleControlContainer::CreateOleFont
- AFXOCC/COleControlContainer::FindItem
- AFXOCC/COleControlContainer::FreezeAllEvents
- AFXOCC/COleControlContainer::GetAmbientProp
- AFXOCC/COleControlContainer::GetDlgItem
- AFXOCC/COleControlContainer::GetDlgItemInt
- AFXOCC/COleControlContainer::GetDlgItemText
- AFXOCC/COleControlContainer::HandleSetFocus
- AFXOCC/COleControlContainer::HandleWindowlessMessage
- AFXOCC/COleControlContainer::IsDlgButtonChecked
- AFXOCC/COleControlContainer::OnPaint
- AFXOCC/COleControlContainer::OnUIActivate
- AFXOCC/COleControlContainer::OnUIDeactivate
- AFXOCC/COleControlContainer::ScrollChildren
- AFXOCC/COleControlContainer::SendDlgItemMessage
- AFXOCC/COleControlContainer::SetDlgItemInt
- AFXOCC/COleControlContainer::SetDlgItemText
- AFXOCC/COleControlContainer::m_crBack
- AFXOCC/COleControlContainer::m_crFore
- AFXOCC/COleControlContainer::m_listSitesOrWnds
- AFXOCC/COleControlContainer::m_nWindowlessControls
- AFXOCC/COleControlContainer::m_pOleFont
- AFXOCC/COleControlContainer::m_pSiteCapture
- AFXOCC/COleControlContainer::m_pSiteFocus
- AFXOCC/COleControlContainer::m_pSiteUIActive
- AFXOCC/COleControlContainer::m_pWnd
- AFXOCC/COleControlContainer::m_siteMap
helpviewer_keywords:
- COleControlContainer [MFC], COleControlContainer
- COleControlContainer [MFC], AttachControlSite
- COleControlContainer [MFC], BroadcastAmbientPropertyChange
- COleControlContainer [MFC], CheckDlgButton
- COleControlContainer [MFC], CheckRadioButton
- COleControlContainer [MFC], CreateControl
- COleControlContainer [MFC], CreateOleFont
- COleControlContainer [MFC], FindItem
- COleControlContainer [MFC], FreezeAllEvents
- COleControlContainer [MFC], GetAmbientProp
- COleControlContainer [MFC], GetDlgItem
- COleControlContainer [MFC], GetDlgItemInt
- COleControlContainer [MFC], GetDlgItemText
- COleControlContainer [MFC], HandleSetFocus
- COleControlContainer [MFC], HandleWindowlessMessage
- COleControlContainer [MFC], IsDlgButtonChecked
- COleControlContainer [MFC], OnPaint
- COleControlContainer [MFC], OnUIActivate
- COleControlContainer [MFC], OnUIDeactivate
- COleControlContainer [MFC], ScrollChildren
- COleControlContainer [MFC], SendDlgItemMessage
- COleControlContainer [MFC], SetDlgItemInt
- COleControlContainer [MFC], SetDlgItemText
- COleControlContainer [MFC], m_crBack
- COleControlContainer [MFC], m_crFore
- COleControlContainer [MFC], m_listSitesOrWnds
- COleControlContainer [MFC], m_nWindowlessControls
- COleControlContainer [MFC], m_pOleFont
- COleControlContainer [MFC], m_pSiteCapture
- COleControlContainer [MFC], m_pSiteFocus
- COleControlContainer [MFC], m_pSiteUIActive
- COleControlContainer [MFC], m_pWnd
- COleControlContainer [MFC], m_siteMap
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
ms.openlocfilehash: 6e97f7ceafb92098d701cba64b4ec01d26d3991a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310444"
---
# <a name="colecontrolcontainer-class"></a>COleControlContainer sınıfı

ActiveX denetimleri için Denetim kapsayıcısı gibi davranır.

## <a name="syntax"></a>Sözdizimi

```
class COleControlContainer : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleControlContainer::COleControlContainer](#colecontrolcontainer)|Oluşturur bir `COleControlContainer` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleControlContainer::AttachControlSite](#attachcontrolsite)|Kapsayıcı tarafından barındırılan bir denetim site oluşturur.|
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|Bir ortam özelliğin değiştirildiğini barındırılan tüm denetimleri bildirir.|
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|Belirtilen bir düğme denetimini değiştirir.|
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|Bir grubun belirtilen radyo düğmesini seçer.|
|[COleControlContainer::CreateControl](#createcontrol)|Barındırılan bir ActiveX denetimi oluşturur.|
|[COleControlContainer::CreateOleFont](#createolefont)|Bir OLE yazı tipi oluşturur.|
|[COleControlContainer::FindItem](#finditem)|Belirtilen denetimin özel site döndürür.|
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|Site denetim olayları kabul ediyor belirler.|
|[COleControlContainer::GetAmbientProp](#getambientprop)|Belirtilen ortam özelliği alır.|
|[COleControlContainer::GetDlgItem](#getdlgitem)|Belirtilen bir iletişim denetimi alır.|
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|Belirtilen bir iletişim kutusu denetiminin değerini alır.|
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|Belirtilen bir iletişim denetimi başlığını alır.|
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|Kapsayıcı WM_SETFOCUS iletilerini işleme, belirler.|
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|Penceresiz denetime gönderilen iletileri işler.|
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|Belirtilen düğmenin durumunu belirler.|
|[COleControlContainer::OnPaint](#onpaint)|Kapsayıcı bir kısmını çizilecek çağrılır.|
|[COleControlContainer::OnUIActivate](#onuiactivate)|Bir denetimi hakkında yerinde etkin olması için çağrılır.|
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|Bir denetim hakkında devre dışı olduğunda çağrılır.|
|[COleControlContainer::ScrollChildren](#scrollchildren)|Bir alt penceresinden kaydırma iletileri alındığında framework tarafından çağırılır.|
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|Belirtilen denetime bir ileti gönderir.|
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|Belirtilen bir denetimin değerini ayarlar.|
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|Belirtilen denetim metnini ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleControlContainer::m_crBack](#m_crback)|Kapsayıcı arka plan rengi.|
|[COleControlContainer::m_crFore](#m_crfore)|Kapsayıcı ön plan rengi.|
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|Desteklenen denetim sitelerini listesi.|
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|Barındırılan penceresiz denetimleri sayısı.|
|[COleControlContainer::m_pOleFont](#m_polefont)|Özel denetim site OLE yazı tipi için bir işaretçi.|
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|Yakalama denetim site işaretçisi.|
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|Şu anda odağı giriş denetimi işaretçisi.|
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|Yerinde etkinleştirilmiş denetimine yönelik işaretçi.|
|[COleControlContainer::m_pWnd](#m_pwnd)|Denetim kapsayıcı uygulama penceresi işaretçisi.|
|[COleControlContainer::m_siteMap](#m_sitemap)|Site haritası.|

## <a name="remarks"></a>Açıklamalar

Bu bir veya daha fazla ActiveX denetimi siteleri için destek sağlayarak gerçekleştirilir (tarafından uygulanan `COleControlSite`). `COleControlContainer` tam olarak uygular [IOleInPlaceFrame](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceframe) ve [IOleContainer](/windows/desktop/api/oleidl/nn-oleidl-iolecontainer) arabirimleri, yerinde öğeleri olarak niteliklerinin karşılamak kapsanan ActiveX denetimlerini izin verme.

Yaygın olarak, bu sınıf ile birlikte kullanılan `COccManager` ve `COleControlSite` özel sitelerle bir veya daha fazla ActiveX denetimleri için özel bir ActiveX denetimi kapsayıcısı uygulamak için.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlContainer`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxocc.h

##  <a name="attachcontrolsite"></a>  COleControlContainer::AttachControlSite

Oluşturup bir denetim site eklemek için framework tarafından çağırılır.

```
virtual void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);

void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Bir işaretçi bir `CWnd` nesne.

*nIDC*<br/>
Eklenecek denetimin kimliği.

### <a name="remarks"></a>Açıklamalar

Bu işlem özelleştirmek istiyorsanız, bu işlev geçersiz kılar.

> [!NOTE]
>  MFC Kitaplığı'na statik olarak bağlıyorsanız, bu işlevin ilk formu kullanın. MFC kitaplığına dinamik olarak bağlıyorsanız, ikinci formu kullanın.

##  <a name="broadcastambientpropertychange"></a>  COleControlContainer::BroadcastAmbientPropertyChange

Bir ortam özelliğin değiştirildiğini barındırılan tüm denetimleri bildirir.

```
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```

### <a name="parameters"></a>Parametreler

*DISPID*<br/>
Ortam değişmekte olan özelliğe gönderme kimliği.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir çevresel özelliğe değeri değiştiğinde framework tarafından çağırılır. Bu işlev, bu davranışını özelleştirmek için geçersiz kılın.

##  <a name="checkdlgbutton"></a>  COleControlContainer::CheckDlgButton

Düğme geçerli durumunu değiştirir.

```
virtual void CheckDlgButton(
    int nIDButton,
    UINT nCheck);
```

### <a name="parameters"></a>Parametreler

*nIDButton*<br/>
Değiştirilecek düğme kimliği.

*Nbakım*<br/>
Düğmenin durumunu belirtir. Aşağıdakilerden biri olabilir:

- BST_CHECKED Ayarlar düğmesi durumuna teslim.

- BST_INDETERMINATE düğmesi durumuna gri, ayarlar belirlenmemiş bir durum gösteren. Yalnızca düğme BS_3STATE veya BS_AUTO3STATE bir stile sahipse, bu değeri kullanın.

- BST_UNCHECKED Ayarlar düğmesi durumuna temizlendi.

##  <a name="checkradiobutton"></a>  COleControlContainer::CheckRadioButton

Bir grupta belirtilen radyo düğmesini seçer ve gruptaki diğer düğmeleri temizler.

```
virtual void CheckRadioButton(
    int nIDFirstButton,
    int nIDLastButton,
    int nIDCheckButton);
```

### <a name="parameters"></a>Parametreler

*nIDFirstButton*<br/>
İlk radyo düğmesi grubunda belirtir.

*nIDLastButton*<br/>
Son radyo düğmesi grubunda belirtir.

*nIDCheckButton*<br/>
Denetlenecek radyo düğmesinin tanımlayıcısını belirtir.

##  <a name="colecontrolcontainer"></a>  COleControlContainer::COleControlContainer

Oluşturur bir `COleControlContainer` nesne.

```
explicit COleControlContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Denetim kapsayıcısının üst penceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesne başarıyla oluşturulduktan sonra bir özel denetim site çağrısıyla eklemek `AttachControlSite`.

##  <a name="createcontrol"></a>  COleControlContainer::CreateControl

Belirtilen tarafından barındırılan bir ActiveX denetimi oluşturur `COleControlSite` nesne.

```
BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);

BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);
```

### <a name="parameters"></a>Parametreler

*pWndCtrl*<br/>
Bir denetimi temsil eden pencere nesnesini bir işaretçi.

*CLSID*<br/>
Denetim sınıfı benzersiz kimliği.

*lpszWindowName*<br/>
Denetimde görüntülenecek metni için bir işaretçi. Denetimin açıklamalı alt yazı veya metin özelliğini değerini (varsa) ayarlar. NULL ise, denetimin açıklamalı alt yazı veya metin özelliğini değiştirilmez.

*dwStyle*<br/>
Windows stilleri. Kullanılabilir stiller altında listelenen **açıklamalar** bölümü.

*Rect*<br/>
Denetimin boyutunu ve konumunu belirtir. Ya da olabilir bir `CRect` nesnesi veya bir `RECT` yapısı.

*nID*<br/>
Denetimin alt penceresi kimliğini belirtir.

*pPersist*<br/>
Bir işaretçi bir `CFile` denetim kalıcı durumunu içeren. NULL denetimi kendisini herhangi bir kalıcı depolama alanından durumuna geri yüklemeden başlatır olduğunu belirten, varsayılan değerdir. BOŞ değilse, bir işaretçi olmalıdır bir `CFile`-türetilmiş bir akış veya bir depolama biçiminde denetimin kalıcı veri içeren nesne. Bu veriler istemcinin önceki bir etkinleştirme kaydedilmiş. `CFile` Diğer verileri içerebilir, ancak okuma-yazma işaretçisini yapılan çağrının zaman kalıcı veri ilk baytı için ayarlanmış olması gerekir `CreateControl`.

*bStorage*<br/>
Belirtir olup olmadığını verileri *pPersist* olarak yorumlanıp `IStorage` veya `IStream` veri. Varsa verilerde *pPersist* bir depolama alanıdır *bStorage* TRUE olmalıdır. Varsa verilerde *pPersist* bir akışı *bStorage* FALSE olmalıdır. Varsayılan değer FALSE olur.

*bstrLicKey*<br/>
İsteğe bağlı lisans anahtar verileri. Bu veriler, yalnızca bir çalışma zamanı lisans anahtarı gerekli denetimleri oluşturmak için gereklidir. Denetim lisanslama destekliyorsa, başarılı olması için Denetim oluşturulması için bir lisans anahtarı sağlamanız gerekir. Varsayılan değer NULL olur.

*ppNewSite*<br/>
Oluşturulan denetimi barındıran mevcut denetim site için bir işaretçi. NULL denetimi yeni bir site otomatik olarak oluşturulur ve yeni denetime bağlı olduğunu belirten, varsayılan değerdir.

*ppt*<br/>
Bir işaretçi bir `POINT` denetimin sol üst köşesinde içeren yapısı. Denetimin boyutu değeri tarafından belirlenir *psize*. *Ppt* ve *psize* değerler denetimin konumunu ve boyutunu belirten isteğe bağlı bir yöntem.

*psize*<br/>
Bir işaretçi bir `SIZE` denetiminin boyutunu içeren yapısı. Sol üst köşesinin değeri tarafından belirlenir *ppt*. *Ppt* ve *psize* değerler denetimin konumunu ve boyutunu belirten isteğe bağlı bir yöntem.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca bir alt kümesini Windows *dwStyle* bayrakları tarafından desteklenen `CreateControl`:

- Ws_vısıble başlangıçta görünen bir pencere oluşturur. Denetim normal windows gibi hemen görünür olmasını istiyorsanız gereklidir.

- Ws_dısabled başlangıçta devre dışı olan bir pencere oluşturur. Devre dışı bırakılmış bir pencere, kullanıcıdan giriş alamaz. Enabled özelliği denetimindeyse ayarlanabilir.

- WS_BORDER ince çizgi kenarlık ile bir pencere oluşturur. BorderStyle özelliği denetimindeyse ayarlanabilir.

- WS_GROUP denetimlerin grubundaki ilk denetimi belirtir. Kullanıcının klavye odağı grubundaki bir denetimden yanındaki yön tuşlarını kullanarak değiştirebilirsiniz. İlk kontrolden sonra aynı gruba WS_GROUP stiliyle tanımlanan tüm denetimler. WS_GROUP stili sonraki denetim grubun sona erer ve sonraki grubu başlatır.

- WS_TABSTOP kullanıcı TAB tuşuna bastığında klavye odağı alabilecek denetimini belirtir. Sekme tuşuna basarak klavye odağı sonraki denetime WS_TABSTOP stili değiştirir.

İkinci aşırı yükleme varsayılan boyutunda denetimler oluşturmak için kullanın.

##  <a name="createolefont"></a>  COleControlContainer::CreateOleFont

Bir OLE yazı tipi oluşturur.

```
void CreateOleFont(CFont* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
Denetim kapsayıcı tarafından kullanılacak yazı tipi için bir işaretçi.

##  <a name="finditem"></a>  COleControlContainer::FindItem

Belirtilen öğe barındıran özel sitesini bulur.

```
virtual COleControlSite* FindItem(UINT nID) const;
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Bulunacak öğe tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğenin özel site için bir işaretçi.

##  <a name="freezeallevents"></a>  COleControlContainer::FreezeAllEvents

Kapsayıcı veya ekli denetim sitelerden olaylarını yoksay koşulları kabul belirler.

```
void FreezeAllEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Parametreler

*bFreeze*<br/>
İşlenmeyebilir olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Denetim olayları denetim kapsayıcı tarafından isteniyorsa tetikleme durdurmak için gerekli değildir. Tetikleyicisinin tetikleme devam edebilirsiniz, ancak tüm sonraki olaylarda denetimi kapsayıcı tarafından göz ardı edilir.

##  <a name="getambientprop"></a>  COleControlContainer::GetAmbientProp

Belirtilen bir ortam özelliğinin değerini alır.

```
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,
    DISPID dispid,
    VARIANT* pvarResult);
```

### <a name="parameters"></a>Parametreler

*pSite*<br/>
Bir işaretçi bir denetim siteye çevresel özelliğe alınır.

*DISPID*<br/>
İstenen ortam özelliği gönderme kimliği.

*pVarResult*<br/>
Ortam özelliğinin değeri için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="getdlgitem"></a>  COleControlContainer::GetDlgItem

Bir iletişim kutusu belirtilen denetime veya alt penceresinde veya başka bir pencere için bir işaretçi alır.

```
virtual CWnd* GetDlgItem(int nID) const;

virtual void GetDlgItem(
    int nID,
    HWND* phWnd) const;
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Alınacak iletişim öğesinin tanıtıcısı.

*phWnd*<br/>
Belirtilen iletişim öğenin pencere nesnesi tanıtıcı bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İletişim öğenin penceresine bir işaretçi.

##  <a name="getdlgitemint"></a>  COleControlContainer::GetDlgItemInt

Verilen denetim çevrilmiş metnin değerini alır.

```
virtual UINT GetDlgItemInt(
    int nID,
    BOOL* lpTrans,
    BOOL bSigned) const;
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Denetim tanımlayıcısı.

*lpTrans*<br/>
Bir işlev başarı/hata değerini alan bir Boolean değişkeni işaretçisine (TRUE, başarı gösterir, FALSE, hata gösterir).

*bSigned*<br/>
İşlev ve başında bir eksi işareti metnini inceleyin bulursa bir işaretli tamsayı değeri döndürmek belirtir. Varsa *bSigned* parametresi TRUE, alınacak değerin bir işaretli tamsayı değer olduğunu belirtmek için dönüş değeri türüne bir **int** türü. Genişletilmiş hata bilgilerini almak için arama [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

### <a name="return-value"></a>Dönüş Değeri

Başarılı, değişkenin işaret ettiği varsa *lpTrans* TRUE olarak ayarlanır ve dönüş değeri çevrilmiş denetim metin değeri.

İşlev başarısız olursa, değişkeni tarafından işaret edilen *lpTrans* FALSE olarak ayarlanır ve dönüş değeri sıfırdır. Sıfır çevrilmiş bir olası değer olduğundan, dönüş değeri sıfır kendisi tarafından arıza olduğunu göstermez, unutmayın.

Varsa *lpTrans* NULL ise işlev başarı veya başarısızlık durumu hakkında bilgi verir.

### <a name="remarks"></a>Açıklamalar

İşlevi, metnin başında fazladan boşluk şeridi oluşturma ve daha sonra ondalık basamak dönüştürerek alınan metin çevirir. İşlevi, metni sonuna ulaştığında veya sayısal bir karakterle karşılaştığında çevirme durdurur.

Çevrilmiş değer INT_MAX (için işaretli sayılara) veya uınt_max (için işaretsiz sayıların) daha büyük ise bu işlev, sıfır döndürür.

##  <a name="getdlgitemtext"></a>  COleControlContainer::GetDlgItemText

Verilen denetim metnini alır.

```
virtual int GetDlgItemText(
    int nID,
    LPTSTR lpStr,
    int nMaxCount) const;
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Denetim tanımlayıcısı.

*lpStr*<br/>
Metin denetimi işaretçisi.

*nMaxCount*<br/>
Tarafından işaret edilen arabellek kopyalanacağı dizenin karakter cinsinden uzunluk üst sınırını belirtir *lpStr*. Dize uzunluğu sınırı aşarsa, dize kesildi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri arabelleğe sondaki null karakter hariç, kopyalanan karakter sayısını belirtir.

İşlev başarısız olursa, dönüş değeri sıfırdır. Genişletilmiş hata bilgilerini almak için arama [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

##  <a name="handlesetfocus"></a>  COleControlContainer::HandleSetFocus

Kapsayıcı WM_SETFOCUS iletilerini işleme, belirler.

```
virtual BOOL HandleSetFocus();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcı WM_SETFOCUS iletilerini işleme olursa sıfır dışı; Aksi halde sıfır.

##  <a name="handlewindowlessmessage"></a>  COleControlContainer::HandleWindowlessMessage

Penceresiz denetimleri için pencere iletileri işler.

```
virtual BOOL HandleWindowlessMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```

### <a name="parameters"></a>Parametreler

*message*<br/>
Windows tarafından sağlanan penceresi iletinin tanımlayıcısı.

*wParam*<br/>
İleti parametre; Windows tarafından sağlanan. Ek ileti özgü bilgileri belirtir. Bu parametre içeriği değerine bağlıdır *ileti* parametresi.

*lParam*<br/>
İleti parametre; Windows tarafından sağlanan. Ek ileti özgü bilgileri belirtir. Bu parametre içeriği değerine bağlıdır *ileti* parametresi.

*plResult*<br/>
Windows Sonuç kodu. İleti işleme sonucunu belirtir ve gönderilen ileti bağlıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu işlev penceresiz denetim iletilerinin işlenmesini özelleştirmek için geçersiz kılın.

##  <a name="isdlgbuttonchecked"></a>  COleControlContainer::IsDlgButtonChecked

Belirtilen düğmenin durumunu belirler.

```
virtual UINT IsDlgButtonChecked(int nIDButton) const;
```

### <a name="parameters"></a>Parametreler

*nIDButton*<br/>
Düğme denetimini tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

BS_AUTOCHECKBOX, bs_autoradıobutton, BS_AUTO3STATE, BS_CHECKBOX, bs_radıobutton veya BS_3STATE stiliyle oluşturulan bir düğmeyle dönüş değeri. Aşağıdakilerden biri olabilir:

- BST_CHECKED düğmesi denetlenir.

- (Yalnızca düğme BS_3STATE veya BS_AUTO3STATE stili varsa geçerlidir) belirlenmemiş bir durum gösteren BST_INDETERMINATE düğmesi renkte gösterilir.

- BST_UNCHECKED düğmesi temizlenir.

### <a name="remarks"></a>Açıklamalar

Düğmeyi üç durumlu denetimi, üye işlevi, işaretli soluk görünür olup olmadığını belirler veya hiçbiri.

##  <a name="m_crback"></a>  COleControlContainer::m_crBack

Kapsayıcı arka plan rengi.

```
COLORREF m_crBack;
```

##  <a name="m_crfore"></a>  COleControlContainer::m_crFore

Kapsayıcı ön plan rengi.

```
COLORREF m_crFore;
```

##  <a name="m_listsitesorwnds"></a>  COleControlContainer::m_listSitesOrWnds

Kapsayıcı tarafından barındırılan denetim sitelerini listesi.

```
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;
```

##  <a name="m_nwindowlesscontrols"></a>  COleControlContainer::m_nWindowlessControls

Denetim kapsayıcı tarafından barındırılan penceresiz denetimleri sayısı.

```
int m_nWindowlessControls;
```

##  <a name="m_polefont"></a>  COleControlContainer::m_pOleFont

Özel denetim site OLE yazı tipi için bir işaretçi.

```
LPFONTDISP m_pOleFont;
```

##  <a name="m_psitecapture"></a>  COleControlContainer::m_pSiteCapture

Yakalama denetim site işaretçisi.

```
COleControlSite* m_pSiteCapture;
```

##  <a name="m_psitefocus"></a>  COleControlContainer::m_pSiteFocus

Denetim site şu anda bir işaretçiye odak giriş.

```
COleControlSite* m_pSiteFocus;
```

##  <a name="m_psiteuiactive"></a>  COleControlContainer::m_pSiteUIActive

Yerinde etkinleştirilmiş denetim sitesi için bir işaretçi.

```
COleControlSite* m_pSiteUIActive;
```

##  <a name="m_pwnd"></a>  COleControlContainer::m_pWnd

Kapsayıcı ile ilişkili pencere nesnesi için bir işaretçi.

```
CWnd* m_pWnd;
```

##  <a name="m_sitemap"></a>  COleControlContainer::m_siteMap

Site haritası.

```
CMapPtrToPtr m_siteMap;
```

##  <a name="onpaint"></a>  COleControlContainer::OnPaint

WM_PAINT isteklerini işlemek için framework tarafından çağırılır.

```
virtual BOOL OnPaint(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Kapsayıcı tarafından kullanılan bir cihaz bağlamı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenmiş olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bu işlev boyama işlemi özelleştirmek için geçersiz kılın.

##  <a name="onuiactivate"></a>  COleControlContainer::OnUIActivate

Framework tarafından çağırılır zaman denetim site tarafından işaret edilen *pSite*, yaklaşık olacak yerinde etkinleştirilmiş.

```
virtual void OnUIActivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Parametreler

*pSite*<br/>
Denetim sitenin hakkında yerinde etkin olması için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Yerinde etkinleştirme kapsayıcının ana menü yerinde bileşik menüyü ile değiştirilir anlamına gelir.

##  <a name="onuideactivate"></a>  COleControlContainer::OnUIDeactivate

Framework tarafından çağırılır zaman denetim site tarafından işaret edilen *pSite*, yaklaşık devre dışı sağlamaktır.

```
virtual void OnUIDeactivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Parametreler

*pSite*<br/>
Yaklaşık devre dışı denetim site için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu bildirim alındığında, kapsayıcı kullanıcı arabirimiyle yeniden yükleyin ve odağı alması gerekir.

##  <a name="scrollchildren"></a>  COleControlContainer::ScrollChildren

Bir alt penceresinden kaydırma iletileri alındığında framework tarafından çağırılır.

```
virtual void ScrollChildren(
    int dx,
    int dy);
```

### <a name="parameters"></a>Parametreler

*DX*<br/>
X ekseni boyunca kaydırma miktarı, piksel cinsinden.

*GN*<br/>
Y ekseni boyunca kaydırma miktarı, piksel cinsinden.

##  <a name="senddlgitemmessage"></a>  COleControlContainer::SendDlgItemMessage

Belirtilen denetime bir ileti gönderir.

```
virtual LRESULT SendDlgItemMessage(
    int nID,
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
İletiyi alır denetimin tanımlayıcısını belirtir.

*message*<br/>
Gönderilecek iletiyi belirtir.

*wParam*<br/>
Ek ileti özgü bilgileri belirtir.

*lParam*<br/>
Ek ileti özgü bilgileri belirtir.

##  <a name="setdlgitemint"></a>  COleControlContainer::SetDlgItemInt

Belirtilen bir tamsayı değerini bir dize gösterimini iletişim kutusunda metin denetiminin ayarlar.

```
virtual void SetDlgItemInt(
    int nID,
    UINT nValue,
    BOOL bSigned);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Denetim tanımlayıcısı.

*nDeğer*<br/>
Görüntülenecek tamsayı değeri.

*bSigned*<br/>
Belirtir olup olmadığını *nDeğer* parametresi işaretli veya işaretlenmemiş. Bu parametre TRUE ise *nDeğer* imzalanır. Bu parametre TRUE ise ve *nDeğer* sıfırdan küçük, eksi işareti, dizedeki ilk basamak önce yerleştirilir. Bu parametre FALSE ise *nDeğer* imzalanmamış.

##  <a name="setdlgitemtext"></a>  COleControlContainer::SetDlgItemText

Metni yer alan metnini kullanarak belirtilen denetiminin ayarlar *lpszString*.

```
virtual void SetDlgItemText(
    int nID,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Denetim tanımlayıcısı.

*lpszString*<br/>
Metin denetimi işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite Sınıfı](../../mfc/reference/colecontrolsite-class.md)<br/>
[COccManager Sınıfı](../../mfc/reference/coccmanager-class.md)
