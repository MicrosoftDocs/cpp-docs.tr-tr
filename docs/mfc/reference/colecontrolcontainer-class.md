---
title: "COleControlContainer sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6d04faa904eba416b290515e5e6773ac6ef9837
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="colecontrolcontainer-class"></a>COleControlContainer sınıfı
ActiveX denetimleri için bir denetim kapsayıcısı olarak görev yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleControlContainer : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleControlContainer::COleControlContainer](#colecontrolcontainer)|Oluşturan bir `COleControlContainer` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleControlContainer::AttachControlSite](#attachcontrolsite)|Kapsayıcı tarafından barındırılan bir denetim site oluşturur.|  
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|Bir ortam özelliği değişti tüm barındırılan denetimlerin bildirir.|  
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|Belirtilen düğme denetimi değiştirir.|  
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|Bir grubun belirtilen radyo düğmesini seçer.|  
|[COleControlContainer::CreateControl](#createcontrol)|Barındırılan bir ActiveX denetimi oluşturur.|  
|[COleControlContainer::CreateOleFont](#createolefont)|OLE yazı tipi oluşturur.|  
|[COleControlContainer::FindItem](#finditem)|Özel site belirtilen denetiminin döndürür.|  
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|Denetim site olayları kabul ediyor belirler.|  
|[COleControlContainer::GetAmbientProp](#getambientprop)|Belirtilen ortam özelliği alır.|  
|[COleControlContainer::GetDlgItem](#getdlgitem)|Belirtilen iletişim denetimi alır.|  
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|Belirtilen iletişim denetimi değerini alır.|  
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|Belirtilen iletişim denetimi resim yazısını alır.|  
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|Kapsayıcı işler varsa belirler `WM_SETFOCUS` iletileri.|  
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|Penceresiz denetime gönderilen iletileri işler.|  
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|Belirtilen düğme durumunu belirler.|  
|[COleControlContainer::OnPaint](#onpaint)|Kapsayıcı bir kısmı çizilecek çağrılır.|  
|[COleControlContainer::OnUIActivate](#onuiactivate)|Bir denetim hakkında yerinde etkin olması için olduğunda çağrılır.|  
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|Bir denetim hakkında devre dışı olduğunda çağrılır.|  
|[COleControlContainer::ScrollChildren](#scrollchildren)|Bir alt penceresinden kaydırma iletileri alındığında çerçevesi tarafından çağrılır.|  
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|Belirtilen denetime bir ileti gönderir.|  
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|Belirtilen denetim değerini ayarlar.|  
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|Metnin belirtilen denetiminin ayarlar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleControlContainer::m_crBack](#m_crback)|Kapsayıcı arka plan rengi.|  
|[COleControlContainer::m_crFore](#m_crfore)|Kapsayıcı ön plan rengi.|  
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|Desteklenen denetim sitelerin listesi.|  
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|Barındırılan penceresiz denetimleri sayısı.|  
|[COleControlContainer::m_pOleFont](#m_polefont)|Özel denetim site OLE yazı tipi için bir işaretçi.|  
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|Yakalama denetim sitesi işaretçisi.|  
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|Şu anda odak giriş denetimine işaretçi.|  
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|Yerinde etkinleştirildi denetimi işaretçi.|  
|[COleControlContainer::m_pWnd](#m_pwnd)|Denetim kapsayıcı uygulama penceresi işaretçi.|  
|[COleControlContainer::m_siteMap](#m_sitemap)|Site haritası.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bir veya daha fazla ActiveX denetimi siteleri için destek sağlayarak gerçekleştirilir (tarafından uygulanan `COleControlSite`). `COleControlContainer`tam olarak uygulayan [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) ve [IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103) arabirimleri, kendi nitelikleri yerinde öğeleri olarak gerçekleştirmeyi kapsanan ActiveX denetimlerini izin verme.  
  
 Genellikle, bu sınıf ile birlikte kullanılan `COccManager` ve `COleControlSite` bir veya daha fazla ActiveX denetimleri için özel sitelerle özel bir ActiveX denetimi kapsayıcısı uygulamak için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlContainer`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxocc.h  
  
##  <a name="attachcontrolsite"></a>COleControlContainer::AttachControlSite  
 Oluşturmak ve bir denetim sitesi eklemek için çerçevesi tarafından çağrılır.  
  
```  
virtual void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);

 
void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Bir işaretçi bir `CWnd` nesnesi.  
  
 `nIDC`  
 Eklenecek denetim kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlemi özelleştirmek istiyorsanız, bu işlev geçersiz kılar.  
  
> [!NOTE]
>  MFC Kitaplığı'na statik olarak bağlıyorsanız, bu işlevin ilk formu kullanın. MFC Kitaplığı'na dinamik olarak bağlıyorsanız ikinci formu kullanın.  
  
##  <a name="broadcastambientpropertychange"></a>COleControlContainer::BroadcastAmbientPropertyChange  
 Bir ortam özelliği değişti tüm barındırılan denetimlerin bildirir.  
  
```  
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="parameters"></a>Parametreler  
 `dispid`  
 Değiştirilmesini ortam özelliği gönderme kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bir ortam özelliği değeri değiştiğinde çerçevesi tarafından çağrılır. Bu işlev bu davranışını özelleştirmek için geçersiz kılar.  
  
##  <a name="checkdlgbutton"></a>COleControlContainer::CheckDlgButton  
 Düğmenin geçerli durumunu değiştirir.  
  
```  
virtual void CheckDlgButton(
    int nIDButton,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDButton`  
 Değiştirilecek düğmesi kimliği.  
  
 `nCheck`  
 Düğmenin durumunu belirtir. Aşağıdakilerden biri olabilir:  
  
- **BST_CHECKED** düğme durumu işaretli olarak ayarlar.  
  
- **BST_INDETERMINATE** düğme durumu, belirlenmemiş bir durum gösteren, gri olarak ayarlar. Yalnızca düğmesi varsa bu değeri kullanın **BS_3STATE** veya **BS_AUTO3STATE** stili.  
  
- **BST_UNCHECKED** düğme durumu temizlenmiş olarak ayarlar.  
  
##  <a name="checkradiobutton"></a>COleControlContainer::CheckRadioButton  
 Bir gruptaki belirtilen radyo düğmesini seçer ve gruptaki kalan düğmeleri temizler.  
  
```  
virtual void CheckRadioButton(
    int nIDFirstButton,  
    int nIDLastButton,  
    int nIDCheckButton);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDFirstButton`  
 Gruptaki ilk radyo düğmesi tanımlayıcısını belirtir.  
  
 `nIDLastButton`  
 Gruptaki son radyo düğmesi tanımlayıcısını belirtir.  
  
 `nIDCheckButton`  
 Denetlenecek radyo düğmesi tanımlayıcısını belirtir.  
  
##  <a name="colecontrolcontainer"></a>COleControlContainer::COleControlContainer  
 Oluşturan bir `COleControlContainer` nesnesi.  
  
```  
explicit COleControlContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Denetim kapsayıcı ana pencereyi gösteren bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne başarıyla oluşturulduktan sonra bir özel denetim sitesi çağrısıyla ekleme `AttachControlSite`.  
  
##  <a name="createcontrol"></a>COleControlContainer::CreateControl  
 Belirtilen tarafından barındırılan bir ActiveX denetimini oluşturur `COleControlSite` nesnesi.  
  
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
 `pWndCtrl`  
 Denetim temsil eden pencere nesnesi için bir işaretçi.  
  
 `clsid`  
 Denetimin benzersiz sınıf kimliği.  
  
 `lpszWindowName`  
 Denetimde görüntülenecek metni için bir işaretçi. Denetimin resim yazısını veya metin özelliğinin değeri (varsa) ayarlar. Varsa **NULL**, denetimin resim yazısını veya metin özelliğini değiştirilmedi.  
  
 `dwStyle`  
 Windows stilleri. Kullanılabilir stiller altında listelenen **açıklamalar** bölümü.  
  
 `rect`  
 Denetimin boyutunu ve konumunu belirtir. Ya da olabilir bir `CRect` nesnesi veya bir `RECT` yapısı.  
  
 `nID`  
 Denetimin alt pencere kimliğini belirtir.  
  
 `pPersist`  
 Bir işaretçi bir `CFile` denetimi kalıcı durumunu içeren. Varsayılan değer **NULL**, denetimi kendisini herhangi kalıcı depolama biriminden durumuna geri yüklemeden başlatır olduğunu gösteren. Aksi takdirde **NULL**, bir işaretçi olmalıdır bir `CFile`-türetilmiş bir akış veya bir depolama biçiminde denetimin kalıcı veri içeren nesne. Bu veriler istemcinin önceki bir etkinleştirme kaydedilmiş. `CFile` Diğer verileri içerebilir, ancak çağrısı zaman kalıcı verilerin ilk baytı ayarlamak okuma-yazma işaretçisini olmalıdır `CreateControl`.  
  
 `bStorage`  
 Gösterir olup olmadığını verileri `pPersist` olarak yorumlanıp `IStorage` veya `IStream` veri. Varsa verilerde `pPersist` bir depolama `bStorage` olmalıdır **doğru**. Varsa verilerde `pPersist` bir akışı `bStorage` olmalıdır **FALSE**. Varsayılan değer **FALSE**.  
  
 `bstrLicKey`  
 İsteğe bağlı lisans anahtar verileri. Bu veriler, yalnızca bir çalışma zamanı lisans anahtarı gerekli denetimleri oluşturmak için gereklidir. Denetim lisans destekliyorsa, başarılı olması için denetimi oluşturulması için bir lisans anahtarı sağlamanız gerekir. Varsayılan değer **NULL**.  
  
 *ppNewSite*  
 Oluşturulan denetim barındıracak olan denetim site için bir işaretçi. Varsayılan değer **NULL**, yeni bir denetim sitesi otomatik olarak oluşturulur ve yeni denetime bağlı olduğunu gösteren.  
  
 `ppt`  
 Bir işaretçi bir **noktası** denetimin sol üst köşesinde içeren yapısı. Denetimin boyutunu değeri tarafından belirlenir *psize*. `ppt` Ve *psize* değerlerdir boyutunu ve konumunu denetiminin belirten isteğe bağlı bir yöntem.  
  
 *psize*  
 Bir işaretçi bir **BOYUTU** denetimin boyutunu içeren yapısı. Sol üst köşesindeki değeri tarafından belirlenir `ppt`. `ppt` Ve *psize* değerlerdir boyutunu ve konumunu denetiminin belirten isteğe bağlı bir yöntem.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca bir alt kümesini Windows `dwStyle` bayrakları tarafından desteklenen `CreateControl`:  
  
- **Ws_vısıble** başlangıçta görünür bir pencere oluşturur. Denetim hemen, normal windows gibi görünür olmasını istiyorsanız gereklidir.  
  
- **Ws_dısabled** başlangıçta devre dışı bir pencere oluşturur. Devre dışı bırakılan penceresinde kullanıcıdan giriş alamaz. Denetim etkin özelliğine sahipse ayarlanabilir.  
  
- `WS_BORDER`Bir pencere ince çizgi kenarlık ile oluşturur. Denetim kenarlık stili özelliğine sahipse ayarlanabilir.  
  
- **WS_GROUP** denetimleri grubunun ilk denetim belirtir. Kullanıcı klavye odağını grubundaki bir denetimden sonraki yön tuşlarını kullanarak değiştirebilirsiniz. İle tanımlanmış tüm denetimler **WS_GROUP** ilk denetim ait sonra aynı gruba stili. Sonraki denetimiyle **WS_GROUP** Stil grubu sona erer ve sonraki grubu başlatır.  
  
- **WS_TABSTOP** kullanıcı SEKME tuşuna bastığında klavye odağı alabilecek bir denetim belirtir. Sonraki denetimin değişiklikleri klavye odağını SEKME tuşuna basarak **WS_TABSTOP** stili.  
  
 İkinci varsayılan boyutlu denetimleri oluşturmak için kullanın.  
  
##  <a name="createolefont"></a>COleControlContainer::CreateOleFont  
 OLE yazı tipi oluşturur.  
  
```  
void CreateOleFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFont`  
 Denetim kapsayıcı tarafından kullanılacak yazı tipi için bir işaretçi.  
  
##  <a name="finditem"></a>COleControlContainer::FindItem  
 Belirtilen öğe barındıran özel site bulur.  
  
```  
virtual COleControlSite* FindItem(UINT nID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Bulunacak öğe tanımlayıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen öğenin özel site için bir işaretçi.  
  
##  <a name="freezeallevents"></a>COleControlContainer::FreezeAllEvents  
 Kapsayıcı veya ekli denetim sitelerinden olaylarını yoksayar bunları kabul belirler.  
  
```  
void FreezeAllEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Parametreler  
 `bFreeze`  
 Olayları işlediğinde sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Denetim olayları denetim kapsayıcı tarafından isteniyorsa tetikleme durdurmak için gerekli değildir. Tetikleme devam edebilirsiniz ancak tüm sonraki olaylarda denetim kapsayıcı tarafından göz ardı edilir.  
  
##  <a name="getambientprop"></a>COleControlContainer::GetAmbientProp  
 Belirtilen bir ortam özelliği değerini alır.  
  
```  
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,  
    DISPID dispid,  
    VARIANT* pvarResult);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSite`  
 Bir işaretçi bir denetim siteye ortam özelliği alınır.  
  
 `dispid`  
 İstenen ortam özelliği gönderme kimliği.  
  
 *pVarResult*  
 Ortam özelliği değerini gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="getdlgitem"></a>COleControlContainer::GetDlgItem  
 Bir iletişim kutusu belirtilen denetim veya alt penceresinde veya başka bir pencere için bir işaretçi alır.  
  
```  
virtual CWnd* GetDlgItem(int nID) const;  
  
virtual void GetDlgItem(
    int nID,  
    HWND* phWnd) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Almak için iletişim öğesinin tanıtıcısı.  
  
 `phWnd`  
 Belirtilen iletişim öğesi'nin pencere nesnesi işlemek için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusu öğesi'nin penceresi için bir işaretçi.  
  
##  <a name="getdlgitemint"></a>COleControlContainer::GetDlgItemInt  
 Belirli bir denetim çevrilmiş metnin değerini alır.  
  
```  
virtual UINT GetDlgItemInt(
    int nID,  
    BOOL* lpTrans,  
    BOOL bSigned) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Denetim tanımlayıcısı.  
  
 `lpTrans`  
 İşlevi başarı/hata değerini alan bir Boolean değişkeni işaretçisine ( **TRUE** başarıyı gösterir **FALSE** başarısız olduğunu gösterir).  
  
 `bSigned`  
 İşlev ve başında eksi işareti metnini inceleyin bulursa imzalı tamsayı değer döndürme belirtir. Varsa `bSigned` parametresi **TRUE**, cast dönüş değeri alınacak değerin imzalı tamsayı değer olduğunu belirten bir `int` türü. Genişletilmiş hata bilgilerini için arama [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, değişkeni gösterdiği varsa `lpTrans` ayarlanır **doğru**, ve dönüş değeri kontrol metni çevrilmiş değeri.  
  
 İşlev başarısız olursa, değişkenin işaret için tarafından `lpTrans` ayarlanır **yanlış**, ve dönüş değeri sıfır. Sıfır olası çevrilmiş değer olduğundan, sıfır dönüş değeri tek başına hatası olduğu anlamına gelmez, unutmayın.  
  
 Varsa `lpTrans` olan **NULL**, başarı veya başarısızlık hakkında hiçbir bilgi işlevi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev, metnin başındaki ek boşluk çıkarma ve ondalık basamak dönüştürme alınan metin çevirir. Metnin sonuna ulaştığında veya bir sayısal karakter karşılaştığında, çevirme işlevini durdurur.  
  
 Çevrilen değeri büyük ise bu işlev, sıfır döndürür. **INT_MAX** (için imzalanmış sayılar) veya **uınt_max** (için imzasız numaraları).  
  
##  <a name="getdlgitemtext"></a>COleControlContainer::GetDlgItemText  
 Belirli bir denetim metni alır.  
  
```  
virtual int GetDlgItemText(
    int nID,  
    LPTSTR lpStr,  
    int nMaxCount) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Denetim tanımlayıcısı.  
  
 `lpStr`  
 Denetim metin işaretçisi.  
  
 `nMaxCount`  
 Gösterdiği arabellek kopyalanacak dizenin karakter cinsinden uzunluk üst sınırını belirtir `lpStr`. Dize, dize uzunluğu sınırı aşarsa kesilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri arabelleğe sonlandırma null karakteri dahil değil, kopyalanan karakter sayısını belirtir.  
  
 İşlev başarısız olursa, dönüş değeri sıfır olur. Genişletilmiş hata bilgilerini için arama [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
##  <a name="handlesetfocus"></a>COleControlContainer::HandleSetFocus  
 Kapsayıcı işler varsa belirler `WM_SETFOCUS` iletileri.  
  
```  
virtual BOOL HandleSetFocus();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsayıcı işliyorsa sıfır olmayan `WM_SETFOCUS` iletiler; Aksi takdirde sıfır.  
  
##  <a name="handlewindowlessmessage"></a>COleControlContainer::HandleWindowlessMessage  
 Pencere iletileri penceresiz denetimleri için işler.  
  
```  
virtual BOOL HandleWindowlessMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* plResult);
```  
  
### <a name="parameters"></a>Parametreler  
 `message`  
 Windows tarafından sağlanan pencere İleti tanımlayıcısı.  
  
 `wParam`  
 İleti parametresinin; Windows tarafından sağlanan. Ek ileti özgü bilgileri belirtir. Bu parametre içeriğini değerine göre bağımlı `message` parametresi.  
  
 `lParam`  
 İleti parametresinin; Windows tarafından sağlanan. Ek ileti özgü bilgileri belirtir. Bu parametre içeriğini değerine göre bağımlı `message` parametresi.  
  
 *plResult*  
 Windows Sonuç kodu. İleti işleme sonucunu belirtir ve gönderilen ileti bağlıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev penceresiz denetim iletileri işleme özelleştirmek için geçersiz kılar.  
  
##  <a name="isdlgbuttonchecked"></a>COleControlContainer::IsDlgButtonChecked  
 Belirtilen düğme durumunu belirler.  
  
```  
virtual UINT IsDlgButtonChecked(int nIDButton) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDButton`  
 Düğme denetimi tanımlayıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri ile oluşturulan bir düğmesinden **BS_AUTOCHECKBOX**, **bs_autoradıobutton**, **BS_AUTO3STATE**, **BS_CHECKBOX**, **Bs_radıobutton**, veya **BS_3STATE** stili. Aşağıdakilerden biri olabilir:  
  
- **BST_CHECKED** düğmesi denetlenir.  
  
- **BST_INDETERMINATE** düğmesi gri, belirlenmemiş bir durum gösteren (yalnızca düğmesi varsa geçerlidir **BS_3STATE** veya **BS_AUTO3STATE** stili).  
  
- **BST_UNCHECKED** düğmesi temizlenir.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme üç durumlu denetim, üye fonksiyonu onu, işaretli soluk olup olmadığını belirler. veya hiçbiri.  
  
##  <a name="m_crback"></a>COleControlContainer::m_crBack  
 Kapsayıcı arka plan rengi.  
  
```  
COLORREF m_crBack;  
```  
  
##  <a name="m_crfore"></a>COleControlContainer::m_crFore  
 Kapsayıcı ön plan rengi.  
  
```  
COLORREF m_crFore;  
```  
  
##  <a name="m_listsitesorwnds"></a>COleControlContainer::m_listSitesOrWnds  
 Kapsayıcı tarafından barındırılan denetim sitelerin listesi.  
  
```  
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;  
```  
  
##  <a name="m_nwindowlesscontrols"></a>COleControlContainer::m_nWindowlessControls  
 Denetim kapsayıcı tarafından barındırılan penceresiz denetimleri sayısı.  
  
```  
int m_nWindowlessControls;  
```  
  
##  <a name="m_polefont"></a>COleControlContainer::m_pOleFont  
 Özel denetim site OLE yazı tipi için bir işaretçi.  
  
```  
LPFONTDISP m_pOleFont;  
```  
  
##  <a name="m_psitecapture"></a>COleControlContainer::m_pSiteCapture  
 Yakalama denetim sitesi işaretçisi.  
  
```  
COleControlSite* m_pSiteCapture;  
```  
  
##  <a name="m_psitefocus"></a>COleControlContainer::m_pSiteFocus  
 Şu anda denetim site için bir işaretçi odak giriş.  
  
```  
COleControlSite* m_pSiteFocus;  
```  
  
##  <a name="m_psiteuiactive"></a>COleControlContainer::m_pSiteUIActive  
 Yerinde etkin denetim alanı için bir işaretçi.  
  
```  
COleControlSite* m_pSiteUIActive;  
```  
  
##  <a name="m_pwnd"></a>COleControlContainer::m_pWnd  
 Kapsayıcı ile ilişkili pencere nesnesi için bir işaretçi.  
  
```  
CWnd* m_pWnd;  
```  
  
##  <a name="m_sitemap"></a>COleControlContainer::m_siteMap  
 Site haritası.  
  
```  
CMapPtrToPtr m_siteMap;  
```  
  
##  <a name="onpaint"></a>COleControlContainer::OnPaint  
 İşlenecek çerçevesi tarafından çağrılır `WM_PAINT` istekleri.  
  
```  
virtual BOOL OnPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Kapsayıcı tarafından kullanılan cihaz bağlamı için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti işleniyorsa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev boyama işlemi özelleştirmek için geçersiz kılar.  
  
##  <a name="onuiactivate"></a>COleControlContainer::OnUIActivate  
 Çerçevesi tarafından çağrılır zaman denetim site işaret için tarafından `pSite`, yaklaşık olacak yerinde etkinleştirildi.  
  
```  
virtual void OnUIActivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSite`  
 Yerinde etkinleştirilmiş denetim sitenin hakkında bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerinde etkinleştirme kapsayıcının ana menü yerinde bileşik menüsüyle değiştirilir anlamına gelir.  
  
##  <a name="onuideactivate"></a>COleControlContainer::OnUIDeactivate  
 Çerçevesi tarafından çağrılır zaman denetim site işaret için tarafından `pSite`, yaklaşık devre dışı değil.  
  
```  
virtual void OnUIDeactivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSite`  
 Bir işaretçi denetim sitesine hakkında devre dışı bırakılmış olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bildirim alındığında, kapsayıcı kullanıcı arabirimi yeniden yükleyin ve odağı alması gerekir.  
  
##  <a name="scrollchildren"></a>COleControlContainer::ScrollChildren  
 Bir alt penceresinden kaydırma iletileri alındığında çerçevesi tarafından çağrılır.  
  
```  
virtual void ScrollChildren(
    int dx,  
    int dy);
```  
  
### <a name="parameters"></a>Parametreler  
 `dx`  
 X ekseni boyunca kaydırma miktarını, piksel cinsinden.  
  
 *GN*  
 Y ekseni boyunca kaydırma miktarını, piksel cinsinden.  
  
##  <a name="senddlgitemmessage"></a>COleControlContainer::SendDlgItemMessage  
 Belirtilen denetime bir ileti gönderir.  
  
```  
virtual LRESULT SendDlgItemMessage(
    int nID,  
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 İletiyi alır denetim tanımlayıcısını belirtir.  
  
 `message`  
 Gönderilecek iletiyi belirtir.  
  
 `wParam`  
 Ek ileti özgü bilgileri belirtir.  
  
 `lParam`  
 Ek ileti özgü bilgileri belirtir.  
  
##  <a name="setdlgitemint"></a>COleControlContainer::SetDlgItemInt  
 Belirtilen bir tamsayı dize gösterimini bir iletişim kutusunda bir denetimi metin ayarlar.  
  
```  
virtual void SetDlgItemInt(
    int nID,  
    UINT nValue,  
    BOOL bSigned);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Denetim tanımlayıcısı.  
  
 `nValue`  
 Görüntülenecek tamsayı değeri.  
  
 `bSigned`  
 Belirtir olup olmadığını `nValue` parametresi imzalanmış veya imzalanmamış. Bu parametre ise **TRUE**, `nValue` imzalanır. Bu parametre ise **TRUE** ve `nValue` sıfırdan küçük, eksi işareti dizedeki ilk rakam önce yerleştirilir. Bu parametre ise **FALSE**, `nValue` imzasız.  
  
##  <a name="setdlgitemtext"></a>COleControlContainer::SetDlgItemText  
 Metnin bulunan metin kullanarak belirtilen denetimi ayarlar `lpszString`.  
  
```  
virtual void SetDlgItemText(
    int nID,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Denetim tanımlayıcısı.  
  
 `lpszString`  
 Denetim metin işaretçisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleControlSite sınıfı](../../mfc/reference/colecontrolsite-class.md)   
 [COccManager Sınıfı](../../mfc/reference/coccmanager-class.md)
