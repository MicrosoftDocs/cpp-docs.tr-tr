---
title: Cotacontrolcontainer sınıfı
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
ms.openlocfilehash: 3aa2515b1731eafcb5e3bcfa22a56ebbc1cdfdfb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504321"
---
# <a name="colecontrolcontainer-class"></a>Cotacontrolcontainer sınıfı

, ActiveX denetimleri için bir denetim kapsayıcısı işlevi görür.

## <a name="syntax"></a>Sözdizimi

```
class COleControlContainer : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cotacontrolcontainer:: Copacontrolcontainer](#colecontrolcontainer)|Bir `COleControlContainer` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotacontrolcontainer:: AttachControlSite](#attachcontrolsite)|Kapsayıcı tarafından barındırılan bir denetim sitesi oluşturur.|
|[Cotacontrolcontainer:: BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|Çevresel bir özelliğin değiştiği tüm barındırılan denetimlere bildirir.|
|[Cotacontrolcontainer:: CheckDlgButton](#checkdlgbutton)|Belirtilen düğme denetimini değiştirir.|
|[Cotacontrolcontainer:: CheckRadioButton](#checkradiobutton)|Bir grubun belirtilen radyo düğmesini seçer.|
|[Cotacontrolcontainer:: CreateControl](#createcontrol)|Barındırılan bir ActiveX denetimi oluşturur.|
|[Cotacontrolcontainer:: Createolefazı tipi](#createolefont)|OLE yazı tipi oluşturur.|
|[Cotacontrolcontainer:: FindItem](#finditem)|Belirtilen denetimin özel sitesini döndürür.|
|[Cotacontrolcontainer:: FreezeAllEvents](#freezeallevents)|Denetim sitesinin olayları kabul edip etmeyeceğini belirler.|
|[Cotacontrolcontainer:: Getambentprop](#getambientprop)|Belirtilen çevresel özelliği alır.|
|[Cotacontrolcontainer:: Getııbu öğe](#getdlgitem)|Belirtilen iletişim kutusu denetimini alır.|
|[Cotacontrolcontainer:: Getdlitemint](#getdlgitemint)|Belirtilen iletişim kutusu denetiminin değerini alır.|
|[Coincontrolcontainer:: Getdlıtemtext](#getdlgitemtext)|Belirtilen iletişim kutusu denetiminin resim yazısını alır.|
|[Cotacontrolcontainer:: HandleSetFocus](#handlesetfocus)|Kapsayıcının WM_SETFOCUS iletilerini işlediğini belirler.|
|[Cotacontrolcontainer:: HandleWindowlessMessage](#handlewindowlessmessage)|Penceresiz bir denetime gönderilen iletileri işler.|
|[Copacontrolcontainer:: ısıbir Buttonchecked](#isdlgbuttonchecked)|Belirtilen düğmenin durumunu belirler.|
|[Cotacontrolcontainer:: OnPaint](#onpaint)|Kapsayıcının bir bölümünü yeniden çizmek için çağırılır.|
|[Cotacontrolcontainer:: OnUIActivate](#onuiactivate)|Bir denetim yerinde etkinleştirilme için olduğunda çağırılır.|
|[Cotacontrolcontainer:: OnUIDeactivate](#onuideactivate)|Bir denetim devre dışı bırakılmakta olduğu zaman çağrılır.|
|[Cotacontrolcontainer:: ScrollChildren](#scrollchildren)|Bir alt pencereden kaydırma iletileri alındığında Framework tarafından çağırılır.|
|[Cotacontrolcontainer:: SendDlgItemMessage](#senddlgitemmessage)|Belirtilen denetime bir ileti gönderir.|
|[Cotacontrolcontainer:: Setdlitemint](#setdlgitemint)|Belirtilen denetimin değerini ayarlar.|
|[Cotacontrolcontainer:: Setdlıtemtext](#setdlgitemtext)|Belirtilen denetimin metnini ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cotacontrolcontainer:: m_crBack](#m_crback)|Kapsayıcının arka plan rengi.|
|[Cotacontrolcontainer:: m_crFore](#m_crfore)|Kapsayıcının ön plan rengi.|
|[Cotacontrolcontainer:: m_listSitesOrWnds](#m_listsitesorwnds)|Desteklenen denetim sitelerinin listesi.|
|[Cotacontrolcontainer:: m_nWindowlessControls](#m_nwindowlesscontrols)|Barındırılan penceresiz denetimlerin sayısı.|
|[Cotacontrolcontainer:: m_pOleFont](#m_polefont)|Özel denetim sitesinin OLE yazı tipine yönelik bir işaretçi.|
|[Cotacontrolcontainer:: m_pSiteCapture](#m_psitecapture)|Yakalama denetimi sitesinin işaretçisi.|
|[Cotacontrolcontainer:: m_pSiteFocus](#m_psitefocus)|Şu anda giriş odağına sahip olan denetimin işaretçisi.|
|[Cotacontrolcontainer:: m_pSiteUIActive](#m_psiteuiactive)|Şu anda yerinde etkinleştirilen denetimin işaretçisi.|
|[Cotacontrolcontainer:: m_pWnd](#m_pwnd)|Denetim kapsayıcısını uygulayan pencerenin işaretçisi.|
|[Cotacontrolcontainer:: m_siteMap](#m_sitemap)|Site haritası.|

## <a name="remarks"></a>Açıklamalar

Bu, bir veya daha fazla ActiveX Denetim sitesi (tarafından `COleControlSite`uygulanan) için destek sağlanarak yapılır. `COleControlContainer`, kapsanan ActiveX denetimlerinin niteliklerini yerinde öğeler olarak yerine getirmelerini sağlayan [IOleInPlaceFrame](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceframe) ve [IOleContainer](/windows/win32/api/oleidl/nn-oleidl-iolecontainer) arabirimlerini tamamen uygular.

Genellikle, bu sınıf bir veya daha fazla ActiveX `COccManager` denetimine `COleControlSite` yönelik özel sitelerle özel bir ActiveX Denetim kapsayıcısı uygulamak için ve ile birlikte kullanılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlContainer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxocc. h

##  <a name="attachcontrolsite"></a>Cotacontrolcontainer:: AttachControlSite

Bir denetim sitesi oluşturmak ve eklemek için Framework tarafından çağırılır.

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
Bir `CWnd` nesne işaretçisi.

*Nıdc*<br/>
Eklenecek denetimin KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu işlemi özelleştirmek istiyorsanız bu işlevi geçersiz kılın.

> [!NOTE]
>  MFC kitaplığına statik olarak bağlanıyorsanız, bu işlevin ilk biçimini kullanın. MFC kitaplığına dinamik olarak bağlanıyorsanız ikinci formu kullanın.

##  <a name="broadcastambientpropertychange"></a>Cotacontrolcontainer:: BroadcastAmbientPropertyChange

Çevresel bir özelliğin değiştiği tüm barındırılan denetimlere bildirir.

```
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
Değiştirilen çevresel özelliğin dağıtım KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir ortam özelliğinin değeri değiştiğinde Framework tarafından çağrılır. Bu davranışı özelleştirmek için bu işlevi geçersiz kılın.

##  <a name="checkdlgbutton"></a>Cotacontrolcontainer:: CheckDlgButton

Düğmenin geçerli durumunu değiştirir.

```
virtual void CheckDlgButton(
    int nIDButton,
    UINT nCheck);
```

### <a name="parameters"></a>Parametreler

*Nıdbutton*<br/>
Değiştirilecek düğmenin KIMLIĞI.

*Nhatayla*<br/>
Düğmenin durumunu belirtir. Aşağıdakilerden biri olabilir:

- BST_CHECKED, düğme durumunu işaretli olarak ayarlar.

- BST_INDETERMINATE, düğme durumunu, belirsiz bir durum belirterek gri olarak ayarlar. Bu değeri yalnızca düğmede BS_3STATE veya BS_AUTO3STATE stili varsa kullanın.

- BST_UNCHECKED, düğme durumunu işaretsiz olarak ayarlar.

##  <a name="checkradiobutton"></a>Cotacontrolcontainer:: CheckRadioButton

Grupta belirtilen radyo düğmesini seçer ve gruptaki kalan düğmeleri temizler.

```
virtual void CheckRadioButton(
    int nIDFirstButton,
    int nIDLastButton,
    int nIDCheckButton);
```

### <a name="parameters"></a>Parametreler

*Nıdfirstbutton*<br/>
Gruptaki ilk radyo düğmesinin tanımlayıcısını belirtir.

*Nıdlastbutton*<br/>
Gruptaki son radyo düğmesinin tanımlayıcısını belirtir.

*Nıdcheckbutton*<br/>
Denetlenecek radyo düğmesinin tanımlayıcısını belirtir.

##  <a name="colecontrolcontainer"></a>Cotacontrolcontainer:: Copacontrolcontainer

Bir `COleControlContainer` nesnesi oluşturur.

```
explicit COleControlContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Denetim kapsayıcısının üst penceresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesne başarıyla oluşturulduktan sonra, çağrısı `AttachControlSite`olan bir özel denetim sitesi ekleyin.

##  <a name="createcontrol"></a>Cotacontrolcontainer:: CreateControl

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
Denetimi temsil eden pencere nesnesine yönelik bir işaretçi.

*in*<br/>
Denetimin benzersiz sınıf KIMLIĞI.

*lpszWindowName*<br/>
Denetimde gösterilecek metne yönelik bir işaretçi. Denetimin başlık veya metin özelliğinin değerini (varsa) ayarlar. NULL ise, denetimin açıklamalı alt yazı veya metin özelliği değiştirilmez.

*dwStyle*<br/>
Windows stilleri. Kullanılabilir stiller, **açıklamalar** bölümü altında listelenmiştir.

*Rect*<br/>
Denetimin boyutunu ve konumunu belirtir. Bir `CRect` nesne`RECT` ya da yapı olabilir.

*NID*<br/>
Denetimin alt pencere KIMLIĞINI belirtir.

*pPersist*<br/>
Denetimin kalıcı durumunu içeren `CFile` bir işaretçisi. Varsayılan değer NULL ' dir ve bu, denetimin kendisini kalıcı depolamadan geri yüklemeden önce başlatıldığını belirtir. NULL değilse, denetimin kalıcı verilerini içeren, bir akış veya `CFile`depolama biçiminde bir türetilmiş nesnenin işaretçisi olması gerekir. Bu veriler, istemcinin önceki bir etkinleştirmesine kaydedilmiş olabilir. Diğer verileri içerebilir, ancak `CreateControl`arama sırasında okuma-yazma işaretçisinin kalıcı verilerin ilk baytına ayarlanmış olması gerekir. `CFile`

*bStorage*<br/>
*PPersist* 'teki verilerin veya `IStorage` `IStream` veri olarak yorumlanıp yorumlanmayacağını gösterir. *PPersist* 'teki veriler bir depolama Ise, *bStorage* doğru olmalıdır. *PPersist* 'teki veriler bir Stream Ise *bStorage* yanlış olmalıdır. Varsayılan değer FALSE 'dur.

*bstrLicKey*<br/>
İsteğe bağlı lisans anahtarı verileri. Bu veriler yalnızca bir çalışma zamanı lisans anahtarı gerektiren denetimler oluşturmak için gereklidir. Denetim lisanslamayı destekliyorsa, denetimin başarılı olması için bir lisans anahtarı sağlamanız gerekir. Varsayılan değer NULL.

*ppNewSite*<br/>
Oluşturulmakta olan denetimi barındıracak var olan denetim sitesine yönelik bir işaretçi. Varsayılan değer, yeni bir denetim sitesinin otomatik olarak oluşturulup yeni denetime iliştirilmeyeceğini belirten NULL değeridir.

*PPT*<br/>
Denetimin sol üst köşesini `POINT` içeren bir yapıya yönelik işaretçi. Denetimin boyutu *psize*değerine göre belirlenir. *PPT* ve *pboyut* değerleri, denetimin boyutunu ve konumunu belirtmek için isteğe bağlı bir yöntemdir.

*psıze*<br/>
Denetimin boyutunu içeren bir `SIZE` yapıya yönelik işaretçi. Sol üst köşe, *PPT*'nin değerine göre belirlenir. *PPT* ve *pboyut* değerleri, denetimin boyutunu ve konumunu belirtmek için isteğe bağlı bir yöntemdir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca Windows *dwStyle* bayraklarının bir alt kümesi tarafından `CreateControl`desteklenir:

- WS_VISIBLE Başlangıçta görünür olan bir pencere oluşturur. Denetimin normal pencereler gibi hemen görünür olmasını istiyorsanız gereklidir.

- WS_DISABLED başlangıçta devre dışı bırakılmış bir pencere oluşturur. Devre dışı bırakılan bir pencere kullanıcıdan giriş alamaz. Denetimin etkin bir özelliği varsa, ayarlanabilir.

- WS_BORDER ince çizgili kenarlığı olan bir pencere oluşturur. Denetimin bir BorderStyle özelliği varsa, ayarlanabilir.

- WS_GROUP bir denetim grubunun ilk denetimini belirtir. Kullanıcı, yön tuşlarını kullanarak, klavye odağını gruptaki bir denetimden bir sonrakine değiştirebilir. İlk denetimden sonra WS_GROUP stiliyle tanımlanan tüm denetimler aynı gruba aittir. WS_GROUP stilinde bir sonraki denetim, grubu sonlandırır ve sonraki grubu başlatır.

- WS_TABSTOP, Kullanıcı TAB tuşuna bastığında klavye odağını alabilen bir denetim belirtir. Sekme tuşuna basıldığında klavye odağı WS_TABSTOP stilinin bir sonraki denetimine değişir.

Varsayılan boyutlu denetimleri oluşturmak için ikinci aşırı yüklemeyi kullanın.

##  <a name="createolefont"></a>Cotacontrolcontainer:: Createolefazı tipi

OLE yazı tipi oluşturur.

```
void CreateOleFont(CFont* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
Denetim kapsayıcısı tarafından kullanılacak yazı tipine yönelik bir işaretçi.

##  <a name="finditem"></a>Cotacontrolcontainer:: FindItem

Belirtilen öğeyi barındıran özel siteyi bulur.

```
virtual COleControlSite* FindItem(UINT nID) const;
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Bulunan öğenin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğenin özel sitesine yönelik bir işaretçi.

##  <a name="freezeallevents"></a>Cotacontrolcontainer:: FreezeAllEvents

Kapsayıcının ekli denetim sitelerinden olayları yoksayıp sayamayacağını belirler veya kabul eder.

```
void FreezeAllEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Parametreler

*bFreeze*<br/>
Olaylar işlenecektir sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Denetim kapsayıcısı tarafından isteniyorsa olayları tetikleyerek denetim için gerekli değildir. Çalışmaya devam edebilir, ancak sonraki tüm olaylar Denetim kapsayıcısı tarafından yok sayılır.

##  <a name="getambientprop"></a>Cotacontrolcontainer:: Getambentprop

Belirtilen ortam özelliğinin değerini alır.

```
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,
    DISPID dispid,
    VARIANT* pvarResult);
```

### <a name="parameters"></a>Parametreler

*Psıte*<br/>
Ortam özelliğinin alınacağı bir denetim sitesine yönelik bir işaretçi.

*dı*<br/>
İstenen çevresel özelliğin dağıtım KIMLIĞI.

*pVarResult*<br/>
Çevresel özelliğin değerine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

##  <a name="getdlgitem"></a>Cotacontrolcontainer:: Getııbu öğe

Bir iletişim kutusu veya başka bir pencerede, belirtilen denetime veya alt pencereye bir işaretçi alır.

```
virtual CWnd* GetDlgItem(int nID) const;

virtual void GetDlgItem(
    int nID,
    HWND* phWnd) const;
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Alınacak iletişim kutusu öğesinin tanımlayıcısı.

*phWnd*<br/>
Belirtilen iletişim kutusu öğesinin pencere nesnesinin tanıtıcısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu öğesinin penceresine yönelik bir işaretçi.

##  <a name="getdlgitemint"></a>Cotacontrolcontainer:: Getdlitemint

Verilen denetimin çevrilmiş metninin değerini alır.

```
virtual UINT GetDlgItemInt(
    int nID,
    BOOL* lpTrans,
    BOOL bSigned) const;
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Denetimin tanımlayıcısı.

*lpTrans*<br/>
Bir işlev başarı/başarısızlık değeri alan bir Boolean değişkeni işaretçisi (doğru başarıyı gösterir, yanlış hatayı gösterir).

*bSigned*<br/>
İşlevin başındaki eksi işaretine ait metni incelemeli ve bir tane bulursa işaretli bir tamsayı değeri döndürmeyeceğini belirtir. *BSigned* parametresi true ise, alınacak değerin işaretli bir tamsayı değeri olduğunu belirtmek için, dönüş değerini bir **int** türüne atayın. Genişletilmiş hata bilgilerini almak için [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)çağrısı yapın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *lpTrans* tarafından işaret EDILEN değişken true olarak ayarlanır ve dönüş değeri denetim metninin çevrilmiş değeridir.

İşlev başarısız olursa, *lpTrans* tarafından işaret EDILEN değişken false olarak ayarlanır ve dönüş değeri sıfırdır. Sıfır olası çevrilmiş bir değer olduğundan sıfır değerinin dönüş değeri, hata olduğunu gösterir.

*LpTrans* null ise, işlev başarı veya başarısızlık hakkında hiçbir bilgi döndürmez.

### <a name="remarks"></a>Açıklamalar

İşlevi, metnin başlangıcında ek boşluklar gerçekleştirerek ve sonra ondalık basamakları dönüştürerek alınan metni çevirir. İşlev, metnin sonuna ulaştığında veya bir sayısal karakter ile karşılaştığında çevirmeyi durduruyor.

Bu işlev, çevrilen değer INT_MAX (işaretli sayılar için) veya UINT_MAX (işaretsiz sayılar için) değerinden büyükse sıfır değerini döndürür.

##  <a name="getdlgitemtext"></a>Coincontrolcontainer:: Getdlıtemtext

Verilen denetimin metnini alır.

```
virtual int GetDlgItemText(
    int nID,
    LPTSTR lpStr,
    int nMaxCount) const;
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Denetimin tanımlayıcısı.

*lpStr*<br/>
Denetimin metin işaretçisi.

*nMaxCount*<br/>
*LPSTR*tarafından işaret edilen arabelleğe kopyalanacak dizenin karakter cinsinden uzunluk üst sınırını belirtir. Dizenin uzunluğu sınırı aşarsa, dize kesilir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri, Sonlandırıcı null karakteri dahil değil, arabelleğe kopyalanmış karakter sayısını belirtir.

İşlev başarısız olursa, dönüş değeri sıfırdır. Genişletilmiş hata bilgilerini almak için [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)çağrısı yapın.

##  <a name="handlesetfocus"></a>Cotacontrolcontainer:: HandleSetFocus

Kapsayıcının WM_SETFOCUS iletilerini işlediğini belirler.

```
virtual BOOL HandleSetFocus();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcı WM_SETFOCUS iletilerini işlediğinde sıfır dışı; Aksi halde sıfır.

##  <a name="handlewindowlessmessage"></a>Cotacontrolcontainer:: HandleWindowlessMessage

Penceresiz denetimler için pencere iletilerini işler.

```
virtual BOOL HandleWindowlessMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```

### <a name="parameters"></a>Parametreler

*message*<br/>
Windows tarafından sunulan pencere iletisi için tanımlayıcı.

*wParam*<br/>
İletinin parametresi; Windows tarafından sağlanmaktadır. İletiye özgü ek bilgileri belirtir. Bu parametrenin içeriği, *ileti* parametresinin değerine bağlıdır.

*lParam*<br/>
İletinin parametresi; Windows tarafından sağlanmaktadır. İletiye özgü ek bilgileri belirtir. Bu parametrenin içeriği, *ileti* parametresinin değerine bağlıdır.

*plResult*<br/>
Windows sonuç kodu. İleti işleme sonucunu belirtir ve gönderilen iletiye göre değişir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Penceresiz Denetim iletilerinin işlenmesini özelleştirmek için bu işlevi geçersiz kılın.

##  <a name="isdlgbuttonchecked"></a>Copacontrolcontainer:: ısıbir Buttonchecked

Belirtilen düğmenin durumunu belirler.

```
virtual UINT IsDlgButtonChecked(int nIDButton) const;
```

### <a name="parameters"></a>Parametreler

*Nıdbutton*<br/>
Düğme denetiminin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON veya BS_3STATE stiliyle oluşturulan bir düğmeden döndürülen değer. Aşağıdakilerden biri olabilir:

- BST_CHECKED düğmesi işaretlendi.

- BST_INDETERMINATE düğmesi gri, belirsiz bir durum olduğunu belirtir (yalnızca düğme BS_3STATE veya BS_AUTO3STATE stiline sahipse geçerlidir).

- BST_UNCHECKED düğmesi temizlendi.

### <a name="remarks"></a>Açıklamalar

Düğme üç durumlu bir denetimdir, üye işlevi soluk, işaretli veya hiçbirini belirler.

##  <a name="m_crback"></a>Cotacontrolcontainer:: m_crBack

Kapsayıcının arka plan rengi.

```
COLORREF m_crBack;
```

##  <a name="m_crfore"></a>Cotacontrolcontainer:: m_crFore

Kapsayıcının ön plan rengi.

```
COLORREF m_crFore;
```

##  <a name="m_listsitesorwnds"></a>Cotacontrolcontainer:: m_listSitesOrWnds

Kapsayıcı tarafından barındırılan denetim sitelerinin listesi.

```
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;
```

##  <a name="m_nwindowlesscontrols"></a>Cotacontrolcontainer:: m_nWindowlessControls

Denetim kapsayıcısı tarafından barındırılan penceresiz denetimlerin sayısı.

```
int m_nWindowlessControls;
```

##  <a name="m_polefont"></a>Cotacontrolcontainer:: m_pOleFont

Özel denetim sitesinin OLE yazı tipine yönelik bir işaretçi.

```
LPFONTDISP m_pOleFont;
```

##  <a name="m_psitecapture"></a>Cotacontrolcontainer:: m_pSiteCapture

Yakalama denetimi sitesinin işaretçisi.

```
COleControlSite* m_pSiteCapture;
```

##  <a name="m_psitefocus"></a>Cotacontrolcontainer:: m_pSiteFocus

Şu anda giriş odağına sahip olan denetim sitesine yönelik bir işaretçi.

```
COleControlSite* m_pSiteFocus;
```

##  <a name="m_psiteuiactive"></a>Cotacontrolcontainer:: m_pSiteUIActive

Yerinde etkinleştirilen denetim sitesine yönelik bir işaretçi.

```
COleControlSite* m_pSiteUIActive;
```

##  <a name="m_pwnd"></a>Cotacontrolcontainer:: m_pWnd

Kapsayıcı ile ilişkili pencere nesnesine yönelik bir işaretçi.

```
CWnd* m_pWnd;
```

##  <a name="m_sitemap"></a>Cotacontrolcontainer:: m_siteMap

Site haritası.

```
CMapPtrToPtr m_siteMap;
```

##  <a name="onpaint"></a>Cotacontrolcontainer:: OnPaint

WM_PAINT isteklerini işlemek için Framework tarafından çağırılır.

```
virtual BOOL OnPaint(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Kapsayıcı tarafından kullanılan cihaz bağlamına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Boyama işlemini özelleştirmek için bu işlevi geçersiz kılın.

##  <a name="onuiactivate"></a>Cotacontrolcontainer:: OnUIActivate

*PSite*tarafından işaret edilen Denetim sitesi, yerinde etkinleştirilmekte olduğu için Framework tarafından çağırılır.

```
virtual void OnUIActivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Parametreler

*Psıte*<br/>
Denetim sitesinin yerinde etkinleştirilmesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Yerinde etkinleştirme, kapsayıcının ana menüsünün yerine yerinde bileşik bir menü olduğu anlamına gelir.

##  <a name="onuideactivate"></a>Cotacontrolcontainer:: OnUIDeactivate

*PSite*tarafından işaret edilen Denetim sitesi devre dışı bırakmak üzereyken Framework tarafından çağırılır.

```
virtual void OnUIDeactivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Parametreler

*Psıte*<br/>
Devre dışı bırakmak üzere denetim sitesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu bildirim alındığında, kapsayıcı kullanıcı arabirimini yeniden yüklemeli ve odağı almalıdır.

##  <a name="scrollchildren"></a>Cotacontrolcontainer:: ScrollChildren

Bir alt pencereden kaydırma iletileri alındığında Framework tarafından çağırılır.

```
virtual void ScrollChildren(
    int dx,
    int dy);
```

### <a name="parameters"></a>Parametreler

*DX*<br/>
X ekseni üzerinde kaydırmanın piksel cinsinden miktarı.

*rengi*<br/>
Y ekseni üzerinde kaydırmanın piksel cinsinden miktarı.

##  <a name="senddlgitemmessage"></a>Cotacontrolcontainer:: SendDlgItemMessage

Belirtilen denetime bir ileti gönderir.

```
virtual LRESULT SendDlgItemMessage(
    int nID,
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
İletiyi alan denetimin tanımlayıcısını belirtir.

*message*<br/>
Gönderilecek iletiyi belirtir.

*wParam*<br/>
İletiye özgü ek bilgileri belirtir.

*lParam*<br/>
İletiye özgü ek bilgileri belirtir.

##  <a name="setdlgitemint"></a>Cotacontrolcontainer:: Setdlitemint

İletişim kutusundaki bir denetimin metnini belirtilen tamsayı değerinin dize gösterimine ayarlar.

```
virtual void SetDlgItemInt(
    int nID,
    UINT nValue,
    BOOL bSigned);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Denetimin tanımlayıcısı.

*nDeğer*<br/>
Görüntülenecek tamsayı değeri.

*bSigned*<br/>
*NValue* parametresinin imzalanmış veya imzasız olduğunu belirtir. Bu parametre TRUE ise, *nValue* imzalanmamıştır. Bu parametre TRUE ise ve *nValue* sıfırdan küçükse, dizedeki ilk basamakla önce bir eksi işareti yerleştirilir. Bu parametre FALSE ise, *nValue değeri* işaretsiz olur.

##  <a name="setdlgitemtext"></a>Cotacontrolcontainer:: Setdlıtemtext

*LpszString*içinde bulunan metni kullanarak belirtilen denetimin metnini ayarlar.

```
virtual void SetDlgItemText(
    int nID,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Denetimin tanımlayıcısı.

*lpszString*<br/>
Denetimin metin işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite Sınıfı](../../mfc/reference/colecontrolsite-class.md)<br/>
[COccManager Sınıfı](../../mfc/reference/coccmanager-class.md)
