---
title: COleControlContainer Sınıfı
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
ms.openlocfilehash: 83171e012db7ef2cce459d35cfc689746afd062c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749017"
---
# <a name="colecontrolcontainer-class"></a>COleControlContainer Sınıfı

ActiveX denetimleri için bir kontrol kapsayıcısı görevi görür.

## <a name="syntax"></a>Sözdizimi

```
class COleControlContainer : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleControlContainer::COleControlContainer](#colecontrolcontainer)|Bir `COleControlContainer` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleControlContainer::AttachControlSite](#attachcontrolsite)|Kapsayıcı tarafından barındırılan bir denetim sitesi oluşturur.|
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|Barındırılan tüm denetimleri ortam özelliğinin değiştiğini bildirir.|
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|Belirtilen düğme denetimini değiştirir.|
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|Bir grubun belirtilen radyo düğmesini seçer.|
|[COleControlContainer::CreateControl](#createcontrol)|Barındırılan activex denetimi oluşturur.|
|[COleControlContainer::CreateOleFont](#createolefont)|Bir OLE yazı tipi oluşturur.|
|[COleControlContainer::FindItem](#finditem)|Belirtilen denetimin özel sitesini döndürür.|
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|Denetim sitesinin olayları kabul edip etmediğini belirler.|
|[COleControlContainer::GetAmbientProp](#getambientprop)|Belirtilen ortam özelliğini alır.|
|[COleControlContainer::GetDlgItem](#getdlgitem)|Belirtilen iletişim denetimini alır.|
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|Belirtilen iletişim denetiminin değerini alır.|
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|Belirtilen iletişim denetiminin alt yazısını alır.|
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|Kapsayıcının WM_SETFOCUS iletileri işleyeceğini belirler.|
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|Penceresiz denetime gönderilen iletileri işler.|
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|Belirtilen düğmenin durumunu belirler.|
|[COleControlContainer::OnPaint](#onpaint)|Kapsayıcının bir kısmını yeniden boyamak için çağrıldı.|
|[COleControlContainer::OnUIActivate](#onuiactivate)|Bir denetim yerinde etkinleştirilmek üzereyken çağrılır.|
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|Denetim devre dışı bırakılmak üzereyken çağrılır.|
|[COleControlContainer::ScrollChildren](#scrollchildren)|Kaydırma iletileri bir alt pencereden alındığı zaman çerçeve tarafından çağrılır.|
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|Belirtilen denetime ileti gönderir.|
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|Belirtilen denetimin değerini ayarlar.|
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|Belirtilen denetimin metnini ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleControlContainer::m_crBack](#m_crback)|Kapsayıcının arka plan rengi.|
|[COleControlKonteyner::m_crFore](#m_crfore)|Konteynerin ön plan rengi.|
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|Desteklenen denetim sitelerinin listesi.|
|[COleControlKonteyner::m_nWindowlessControls](#m_nwindowlesscontrols)|Barındırılan penceresiz denetimlerin sayısı.|
|[COleControlKonteyner::m_pOleFont](#m_polefont)|Özel denetim sitesinin OLE yazı tipine işaretçi.|
|[COleControlKonteyner::m_pSiteCapture](#m_psitecapture)|Yakalama denetim sitesine işaretçi.|
|[COleControlKonteyner::m_pSiteFocus](#m_psitefocus)|Giriş odağı olan denetime işaretçi.|
|[COleControlKonteyner::m_pSiteUIActive](#m_psiteuiactive)|Şu anda yerinde etkinleştirilen denetimi işaretçi.|
|[COleControlContainer::m_pWnd](#m_pwnd)|Denetim kapsayıcısını uygulayan pencereyi işaretçi.|
|[COleControlKonteyner::m_siteMap](#m_sitemap)|Site haritası.|

## <a name="remarks"></a>Açıklamalar

Bu bir veya daha fazla ActiveX kontrol siteleri (tarafından `COleControlSite`uygulanan) için destek sağlayarak yapılır. `COleControlContainer`[iOleInPlaceFrame](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceframe) ve [IOleContainer](/windows/win32/api/oleidl/nn-oleidl-iolecontainer) arabirimlerini tam olarak uygulayarak, içerdiği ActiveX denetimlerinin yerinde öğeler olarak niteliklerini yerine getirmesine olanak tanır.

Genellikle, bu sınıf bir veya `COccManager` `COleControlSite` daha fazla ActiveX denetimleri için özel siteler ile özel bir ActiveX denetim kapsayıcı ile birlikte ve uygulamak için kullanılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlContainer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxocc.h

## <a name="colecontrolcontainerattachcontrolsite"></a><a name="attachcontrolsite"></a>COleControlContainer::AttachControlSite

Bir denetim sitesi oluşturmak ve eklemek için çerçeve tarafından çağrılır.

```
virtual void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);

void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Bir `CWnd` nesneye işaretçi.

*nIDC*<br/>
Eklenecek denetimin kimliği.

### <a name="remarks"></a>Açıklamalar

Bu işlemi özelleştirmek istiyorsanız bu işlevi geçersiz kılın.

> [!NOTE]
> MFC kitaplığına statik olarak bağlanAn bu işlevin ilk biçimini kullanın. MFC kitaplığına dinamik olarak bağlanAn ikinci formu kullanın.

## <a name="colecontrolcontainerbroadcastambientpropertychange"></a><a name="broadcastambientpropertychange"></a>COleControlContainer::BroadcastAmbientPropertyChange

Barındırılan tüm denetimleri ortam özelliğinin değiştiğini bildirir.

```
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```

### <a name="parameters"></a>Parametreler

*Dıspıd*<br/>
Ortam özelliğinin sevk kimliği değiştiriliyor.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ortam özelliği değeri değiştiğinde çerçeve tarafından çağrılır. Bu davranışı özelleştirmek için bu işlevi geçersiz kılın.

## <a name="colecontrolcontainercheckdlgbutton"></a><a name="checkdlgbutton"></a>COleControlContainer::CheckDlgButton

Düğmenin geçerli durumunu değiştirir.

```
virtual void CheckDlgButton(
    int nIDButton,
    UINT nCheck);
```

### <a name="parameters"></a>Parametreler

*nIDButton*<br/>
Değiştirilecek düğmenin kimliği.

*nCheck*<br/>
Düğmenin durumunu belirtir. Aşağıdakilerden biri olabilir:

- BST_CHECKED Kontrol etmek için düğme durumunu ayarlar.

- BST_INDETERMINATE Belirsiz bir durumu gösteren düğme durumunu griye ayarlar. Bu değeri yalnızca düğmede BS_3STATE veya BS_AUTO3STATE stili varsa kullanın.

- BST_UNCHECKED Düğme durumunun temizlenmesini ayarlar.

## <a name="colecontrolcontainercheckradiobutton"></a><a name="checkradiobutton"></a>COleControlContainer::CheckRadioButton

Bir grupta belirtilen bir radyo düğmesini seçer ve gruptaki kalan düğmeleri temizler.

```
virtual void CheckRadioButton(
    int nIDFirstButton,
    int nIDLastButton,
    int nIDCheckButton);
```

### <a name="parameters"></a>Parametreler

*nIDFirstButton*<br/>
Gruptaki ilk radyo düğmesinin tanımlayıcısını belirtir.

*nIDLastButton*<br/>
Gruptaki son radyo düğmesinin tanımlayıcısını belirtir.

*nIDCheckButton*<br/>
Denetlenecek radyo düğmesinin tanımlayıcısını belirtir.

## <a name="colecontrolcontainercolecontrolcontainer"></a><a name="colecontrolcontainer"></a>COleControlContainer::COleControlContainer

Bir `COleControlContainer` nesne inşa eder.

```
explicit COleControlContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Denetim kapsayıcısının üst penceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesne başarıyla oluşturulduktan sonra, ''ye `AttachControlSite`çağrı içeren özel bir denetim sitesi ekleyin.

## <a name="colecontrolcontainercreatecontrol"></a><a name="createcontrol"></a>COleControlContainer::CreateControl

Belirtilen `COleControlSite` nesne tarafından barındırılan bir ActiveX denetimi oluşturur.

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
Denetimi temsil eden pencere nesnesi için bir işaretçi.

*Clsıd*<br/>
Denetimin benzersiz sınıf kimliği.

*lpszWindowName*<br/>
Denetimde görüntülenecek metne işaretçi. Denetimin Resim Yazısı veya Metin özelliğinin değerini ayarlar (varsa). NULL ise, denetimin Resim Yazısı veya Metin özelliği değiştirilmez.

*Dwstyle*<br/>
Windows stilleri. Kullanılabilir stiller **Açıklamalar** bölümünde listelenir.

*Rect*<br/>
Denetimin boyutunu ve konumunu belirtir. Bir `CRect` nesne veya yapı `RECT` olabilir.

*Nıd*<br/>
Denetimin alt pencere kimliğini belirtir.

*pPersist*<br/>
Denetim için `CFile` kalıcı durumu içeren bir işaretçi. Varsayılan değer NULL'dur ve denetimin durumunu kalıcı depolamadan geri almadan kendisini başlattıgına işaret eder. NULL değilse, denetimin kalıcı verilerini `CFile`içeren türetilmiş bir nesneye akış veya depolama biçiminde işaretçi olmalıdır. Bu veriler istemcinin önceki etkinleştirme kaydedilmiş olabilir. Diğer `CFile` verileri içerebilir, ancak okuma-yazma işaretçisinin çağrı sırasında ki ilk kalıcı veri baytına `CreateControl`ayarlatılması gerekir.

*bDepolama*<br/>
*pPersist'deki* verilerin veri olarak `IStorage` mı `IStream` yorumlanması gerektiğini gösterir. *pPersist'deki* veriler bir depolama ysa, *bStorage* TRUE olmalıdır. *pPersist'deki* veriler bir akışsa, *bStorage* FALSE olmalıdır. Varsayılan değer FALSE'dur.

*bstrLicKey*<br/>
İsteğe bağlı lisans anahtar verileri. Bu veriler yalnızca çalışma zamanı lisans anahtarı gerektiren denetimler oluşturmak için gereklidir. Denetim lisanslamayı destekliyorsa, denetimin oluşturulmasının başarılı olması için bir lisans anahtarı sağlamanız gerekir. Varsayılan değer NULL'dur.

*ppNewSite*<br/>
Oluşturulan denetimi barındıracak varolan denetim sitesine işaretçi. Varsayılan değer NULL'dur ve yeni bir denetim sitesinin otomatik olarak oluşturulacağını ve yeni denetime eklendiğini gösterir.

*Ppt*<br/>
Denetimin sol `POINT` üst köşesini içeren bir yapıya işaretçi. Denetimin boyutu *psize*değerine göre belirlenir. *PPT* ve *psize* değerleri, denetimin boyutunu ve konumunu belirten isteğe bağlı bir yöntemdir.

*psize*<br/>
Denetimin boyutunu `SIZE` içeren bir yapıya işaretçi. Sol üst köşe *ppt*değerine göre belirlenir. *PPT* ve *psize* değerleri, denetimin boyutunu ve konumunu belirten isteğe bağlı bir yöntemdir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca Windows *dwStyle* bayraklarının bir alt `CreateControl`kümesi aşağıdakiler tarafından desteklenir:

- WS_VISIBLE Başlangıçta görünür bir pencere oluşturur. Denetimin sıradan pencereler gibi hemen görünür olmasını istiyorsanız gereklidir.

- WS_DISABLED Başlangıçta devre dışı bırakılmış bir pencere oluşturur. Devre dışı bırakılmış bir pencere kullanıcıdan giriş alamaz. Denetimetkin bir özelliği varsa ayarlanabilir.

- WS_BORDER ince çizgi kenarlıklı bir pencere oluşturur. Denetimin BorderStyle özelliği varsa ayarlanabilir.

- WS_GROUP Bir denetim grubunun ilk denetimini belirtir. Kullanıcı yön tuşlarını kullanarak klavye odağı gruptaki bir denetimden diğerine değiştirebilir. İlk denetimden sonra WS_GROUP stili ile tanımlanan tüm denetimler aynı gruba aittir. WS_GROUP stili ile bir sonraki denetim grubu sona erdirer ve bir sonraki grubu başlatır.

- WS_TABSTOP Kullanıcı TAB tuşuna bastığında klavye odağı alabilecek bir denetim belirtir. TAB tuşuna basıldığında klavye odağı WS_TABSTOP stilinin bir sonraki denetimine dönüşür.

Varsayılan boyutlu denetimler oluşturmak için ikinci aşırı yüklemeyi kullanın.

## <a name="colecontrolcontainercreateolefont"></a><a name="createolefont"></a>COleControlContainer::CreateOleFont

Bir OLE yazı tipi oluşturur.

```cpp
void CreateOleFont(CFont* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
Denetim kapsayıcısı tarafından kullanılacak yazı tipiiçin bir işaretçi.

## <a name="colecontrolcontainerfinditem"></a><a name="finditem"></a>COleControlContainer::FindItem

Belirtilen öğeyi barındıran özel siteyi bulur.

```
virtual COleControlSite* FindItem(UINT nID) const;
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Bulunacak öğenin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğenin özel sitesine bir işaretçi.

## <a name="colecontrolcontainerfreezeallevents"></a><a name="freezeallevents"></a>COleControlContainer::FreezeAllEvents

Kapsayıcının bağlı denetim sitelerindeki olayları yoksayacağını veya kabul edip edmeyeceğini belirler.

```cpp
void FreezeAllEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Parametreler

*bFreeze*<br/>
Olaylar işlenecekse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Denetim konteyneri tarafından istenirse olayları ateşlemeyi durdurmak için denetim gerekli değildir. Bu ateş devam edebilirsiniz ama sonraki tüm olaylar kontrol konteyner tarafından göz ardı edilecektir.

## <a name="colecontrolcontainergetambientprop"></a><a name="getambientprop"></a>COleControlContainer::GetAmbientProp

Belirtilen ortam özelliğinin değerini alır.

```
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,
    DISPID dispid,
    VARIANT* pvarResult);
```

### <a name="parameters"></a>Parametreler

*pSite*<br/>
Ortam özelliğinin alınacağı bir denetim sitesine işaretçi.

*Dıspıd*<br/>
İstenilen ortam özelliğinin sevk kimliği.

*pVarResult*<br/>
Ortam özelliğinin değerine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

## <a name="colecontrolcontainergetdlgitem"></a><a name="getdlgitem"></a>COleControlContainer::GetDlgItem

Bir iletişim kutusunda veya başka bir pencerede belirtilen denetim veya alt pencereiçin bir işaretçi alır.

```
virtual CWnd* GetDlgItem(int nID) const;

virtual void GetDlgItem(
    int nID,
    HWND* phWnd) const;
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Alınacak iletişim öğesinin tanımlayıcısı.

*phWnd*<br/>
Belirtilen iletişim öğesinin pencere nesnesinin tanıtıcısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İletişim öğesinin penceresine işaretçi.

## <a name="colecontrolcontainergetdlgitemint"></a><a name="getdlgitemint"></a>COleControlContainer::GetDlgItemInt

Verilen denetimin çevrilen metninin değerini alır.

```
virtual UINT GetDlgItemInt(
    int nID,
    BOOL* lpTrans,
    BOOL bSigned) const;
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Denetimin tanımlayıcısı.

*lpTrans*<br/>
İşlev başarı/hata değeri alan bir Boolean değişkenine işaretçi (TRUE başarıyı gösterir, FALSE başarısızlığı gösterir).

*bİmzalandı*<br/>
İşlevin başında eksi işareti için metni incelemesi ve bir tane bulursa imzalı bir tamsayı değerini döndürüp döndürmemesi gerektiğini belirtir. Bİmzaparametresi TRUE ise, alınacak değerin imzalı bir tamsayı değeri olduğunu belirterek, iade değerini **int** türüne döküm. *bSigned* Genişletilmiş hata bilgilerini almak için [GetLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)arayın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *lpTrans* tarafından işaret edilen değişken TRUE olarak ayarlanır ve iade değeri kontrol metninin çevrilmiş değeridir.

İşlev başarısız olursa, *lpTrans* tarafından işaret edilen değişken FALSE olarak ayarlanır ve geri dönüş değeri sıfırdır. Sıfır olası çevrilmiş bir değer olduğundan, sıfırın dönüş değerinin tek başına hata yılıdığını göstermediğini unutmayın.

*lpTrans* NULL ise, işlev başarı veya başarısızlık hakkında hiçbir bilgi döndürür.

### <a name="remarks"></a>Açıklamalar

İşlev, metnin başındaki fazladan boşlukları sıyırıp ondalık basamakları dönüştürerek alınan metni çevirir. Işlev, metnin sonuna ulaştığında veya sayısal olmayan bir karakterle karşılaştığında çevirmeyi durdurur.

Çevrilen değer INT_MAX (imzalı sayılar için) veya UINT_MAX (imzalanmamış sayılar için) büyükse bu işlev sıfır döndürür.

## <a name="colecontrolcontainergetdlgitemtext"></a><a name="getdlgitemtext"></a>COleControlContainer::GetDlgItemText

Verilen denetimin metnini alır.

```
virtual int GetDlgItemText(
    int nID,
    LPTSTR lpStr,
    int nMaxCount) const;
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Denetimin tanımlayıcısı.

*Lpstr*<br/>
Denetim metnine işaretçi.

*nMaxCount*<br/>
LPStr tarafından işaret edilen arabelleğe kopyalanacak dize, karakterlerdeki maksimum *lpStr*uzunluğu belirtir. Dize uzunluğu sınırı aşarsa, dize kesilir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, iade değeri arabelleğe kopyalanan karakter sayısını belirtir, sonlandırıcı null karakteri dahil değil.

İşlev başarısız olursa, geri dönüş değeri sıfırdır. Genişletilmiş hata bilgilerini almak için [GetLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)arayın.

## <a name="colecontrolcontainerhandlesetfocus"></a><a name="handlesetfocus"></a>COleControlContainer::HandleSetFocus

Kapsayıcının WM_SETFOCUS iletileri işleyeceğini belirler.

```
virtual BOOL HandleSetFocus();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcı WM_SETFOCUS iletileri işlerse sıfırolmayan; aksi takdirde sıfır.

## <a name="colecontrolcontainerhandlewindowlessmessage"></a><a name="handlewindowlessmessage"></a>COleControlContainer::HandleWindowlessMessage

Penceresi iletilerini penceresiz denetimler için işler.

```
virtual BOOL HandleWindowlessMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```

### <a name="parameters"></a>Parametreler

*İleti*<br/>
Windows tarafından sağlanan pencere iletisinin tanımlayıcısı.

*Wparam*<br/>
İletinin parametresi; Windows tarafından sağlanır. İletiye özgü ek bilgileri belirtir. Bu parametrenin içeriği *ileti* parametresinin değerine bağlıdır.

*Lparam*<br/>
İletinin parametresi; Windows tarafından sağlanır. İletiye özgü ek bilgileri belirtir. Bu parametrenin içeriği *ileti* parametresinin değerine bağlıdır.

*plResult*<br/>
Windows sonuç kodu. İleti işleme nin sonucunu belirtir ve gönderilen iletiye bağlıdır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Penceresiz denetim iletilerinin işlenmesini özelleştirmek için bu işlevi geçersiz kılın.

## <a name="colecontrolcontainerisdlgbuttonchecked"></a><a name="isdlgbuttonchecked"></a>COleControlContainer::IsDlgButtonChecked

Belirtilen düğmenin durumunu belirler.

```
virtual UINT IsDlgButtonChecked(int nIDButton) const;
```

### <a name="parameters"></a>Parametreler

*nIDButton*<br/>
Düğme denetiminin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON veya BS_3STATE stiliyle oluşturulan bir düğmeden gelen iade değeri. Aşağıdakilerden biri olabilir:

- BST_CHECKED Button kontrol edilir.

- BST_INDETERMINATE Düğmesi belirsiz bir durumu belirten gri renktedir (yalnızca düğmede BS_3STATE veya BS_AUTO3STATE stili varsa geçerlidir).

- BST_UNCHECKED Button temizlendi.

### <a name="remarks"></a>Açıklamalar

Düğme üç durumlu bir denetimse, üye işlev soluk olup olmadığını, denetlenip işaretlenmediğini veya olmadığını belirler.

## <a name="colecontrolcontainerm_crback"></a><a name="m_crback"></a>COleControlContainer::m_crBack

Kapsayıcının arka plan rengi.

```
COLORREF m_crBack;
```

## <a name="colecontrolcontainerm_crfore"></a><a name="m_crfore"></a>COleControlKonteyner::m_crFore

Konteynerin ön plan rengi.

```
COLORREF m_crFore;
```

## <a name="colecontrolcontainerm_listsitesorwnds"></a><a name="m_listsitesorwnds"></a>COleControlContainer::m_listSitesOrWnds

Kapsayıcı tarafından barındırılan kontrol sitelerinin listesi.

```
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;
```

## <a name="colecontrolcontainerm_nwindowlesscontrols"></a><a name="m_nwindowlesscontrols"></a>COleControlKonteyner::m_nWindowlessControls

Denetim kapsayıcısı tarafından barındırılan penceresiz denetimlerin sayısı.

```
int m_nWindowlessControls;
```

## <a name="colecontrolcontainerm_polefont"></a><a name="m_polefont"></a>COleControlKonteyner::m_pOleFont

Özel denetim sitesinin OLE yazı tipine işaretçi.

```
LPFONTDISP m_pOleFont;
```

## <a name="colecontrolcontainerm_psitecapture"></a><a name="m_psitecapture"></a>COleControlKonteyner::m_pSiteCapture

Yakalama denetim sitesine işaretçi.

```
COleControlSite* m_pSiteCapture;
```

## <a name="colecontrolcontainerm_psitefocus"></a><a name="m_psitefocus"></a>COleControlKonteyner::m_pSiteFocus

Şu anda giriş odağı olan denetim sitesine işaretçi.

```
COleControlSite* m_pSiteFocus;
```

## <a name="colecontrolcontainerm_psiteuiactive"></a><a name="m_psiteuiactive"></a>COleControlKonteyner::m_pSiteUIActive

Yerinde etkinleştirilen denetim sitesine işaretçi.

```
COleControlSite* m_pSiteUIActive;
```

## <a name="colecontrolcontainerm_pwnd"></a><a name="m_pwnd"></a>COleControlContainer::m_pWnd

Kapsayıcıyla ilişkili pencere nesnesi için bir işaretçi.

```
CWnd* m_pWnd;
```

## <a name="colecontrolcontainerm_sitemap"></a><a name="m_sitemap"></a>COleControlKonteyner::m_siteMap

Site haritası.

```
CMapPtrToPtr m_siteMap;
```

## <a name="colecontrolcontaineronpaint"></a><a name="onpaint"></a>COleControlContainer::OnPaint

WM_PAINT isteklerini işlemek için çerçeve tarafından çağrıldı.

```
virtual BOOL OnPaint(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Kapsayıcı tarafından kullanılan aygıt bağlamına bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfır olmayan; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Boyama işlemini özelleştirmek için bu işlevi geçersiz kılın.

## <a name="colecontrolcontaineronuiactivate"></a><a name="onuiactivate"></a>COleControlContainer::OnUIActivate

Çerçeve tarafından çağrılan kontrol sitesi, *pSite*tarafından işaret edildiğinde, yerinde etkinleştirilmek üzeredir.

```
virtual void OnUIActivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Parametreler

*pSite*<br/>
Yerinde etkinleştirilmek üzere olan denetim sitesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Yerinde etkinleştirme, kapsayıcının ana menüsünün yerinde bileşik bir menüyle değiştirilmesi anlamına gelir.

## <a name="colecontrolcontaineronuideactivate"></a><a name="onuideactivate"></a>COleControlContainer::OnUIDeactivate

Çerçeve tarafından çağrılan kontrol sitesi, *pSite*tarafından işaret edildiğinde, devre dışı bırakılmak üzeredir.

```
virtual void OnUIDeactivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Parametreler

*pSite*<br/>
Denetim sitesine işaretçi devre dışı bırakılmak üzere.

### <a name="remarks"></a>Açıklamalar

Bu bildirim alındığı zaman, kapsayıcı kullanıcı arabirimini yeniden yüklemeli ve odak almalıdır.

## <a name="colecontrolcontainerscrollchildren"></a><a name="scrollchildren"></a>COleControlContainer::ScrollChildren

Kaydırma iletileri bir alt pencereden alındığı zaman çerçeve tarafından çağrılır.

```
virtual void ScrollChildren(
    int dx,
    int dy);
```

### <a name="parameters"></a>Parametreler

*Dx*<br/>
Piksel olarak x ekseni boyunca kaydırma miktarı.

*Dy*<br/>
Y ekseni boyunca kaydırmanın piksel olarak miktarı.

## <a name="colecontrolcontainersenddlgitemmessage"></a><a name="senddlgitemmessage"></a>COleControlContainer::SendDlgItemMessage

Belirtilen denetime ileti gönderir.

```
virtual LRESULT SendDlgItemMessage(
    int nID,
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
İletiyi alan denetimin tanımlayıcısını belirtir.

*İleti*<br/>
Gönderilecek iletiyi belirtir.

*Wparam*<br/>
İletiye özgü ek bilgileri belirtir.

*Lparam*<br/>
İletiye özgü ek bilgileri belirtir.

## <a name="colecontrolcontainersetdlgitemint"></a><a name="setdlgitemint"></a>COleControlContainer::SetDlgItemInt

İletişim kutusundaki denetim metnini, belirtilen bir tamsayı değerinin dize gösterimine ayarlar.

```
virtual void SetDlgItemInt(
    int nID,
    UINT nValue,
    BOOL bSigned);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Denetimin tanımlayıcısı.

*nDeğer*<br/>
Görüntülenecek olan tümsesayı değeri.

*bİmzalandı*<br/>
*nValue* parametresinin imzalı veya imzasız olup olmadığını belirtir. Bu parametre TRUE ise, *nValue* imzalanır. Bu parametre TRUE ise ve *nValue* sıfırdan küçükse, dizedeki ilk basamaktan önce eksi işareti yerleştirilir. Bu parametre FALSE ise, *nValue* imzasızdır.

## <a name="colecontrolcontainersetdlgitemtext"></a><a name="setdlgitemtext"></a>COleControlContainer::SetDlgItemText

*LPSZString'te*yer alan metni kullanarak belirtilen denetimin metnini ayarlar.

```
virtual void SetDlgItemText(
    int nID,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Denetimin tanımlayıcısı.

*lpszString*<br/>
Denetim metnine işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite Sınıfı](../../mfc/reference/colecontrolsite-class.md)<br/>
[COccManager Sınıfı](../../mfc/reference/coccmanager-class.md)
