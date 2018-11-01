---
title: CBaseTabbedPane sınıfı
ms.date: 11/04/2016
f1_keywords:
- CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::AddTab
- AFXBASETABBEDPANE/CBaseTabbedPane::AllowDestroyEmptyTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::ApplyRestoredTabInfo
- AFXBASETABBEDPANE/CBaseTabbedPane::CanFloat
- AFXBASETABBEDPANE/CBaseTabbedPane::CanSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::ConvertToTabbedDocument
- AFXBASETABBEDPANE/CBaseTabbedPane::DetachPane
- AFXBASETABBEDPANE/CBaseTabbedPane::EnableSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::FillDefaultTabsOrderArray
- AFXBASETABBEDPANE/CBaseTabbedPane::FindBarByTabNumber
- AFXBASETABBEDPANE/CBaseTabbedPane::FindPaneByID
- AFXBASETABBEDPANE/CBaseTabbedPane::FloatTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetDefaultTabsOrder
- AFXBASETABBEDPANE/CBaseTabbedPane::GetFirstVisibleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetMinSize
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneIcon
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneList
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabArea
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::GetUnderlyingWindow
- AFXBASETABBEDPANE/CBaseTabbedPane::GetVisibleTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::HasAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::IsHideSingleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::RecalcLayout
- AFXBASETABBEDPANE/CBaseTabbedPane::RemovePane
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoDestroy
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::ShowTab
helpviewer_keywords:
- CBaseTabbedPane [MFC], AddTab
- CBaseTabbedPane [MFC], AllowDestroyEmptyTabbedPane
- CBaseTabbedPane [MFC], ApplyRestoredTabInfo
- CBaseTabbedPane [MFC], CanFloat
- CBaseTabbedPane [MFC], CanSetCaptionTextToTabName
- CBaseTabbedPane [MFC], ConvertToTabbedDocument
- CBaseTabbedPane [MFC], DetachPane
- CBaseTabbedPane [MFC], EnableSetCaptionTextToTabName
- CBaseTabbedPane [MFC], FillDefaultTabsOrderArray
- CBaseTabbedPane [MFC], FindBarByTabNumber
- CBaseTabbedPane [MFC], FindPaneByID
- CBaseTabbedPane [MFC], FloatTab
- CBaseTabbedPane [MFC], GetDefaultTabsOrder
- CBaseTabbedPane [MFC], GetFirstVisibleTab
- CBaseTabbedPane [MFC], GetMinSize
- CBaseTabbedPane [MFC], GetPaneIcon
- CBaseTabbedPane [MFC], GetPaneList
- CBaseTabbedPane [MFC], GetTabArea
- CBaseTabbedPane [MFC], GetTabsNum
- CBaseTabbedPane [MFC], GetUnderlyingWindow
- CBaseTabbedPane [MFC], GetVisibleTabsNum
- CBaseTabbedPane [MFC], HasAutoHideMode
- CBaseTabbedPane [MFC], IsHideSingleTab
- CBaseTabbedPane [MFC], RecalcLayout
- CBaseTabbedPane [MFC], RemovePane
- CBaseTabbedPane [MFC], SetAutoDestroy
- CBaseTabbedPane [MFC], SetAutoHideMode
- CBaseTabbedPane [MFC], ShowTab
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
ms.openlocfilehash: 51344a8cd0e5671f81e608b74363ed06c9200324
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640901"
---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane sınıfı

İşlevselliğini genişletir [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md) sekmeli pencerelerin oluşturulmasını desteklemek için.

## <a name="syntax"></a>Sözdizimi

```
class CBaseTabbedPane : public CDockablePane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CBaseTabbedPane::CBaseTabbedPane`|Varsayılan Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBaseTabbedPane::AddTab](#addtab)|Yeni bir sekme sekmeli bir bölmeye ekler.|
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Boş bir sekmeli bölme yok edilebilir olup olmadığını belirtir.|
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|Kayıt defterinden sekmeli bir bölmeye yüklenen Sekme ayarlarını uygular.|
|[CBaseTabbedPane::CanFloat](#canfloat)|Bölmesinde kaydırabilirsiniz olup olmadığını belirler. (Geçersiz kılmaları [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Sekmeli bölmesi için açıklama yazısını etkin sekme aynı metni görüntüleyip görüntülemeyeceğini belirler.|
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(Geçersiz kılmaları [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|
|[CBaseTabbedPane::DetachPane](#detachpane)|Bir veya daha fazla yerleştirilebilir bölmeleri MDI sekmeli belgeye dönüştürür.|
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|Etkinleştirir veya sekmeli bölme etkin sekmede etiket metni ile açıklamalı alt yazı metni eşitlemek yeteneği devre dışı bırakır.|
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|İç sekme sırası varsayılan durumuna geri yükler.|
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|Sekmesi sekmesini sıfır tabanlı dizine göre tanımlandığında bir sekmede bulunduğu bölme döndürür.|
|||
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|Bölmesinde kimliğine göre tanımlanan bir bölme döndürür|
|[CBaseTabbedPane::FloatTab](#floattab)|Bölmeyi şu anda çıkarılabilir bir sekmede yer alıyorsa ancak yalnızca bir bölme kaydırır.|
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|Varsayılan sekme sırasını bölmesinde döndürür.|
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|İlk görüntülenen sekme için bir işaretçi alır.|
|[CBaseTabbedPane::GetMinSize](#getminsize)|Bölme boyutu izin verilen en düşük alır. (Geçersiz kılmaları [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|Bölmesi simge için bir tanıtıcı döndürür. (Geçersiz kılmaları [CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|
|[CBaseTabbedPane::GetPaneList](#getpanelist)|Sekmeli bölmesinde bulunan bölmeleri listesini döndürür.|
|[CBaseTabbedPane::GetTabArea](#gettabarea)|Üst ve alt sekmesinde alanlar için sınırlayıcı dikdörtgenler döndürür.|
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|Bir sekme penceresinde sekmeleri sayısını döndürür.|
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|Temel alınan (Sarmalanan) sekmesi penceresi alır.|
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|Görüntülenen sekmeleri sayısını döndürür.|
|[CBaseTabbedPane::HasAutoHideMode](#hasautohidemode)|Sekmeli bölme otomatik gizleme moduna geçiş olup olmadığını belirler.|
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|Bir sekme görüntülenen yalnızca sekmeli bölme gizli olup olmadığını belirler.|
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Serileştirme sırasında dahili olarak kullanılır.|
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|Düzen bölmesi bilgilerini yeniden hesaplar. (Geçersiz kılmaları [CPane::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|
|[CBaseTabbedPane::RemovePane](#removepane)|Bir bölme sekmeli bölmesinden kaldırır.|
|`CBaseTabbedPane::SaveSiblingBarIDs`|Serileştirme sırasında dahili olarak kullanılır.|
|`CBaseTabbedPane::Serialize`|(Geçersiz kılmaları [CDockablePane::Serialize](cdockablepane-class.md).)|
|`CBaseTabbedPane::SerializeTabWindow`|Serileştirme sırasında dahili olarak kullanılır.|
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|Sekmeli denetim çubuğu otomatik olarak edileceği olup olmadığını belirler.|
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|Yerleştirme bölmesi arasında görüntülenen değiştirir ve otomatik gizleme modu. (Geçersiz kılmaları [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|
|[CBaseTabbedPane::ShowTab](#showtab)|Bir sekme gizler veya gösterir.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, soyut bir sınıf olan ve örnekleri oluşturulamaz. Sekmeli bölmelerde her tür için ortak olan hizmetlere uygular.

Şu anda iki türetilmiş sekmeli bölme sınıf kitaplığı içerir: [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md) ve [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).

A `CBaseTabbedPane` nesne için bir işaretçi sarar bir [CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md) nesne. [CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md) sekmeli bölme alt penceresi daha sonra olur.

Sekmeli bölmelerde oluşturma hakkında daha fazla bilgi için bkz. [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md), [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md), ve [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

`CBaseTabbedPane`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxBaseTabbedPane.h

##  <a name="addtab"></a>  CBaseTabbedPane::AddTab

Yeni bir sekme sekmeli bir bölmeye ekler.

```
virtual BOOL AddTab(
    CWnd* pNewBar,
    BOOL bVisible = TRUE,
    BOOL bSetActive = TRUE,
    BOOL bDetachable = TRUE);
```

### <a name="parameters"></a>Parametreler

*pNewBar*<br/>
[out içinde] Bölmesine eklemek için bir işaretçi. Bu yöntem çağrısından sonra bu işaretçinin geçersiz hale gelebilir. Daha fazla bilgi için Açıklamalar bölümüne bakın.

*bVisible*<br/>
[in] Sekme görünür yapmak için TRUE; Aksi takdirde FALSE.

*bSetActive*<br/>
[in] Etkin sekmede sekmesini yapmak için TRUE; Aksi takdirde FALSE.

*bDetachable*<br/>
[in] Sekme çıkarılabilir yapmak için TRUE; Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

TRUE bölmesinde bir sekme başarıyla eklendi ve işlemde yok edilmez. Eklenen bölmesinde bir nesne türü ise FALSE `CBaseTabbedPane`. Daha fazla bilgi için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Bir bölme sekmeli bir bölmeye yeni bir sekmede olarak eklemek için bu yöntemi çağırın. Varsa *pNewBar* türündeki bir nesneye işaret `CBaseTabbedPane`, tüm sekmeler sekmeli bölmesinden kopyalanır ve ardından *pNewBar* yok. Bu nedenle, *pNewBar* geçersiz bir işaretçi alır ve kullanılmamalıdır.

##  <a name="allowdestroyemptytabbedpane"></a>  CBaseTabbedPane::AllowDestroyEmptyTabbedPane

Boş bir sekmeli bölme yok edilebilir olup olmadığını belirtir.

```
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

Boş bir sekmeli bölme yok edilebilir TRUE; Aksi takdirde FALSE. Varsayılan uygulama her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Boş bir sekmeli bölme yok edileceği izin verilmiyorsa framework bölmesi yerine gizler.

##  <a name="applyrestoredtabinfo"></a>  CBaseTabbedPane::ApplyRestoredTabInfo

Sekme ayarları kayıt defterinden yükler ve bunları sekmeli bir bölmeye uygular.

```
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```

### <a name="parameters"></a>Parametreler

*bUseTabIndexes*<br/>
[in] Bu parametre, framework tarafından dahili olarak kullanılır.

### <a name="remarks"></a>Açıklamalar

Yerleştirme durumu bilgilerini kayıt defterinden yüklediğinde bu yöntem framework tarafından çağırılır. Yöntemi, sekme sırasını ve sekmeli bölme için sekmesinde adları hakkında bilgi alır.

##  <a name="canfloat"></a>  CBaseTabbedPane::CanFloat

Sekmeli bölme kaydırabilirsiniz olup olmadığını belirtir.

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde kaydırabilirsiniz TRUE; Aksi takdirde FALSE.

##  <a name="cansetcaptiontexttotabname"></a>  CBaseTabbedPane::CanSetCaptionTextToTabName

Sekmeli bölmesi için açıklama yazısını etkin sekme aynı metni görüntüleyip görüntülemeyeceğini belirler.

```
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekmeli bölme açıklamalı alt yazı metni etkin sekmede metne olarak ayarlanmışsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Yöntemi, metin sekmeli bölme açıklamalı alt yazı çoğaltmaların üzerinde etkin sekmede etiketi gösterilip belirlemek için kullanılır. Etkinleştirebilir veya çağırarak bu işlevi devre dışı [CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname).

##  <a name="converttotabbeddocument"></a>  CBaseTabbedPane::ConvertToTabbedDocument

Bir veya daha fazla yerleştirilebilir bölmeleri MDI sekmeli belgeye dönüştürür.

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>Parametreler

*bActiveTabOnly*<br/>
[in] Sekmeli bir bölmeye dönüştürdüğünüzde, yalnızca etkin sekmede dönüştürmek için true değerini belirtin. Bölmedeki tüm sekmeleri dönüştürmek için FALSE belirtin.

##  <a name="detachpane"></a>  CBaseTabbedPane::DetachPane

Sekmeli bölme bölmesinden ayırır.

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[in] Bölmesinde ayırmak için işaretçi.

*bHide*<br/>
[in] Ayrılmış sonra framework bölmesini gizler olup olmadığını belirten Boole parametresi.

### <a name="return-value"></a>Dönüş Değeri

Framework başarıyla bölmeyi ayırır, TRUE; FALSE ise *pBar* boş ise veya sekmeli bölmesinde değil bir bölme ifade eder.

### <a name="remarks"></a>Açıklamalar

Framework ayrılmış bölmesinde mümkünse kayar. Daha fazla bilgi için [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).

##  <a name="enablesetcaptiontexttotabname"></a>  CBaseTabbedPane::EnableSetCaptionTextToTabName

Etkinleştirir veya sekmeli bölme etkin sekmede etiket metni ile açıklamalı alt yazı metni eşitlemek yeteneği devre dışı bırakır.

```
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Sekmeli Bölmesi Başlığı etkin sekme açıklamalı eşitlemek için TRUE; Aksi takdirde FALSE.

##  <a name="filldefaulttabsorderarray"></a>  CBaseTabbedPane::FillDefaultTabsOrderArray

İç sekme sırası varsayılan durumuna geri yükler.

```
void FillDefaultTabsOrderArray();
```

### <a name="remarks"></a>Açıklamalar

Framework bir Outlook Çubuğu bir ilk durumuna geri yükler. Bu yöntem çağrılır.

##  <a name="findpanebyid"></a>  CBaseTabbedPane::FindPaneByID

Bölmesinde kimliği tarafından tanımlanan bölme döndürür

```
virtual CWnd* FindPaneByID(UINT uBarID);
```

### <a name="parameters"></a>Parametreler

*uBarID*<br/>
[in] Bulunacak bölmesinde Kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi, bulunmadıysa bölmesine; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tüm sekmeler bölmesinde karşılaştırır ve tarafından belirtilen Kimliğe sahip bir döndürür *uBarID* parametresi.

##  <a name="findbarbytabnumber"></a>  CBaseTabbedPane::FindBarByTabNumber

Bir sekmede bulunduğu bir bölme döndürür.

```
virtual CWnd* FindBarByTabNumber(
    int nTabNum,
    BOOL bGetWrappedBar = FALSE);
```

### <a name="parameters"></a>Parametreler

*nTabNum*<br/>
[in] Almak için sekmesinde sıfır tabanlı dizini belirtir.

*bGetWrappedBar*<br/>
[in] Temel alınan (Sarmalanan) pencereyi bölmesinin bölmesi yerine döndürmek için TRUE; Aksi durumda FALSE. Bu, yalnızca türetilmiş bölmelere geçerlidir [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md).

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde bulunursa, geçerli bir işaretçi Aranan bölmesine verilir; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Tarafından belirtilen sekmesinde bulunan bölmesinde almak için bu yöntemi çağırın *nTabNum* parametresi.

##  <a name="floattab"></a>  CBaseTabbedPane::FloatTab

Bölmeyi şu anda çıkarılabilir bir sekmede yer alıyorsa ancak yalnızca bir bölme kaydırır.

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[out içinde] Kayan nokta bölmesi için bir işaretçi.

*nTabID*<br/>
[in] Kayan nokta için sekmesinde sıfır tabanlı dizini belirtir.

*dockMethod*<br/>
[in] Bölmesinde float yapmak için kullanılacak yöntemi belirtir. Daha fazla bilgi için Açıklamalar bölümüne bakın.

*bHide*<br/>
[in] Kayan önce bölmesinde gizlemek için TRUE; Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde kaydırıldı TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Şu anda bir çıkarılabilir sekmesinde bulunan bir bölme kaydırmak için bu yöntemi çağırın.

Bir bölme programlı olarak ayırmak istediğinizde, için DM_SHOW belirtin *dockMethod* parametresi. Burada, kaydırıldı daha önce aynı konumda bölmesinde kaydırmak olarak DM_DBL_CLICK belirtin *dockMethod* parametresi.

##  <a name="getdefaulttabsorder"></a>  CBaseTabbedPane::GetDefaultTabsOrder

Varsayılan sekme sırasını bölmesinde döndürür.

```
const CArray<int,int>& GetDefaultTabsOrder();
```

### <a name="return-value"></a>Dönüş Değeri

A `CArray` nesnesini bölmede sekme varsayılan sırayı belirtir.

### <a name="remarks"></a>Açıklamalar

Bir Outlook Çubuğu bir ilk duruma sıfırlandığında framework bu yöntemi çağırır.

##  <a name="getfirstvisibletab"></a>  CBaseTabbedPane::GetFirstVisibleTab

İlk görüntülenen sekme için bir işaretçi alır.

```
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```

### <a name="parameters"></a>Parametreler

*iTabNum*<br/>
[in] Bir tamsayının bir başvuru. Bu yöntem ilk görüntülenen sekmeyi sıfır tabanlı dizini bu parametresi veya -1 görüntülenen Hayır ise sekmesinde bulunan yazar.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ilk görüntülenen sekmesini; bir işaretçi Aksi takdirde NULL.

##  <a name="getminsize"></a>  CBaseTabbedPane::GetMinSize

Bölme boyutu izin verilen en düşük alır.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
[out] A `CSize` boyutu izin verilen en düşük ile doldurulan bir nesne.

### <a name="remarks"></a>Açıklamalar

Minimum bölme boyutlarda tutarlı işleme etkinse ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *boyutu* etkin sekme boyutu izin verilen en düşük ile doldurulur. Aksi takdirde, *boyutu* dönüş değeriyle doldurulur [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).

##  <a name="getpaneicon"></a>  CBaseTabbedPane::GetPaneIcon

Bölme boyutu izin verilen en düşük alır.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
[out] A `CSize` boyutu izin verilen en düşük ile doldurulan bir nesne.

### <a name="remarks"></a>Açıklamalar

Minimum bölme boyutlarda tutarlı işleme etkinse ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *boyutu* etkin sekme boyutu izin verilen en düşük ile doldurulur. Aksi takdirde, *boyutu* dönüş değeriyle doldurulur [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).

##  <a name="getpanelist"></a>  CBaseTabbedPane::GetPaneList

Sekmeli bölmesinde bulunan bölmeleri listesini döndürür.

```
virtual void GetPaneList(
    CObList& lst,
    CRuntimeClass* pRTCFilter = NULL);
```

### <a name="parameters"></a>Parametreler

*lst*<br/>
[out] A `CObList` sekmeli bölmesinde bulunan bölmelerin ile doldurulur.

*pRTCFilter*<br/>
[in] NULL değilse, döndürülen liste belirtilen çalışma zamanı sınıfının olan bölmeleri içerir.

##  <a name="gettabarea"></a>  CBaseTabbedPane::GetTabArea

Üst ve alt sekmesinde alanlar için sınırlayıcı dikdörtgenler döndürür.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const = 0;
```

### <a name="parameters"></a>Parametreler

*rectTabAreaTop*<br/>
[out] Üst sekme alanının ekran koordinatları alır.

*rectTabAreaBottom*<br/>
[out] Ekran koordinatları alt sekme alanının alır.

### <a name="remarks"></a>Açıklamalar

Ekran koordinatları, sekme üst ve alt alanlar için sınırlayıcı dikdörtgenler belirlemek için bu yöntemi çağırın.

##  <a name="gettabsnum"></a>  CBaseTabbedPane::GetTabsNum

Bir sekme penceresinde sekmeleri sayısını döndürür.

```
virtual int GetTabsNum() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekmeli bölme sekmelerde sayısı.

##  <a name="getunderlyingwindow"></a>  CBaseTabbedPane::GetUnderlyingWindow

Temel alınan (Sarmalanan) sekmesi penceresi alır.

```
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan sekmesi penceresi için bir işaretçi.

##  <a name="getvisibletabsnum"></a>  CBaseTabbedPane::GetVisibleTabsNum

Görünen sekmeler sayısını döndürür.

```
virtual int GetVisibleTabsNum() const;
```

### <a name="return-value"></a>Dönüş Değeri

Büyük veya sıfıra eşit olacak görünür sekme sayısı.

### <a name="remarks"></a>Açıklamalar

Sekmeli bölmesinde görünen sekmeler sayısını belirlemek için bu yöntemi çağırın.

##  <a name="hasautohidemode"></a>  CBaseTabbedPane::HasAutoHideMode

Sekmeli bölme autohide moduna geçiş olup olmadığını belirler.

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Otomatik Gizle moduna bölmesinde değiştirilebilir TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Otomatik Gizle modu devre dışı bırakılırsa, hiç pin düğmesini sekmeli bölme resim yazısını görüntülenir.

##  <a name="ishidesingletab"></a>  CBaseTabbedPane::IsHideSingleTab

Bir sekme görüntülenen yalnızca sekmeli bölme gizli olup olmadığını belirler.

```
virtual BOOL IsHideSingleTab() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tek bir görünür sekme olduğunda sekmesi penceresi görüntülenmiyorsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Tek bir sekme açık olduğundan bölmesi görüntülenmiyorsa sekmeli bölme doğru şekilde çalışıp çalışmadığını belirlemek için bu yöntemi çağırabilirsiniz.

##  <a name="removepane"></a>  CBaseTabbedPane::RemovePane

Bir bölme sekmeli bölmesinden kaldırır.

```
virtual BOOL RemovePane(CWnd* pBar);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[out içinde] Sekmeli bölmesinden kaldırmak için bölmesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sekmeli bölmesinden bölmesinde başarıyla kaldırıldıysa ve sekmeli bölme hala geçerliyse TRUE. Son bölmesinde sekmeli bölmesinden kaldırıldı ve edilmek için sekmeli bölme ise FALSE. Dönüş değeri FALSE ise, sekmeli bölme artık kullanmayın.

### <a name="remarks"></a>Açıklamalar

Tarafından belirtilen bölmesinde kaldırmak için bu yöntemi çağırın *pBar* parametresinden sekmeli bölme.

##  <a name="setautodestroy"></a>  CBaseTabbedPane::SetAutoDestroy

Sekmeli denetim çubuğu otomatik olarak edileceği olup olmadığını belirler.

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*bAutoDestroy*<br/>
[in] Sekmeli bölme dinamik olarak oluşturulmuş ve yaşam süresi denetleme değil ise TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Ayarlama sekmeli bir bölmeye dinamik olarak oluşturmak ve ömrü denetleme değil, doğru moda otomatik-yok. Otomatik yok modu ise TRUE, sekmeli bölme framework tarafından otomatik olarak edileceği.

##  <a name="showtab"></a>  CBaseTabbedPane::ShowTab

Bir sekme gizler veya gösterir.

```
virtual BOOL ShowTab(
    CWnd* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[in] Göstermek veya gizlemek için bölmesi için bir işaretçi.

*bBilgi Göster*<br/>
[in] Bölmesini görüntülemek için TRUE; Bölmesinde gizlemek için FALSE.

*bDelay*<br/>
[in] Sekme düzenini ayarlama geciktirmek için TRUE; Aksi takdirde FALSE.

*bActivate*<br/>
[in] Etkin sekmede sekmesini yapmak için TRUE; Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Sekmesinde gösterilen veya gizli başarıyla gerekiyorsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırdığınızda bir bölmesinde gösterilen veya gizli, bağlı olarak değeri *bBilgi Göster* parametresi. Bir sekme gizleyebilir ve temel alınan sekme penceresinde görünür son sekmeyi olan sekmeli bölme gizlenir. Sekmeli bölme vardır, daha önce hiç sekmeleri görünür bir sekme gösterirse, gösterilir.

##  <a name="recalclayout"></a>  CBaseTabbedPane::RecalcLayout

Düzen bölmesi bilgilerini yeniden hesaplar.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bölmesinde kayan, Mini çerçeve geçerli boyutunu bölmesi için framework bildirir.

Bu yöntem, bölmesinde yerleştirilmişse, hiçbir şey yapmaz.

##  <a name="setautohidemode"></a>  CBaseTabbedPane::SetAutoHideMode

Sekmeli bölmesinde çıkarılabilir bölmeleri için modu ayarlar otomatik olarak gizle.

```
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,
    DWORD dwAlignment,
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,
    BOOL bUseTimer = TRUE);
```

### <a name="parameters"></a>Parametreler

*bMode*<br/>
[in] Otomatik gizleme modunu etkinleştirmek için TRUE; Normal yerleştirme modunu etkinleştirmek için FALSE.

*dwAlignment*<br/>
[in] Oluşturulacak otomatik gizleme bölmesini hizalamasını belirtir. Olası değerler listesi için bkz. [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment).

*pCurrAutoHideBar*<br/>
[out içinde] Geçerli otomatik gizleme araç için bir işaretçi. NULL olabilir.

*bUseTimer*<br/>
[in] Otomatik gizleme etkin kullanıcı bölmesinde otomatik gizleme moduna geçiş yaptığında kullanın ya da bölmeyi hemen gizlemek için belirtir.

### <a name="return-value"></a>Dönüş Değeri

Hiçbir araç oluşturulursa otomatik gizleme modu veya NULL geçiş yaparken oluşturulan otomatik gizleme araç için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir kullanıcı sekmeli bölme otomatik gizleme modu veya normal yerleştirme moduna geçmek için pin düğmesini seçtiğinde framework bu yöntemi çağırır.

Otomatik gizleme modu sekmeli bölmesinde çıkarılabilir her bölme için ayarlanır. Çıkarılabilir olmayan bölmeleri göz ardı edilir. Daha fazla bilgi için [CMFCBaseTabCtrl::EnableTabDetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach).

Sekmeli bir bölmeye program aracılığıyla otomatik gizleme moduna geçmek için bu yöntemi çağırın. Ana çerçeve penceresine bölmenin yerleştirilmiş olmalıdır ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) geçerli işaretçi döndürmelidir [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)
