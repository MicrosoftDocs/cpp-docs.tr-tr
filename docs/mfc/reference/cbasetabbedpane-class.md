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
ms.openlocfilehash: d7ffaa7274a8ed12944cdbc5dcbbdcb8fd3fd2b9
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883686"
---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane sınıfı

Sekmeli pencerelerin oluşturulmasını desteklemek için [CDockablePane sınıfının](../../mfc/reference/cdockablepane-class.md) işlevselliğini genişletir.

## <a name="syntax"></a>Sözdizimi

```
class CBaseTabbedPane : public CDockablePane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CBaseTabbedPane::CBaseTabbedPane`|Varsayılan Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CBaseTabbedPane:: AddTab](#addtab)|Sekmeli bölmeye yeni bir sekme ekler.|
|[CBaseTabbedPane:: AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Boş bir sekmeli bölmenin yok edilip edilmeyeceğini belirtir.|
|[CBaseTabbedPane:: Applyrestoredtabınfo](#applyrestoredtabinfo)|Kayıt defterinden bir sekmeli bölmeye yüklenen sekme ayarlarını uygular.|
|[CBaseTabbedPane:: CanFloat](#canfloat)|Bölmenin kayıp kayamayacağını belirler. ( [CBasePane:: CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)) geçersiz kılar.|
|[CBaseTabbedPane:: CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Sekmeli bölme başlığının etkin sekmeyle aynı metni görüntüleyip görüntülemeyeceği belirler.|
|[CBaseTabbedPane:: ConvertToTabbedDocument](#converttotabbeddocument)|( [CDockablePane:: ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument)geçersiz kılar.)|
|[CBaseTabbedPane::D etachPane](#detachpane)|Bir veya daha fazla yerleştirilebilir bölmesini MDI sekmeli belgelerine dönüştürür.|
|[CBaseTabbedPane:: EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|Sekmeli bölmenin açıklamalı alt yazı metnini etkin sekmesindeki etiket metniyle eşitlemesini sağlar veya devre dışı bırakır.|
|[CBaseTabbedPane:: FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|İç sekme sırasını varsayılan durumuna geri yükler.|
|[CBaseTabbedPane:: FindBarByTabNumber](#findbarbytabnumber)|Sekme, sıfır tabanlı sekme dizini tarafından tanımlandığında bir sekmede bulunan bir bölmeyi döndürür.|
|||
|[CBaseTabbedPane:: Findbölmesi Byıd](#findpanebyid)|Bölme KIMLIĞI tarafından tanımlanan bir bölmeyi döndürür.|
|[CBaseTabbedPane:: FloatTab](#floattab)|Bir bölmeyi, ancak yalnızca bölme şu anda çıkarılabilir bir sekmede bulunuyorsa kayar.|
|[CBaseTabbedPane:: GetDefaultTabsOrder](#getdefaulttabsorder)|Bölmedeki sekmelerin varsayılan sırasını döndürür.|
|[CBaseTabbedPane:: GetFirstVisibleTab](#getfirstvisibletab)|İlk görüntülenmiş sekmeye bir işaretçi alır.|
|[CBaseTabbedPane:: GetMinSize](#getminsize)|Bölme için izin verilen en küçük boyutu alır. ( [CPane:: GetMinSize](../../mfc/reference/cpane-class.md#getminsize).) öğesini geçersiz kılar|
|[CBaseTabbedPane:: GetPaneIcon](#getpaneicon)|Bölme simgesine bir tanıtıcı döndürür. ( [CBasePane:: GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).) öğesini geçersiz kılar|
|[CBaseTabbedPane:: Getbölmesi listesi](#getpanelist)|Sekmeli bölmedeki bölmeler listesini döndürür.|
|[CBaseTabbedPane:: GetTabArea](#gettabarea)|Üst ve alt sekme alanlarının sınırlayıcı dikdörtgenlerini döndürür.|
|[CBaseTabbedPane:: GetTabsNum](#gettabsnum)|Sekme penceresindeki sekmelerin sayısını döndürür.|
|[CBaseTabbedPane:: GetUnderlyingWindow](#getunderlyingwindow)|Temel alınan (kaydırılan) sekme penceresini alır.|
|[CBaseTabbedPane:: GetVisibleTabsNum](#getvisibletabsnum)|Görüntülenmiş sekmelerin sayısını döndürür.|
|[CBaseTabbedPane:: HasAutoHideMode](#hasautohidemode)|Sekmeli bölmenin otomatik gizleme moduna geçiş yapıp yapamayacağını belirler.|
|[CBaseTabbedPane:: ıshidesingletab](#ishidesingletab)|Yalnızca bir sekme görüntüleniyorsa sekmeli bölmenin gizlenip gizlenmeyeceğini belirler.|
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Serileştirme sırasında dahili olarak kullanılır.|
|[CBaseTabbedPane:: RecalcLayout](#recalclayout)|Bölmenin düzen bilgilerini yeniden hesaplar. ( [CPane:: RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).) öğesini geçersiz kılar|
|[CBaseTabbedPane:: RemovePane](#removepane)|Sekmeli bölmeden bir bölmeyi kaldırır.|
|`CBaseTabbedPane::SaveSiblingBarIDs`|Serileştirme sırasında dahili olarak kullanılır.|
|`CBaseTabbedPane::Serialize`|( [CDockablePane:: serileştirme](cdockablepane-class.md)geçersiz kılar.)|
|`CBaseTabbedPane::SerializeTabWindow`|Serileştirme sırasında dahili olarak kullanılır.|
|[CBaseTabbedPane:: SetAutoDestroy](#setautodestroy)|Sekmeli denetim çubuğunun otomatik olarak yok edileceği olup olmayacağını belirler.|
|[CBaseTabbedPane:: SetAutoHideMode](#setautohidemode)|Yerleştirme bölmesini, görüntülenmiş ve otomatik gizleme modu arasında değiştirir. ( [CDockablePane:: SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode)'u geçersiz kılar.)|
|[CBaseTabbedPane:: ShowTab](#showtab)|Bir sekmeyi gösterir veya gizler.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, soyut bir sınıftır ve örneklenemez. Her türlü sekmeli bölme için ortak olan hizmetleri uygular.

Şu anda, kitaplık iki türetilmiş sekmeli bölme sınıfı içerir: [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md) ve [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).

`CBaseTabbedPane` nesnesi bir [CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md) nesnesine bir işaretçi sarmalar. [CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md) daha sonra sekmeli bölmenin bir alt penceresi haline gelir.

Sekmeli bölmeler oluşturma hakkında daha fazla bilgi için bkz. [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md), [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md)ve [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

`CBaseTabbedPane`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxBaseTabbedPane. h

##  <a name="addtab"></a>CBaseTabbedPane:: AddTab

Sekmeli bölmeye yeni bir sekme ekler.

```
virtual BOOL AddTab(
    CWnd* pNewBar,
    BOOL bVisible = TRUE,
    BOOL bSetActive = TRUE,
    BOOL bDetachable = TRUE);
```

### <a name="parameters"></a>Parametreler

*pNewBar*<br/>
[in, out] Eklenecek bölmeye yönelik bir işaretçi. Bu yöntemi çağırdıktan sonra bu işaretçi geçersiz hale gelebilir. Daha fazla bilgi için, açıklamalar bölümüne bakın.

*bVisible*<br/>
'ndaki Sekmeyi görünür hale getirmek için TRUE; Aksi takdirde, FALSE.

*bSetActive*<br/>
'ndaki Sekmeyi etkin sekmesine getirmek için TRUE; Aksi takdirde, FALSE.

*Ayrılabilir*<br/>
'ndaki Sekmeyi çıkarılabilir hale getirmek için TRUE; Aksi takdirde, FALSE.

### <a name="return-value"></a>Dönüş Değeri

Bölme başarıyla bir sekme olarak eklendiyse ve işlemde yok edilmediyse TRUE. Eklenmekte olan bölme `CBaseTabbedPane`türünde bir nesne ise FALSE. Daha fazla bilgi için, açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Sekmeli bir bölmeye yeni sekme olarak bir bölme eklemek için bu yöntemi çağırın. *Pnewbar* `CBaseTabbedPane`türünde bir nesneye işaret ediyorsa, tüm sekmeleri sekmeli bölmeye kopyalanır ve sonra *pNewBar* yok edilir. Bu nedenle, *pNewBar* geçersiz bir işaretçi haline gelir ve kullanılmamalıdır.

##  <a name="allowdestroyemptytabbedpane"></a>CBaseTabbedPane:: AllowDestroyEmptyTabbedPane

Boş bir sekmeli bölmenin yok edilip edilmeyeceğini belirtir.

```
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

Boş bir sekmeli bölme yok edilebiliyorsa TRUE; Aksi takdirde, FALSE. Varsayılan uygulama her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Boş bir sekmeli bölmenin yok edilmesi izin verilmiyorsa, çerçeve bunun yerine bölmeyi gizler.

##  <a name="applyrestoredtabinfo"></a>CBaseTabbedPane:: Applyrestoredtabınfo

Kayıt defterinden sekme ayarlarını yükler ve sekmeli bir bölmeye uygular.

```
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```

### <a name="parameters"></a>Parametreler

*bUseTabIndexes*<br/>
'ndaki Bu parametre, Framework tarafından dahili olarak kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterinden takma durum bilgilerini yeniden yüklediğinde Framework tarafından çağırılır. Yöntemi sekmeli bölme için sekme sırası ve sekme adları hakkında bilgi edinir.

##  <a name="canfloat"></a>CBaseTabbedPane:: CanFloat

Sekmeli bölmenin kayıp kayamayacağını belirtir.

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme kaybiliyorsa, doğru; Aksi takdirde, FALSE.

##  <a name="cansetcaptiontexttotabname"></a>CBaseTabbedPane:: CanSetCaptionTextToTabName

Sekmeli bölme başlığının etkin sekmeyle aynı metni görüntüleyip görüntülemeyeceği belirler.

```
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekmeli bölmenin açıklamalı alt yazı metni etkin sekmenin metni olarak ayarlandıysa, doğru. Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Yöntemi, sekmeli bölme başlığı üzerinde görünen metnin etkin sekmenin etiketini çoğaltmasının gerekip gerekmediğini belirlemekte kullanılır. [CBaseTabbedPane:: EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)çağırarak bu işlevselliği etkinleştirebilir veya devre dışı bırakabilirsiniz.

##  <a name="converttotabbeddocument"></a>CBaseTabbedPane:: ConvertToTabbedDocument

Bir veya daha fazla yerleştirilebilir bölmesini MDI sekmeli belgelerine dönüştürür.

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>Parametreler

*yalnızca bactivetab*<br/>
'ndaki Sekmeli bir bölmeyi dönüştürdüğünüzde, yalnızca etkin sekmesini dönüştürmek için TRUE değerini belirtin. bölmedeki tüm sekmeleri dönüştürmek için FALSE belirtin.

##  <a name="detachpane"></a>CBaseTabbedPane::D etachPane

Sekmeli bölmeden bir bölmeyi ayırır.

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
'ndaki Ayrılmak için bölmenin işaretçisi.

*bHide*<br/>
'ndaki Çerçevenin ayrıldıktan sonra bölmeyi gizleyemeyeceğini belirten Boolean parametresi.

### <a name="return-value"></a>Dönüş Değeri

Framework bölmeyi başarıyla ayırır; *PBar* null ise veya sekmeli bölmede olmayan bir bölmeyi ifade eder.

### <a name="remarks"></a>Açıklamalar

Çerçeve, mümkünse ayrılan bölmeyi float. Daha fazla bilgi için bkz. [CBasePane:: CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).

##  <a name="enablesetcaptiontexttotabname"></a>CBaseTabbedPane:: EnableSetCaptionTextToTabName

Sekmeli bölmenin açıklamalı alt yazı metnini etkin sekmesindeki etiket metniyle eşitlemesini sağlar veya devre dışı bırakır.

```
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Sekmeli bölme başlığını etkin sekme başlığı ile senkronize etmek için TRUE; Aksi takdirde, FALSE.

##  <a name="filldefaulttabsorderarray"></a>CBaseTabbedPane:: FillDefaultTabsOrderArray

İç sekme sırasını varsayılan durumuna geri yükler.

```
void FillDefaultTabsOrderArray();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Framework bir Outlook çubuğunu bir başlangıç durumuna geri yüklediğinde çağrılır.

##  <a name="findpanebyid"></a>CBaseTabbedPane:: Findbölmesi Byıd

Bölme KIMLIĞI tarafından tanımlanan bir bölmeyi döndürür.

```
virtual CWnd* FindPaneByID(UINT uBarID);
```

### <a name="parameters"></a>Parametreler

*uBarID*<br/>
'ndaki Bulunacak bölmenin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa bölme için bir işaretçi; Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bölmedeki tüm sekmeleri karşılaştırır ve *uBarID* parametresi tarafından belirtilen kimliğe sahip olanı döndürür.

##  <a name="findbarbytabnumber"></a>CBaseTabbedPane:: FindBarByTabNumber

Bir sekmede bulunan bir bölmeyi döndürür.

```
virtual CWnd* FindBarByTabNumber(
    int nTabNum,
    BOOL bGetWrappedBar = FALSE);
```

### <a name="parameters"></a>Parametreler

*nTabNum*<br/>
'ndaki Alınacak sekmenin sıfır tabanlı dizinini belirtir.

*bGetWrappedBar*<br/>
'ndaki Bölmenin kendisi yerine, bölmenin temel (kaydırılan) penceresini döndürmek için TRUE; Aksi halde yanlış. Bu yalnızca [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)'dan türetilmiş bölmeler için geçerlidir.

### <a name="return-value"></a>Dönüş Değeri

Bölmesi bulunursa, aranmakta olan bölmeye yönelik geçerli bir işaretçi döndürülür; Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

*NTabNum* parametresi tarafından belirtilen sekmede bulunan bölmeyi almak için bu yöntemi çağırın.

##  <a name="floattab"></a>CBaseTabbedPane:: FloatTab

Bir bölmeyi, ancak yalnızca bölme şu anda çıkarılabilir bir sekmede bulunuyorsa kayar.

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[in, out] Kaydırma için bölmeye yönelik bir işaretçi.

*Ntabıd*<br/>
'ndaki Kayan sekmenin sıfır tabanlı dizinini belirtir.

*Dockyöntemi*<br/>
'ndaki Bölmeyi yüzer hale getirmek için kullanılacak yöntemi belirtir. Daha fazla bilgi için, açıklamalar bölümüne bakın.

*bHide*<br/>
'ndaki Kayan bölmeden gizlemek için TRUE; Aksi takdirde, FALSE.

### <a name="return-value"></a>Dönüş Değeri

Bölme katalıyorsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Şu anda çıkarılabilir bir sekmede bulunan bir bölmeyi kaydırmak için bu yöntemi çağırın.

Bir bölmeyi programlı bir şekilde ayırmak istiyorsanız, *dockMethod* parametresi için DM_SHOW belirtin. Bölmeyi daha önce kaydırılan aynı konumda kaydırmak istiyorsanız, *dockMethod* parametresi olarak DM_DBL_CLICK belirtin.

##  <a name="getdefaulttabsorder"></a>CBaseTabbedPane:: GetDefaultTabsOrder

Bölmedeki sekmelerin varsayılan sırasını döndürür.

```
const CArray<int,int>& GetDefaultTabsOrder();
```

### <a name="return-value"></a>Dönüş Değeri

Bölmedeki sekmelerin varsayılan sırasını belirten `CArray` nesnesi.

### <a name="remarks"></a>Açıklamalar

Bir Outlook çubuğu bir başlangıç durumuna sıfırlandığında Framework bu yöntemi çağırır.

##  <a name="getfirstvisibletab"></a>CBaseTabbedPane:: GetFirstVisibleTab

İlk görüntülenmiş sekmeye bir işaretçi alır.

```
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```

### <a name="parameters"></a>Parametreler

*ıtabnum*<br/>
'ndaki Tamsayıya bir başvuru. Bu yöntem, ilk görüntülenmiş sekmenin sıfır tabanlı dizinini bu parametreye yazar veya görüntülenmediğinde-1.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ilk görüntülenmiş sekmeye yönelik bir işaretçi; Aksi takdirde, NULL.

##  <a name="getminsize"></a>CBaseTabbedPane:: GetMinSize

Bölme için izin verilen en küçük boyutu alır.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
dışı İzin verilen en küçük boyut ile doldurulmuş `CSize` nesne.

### <a name="remarks"></a>Açıklamalar

Minimum bölme boyutlarının tutarlılığını işleme etkinse ( [CPane:: m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *Boyut* , etkin sekme için izin verilen en düşük boyutla doldurulur. Aksi halde, *Boyut* [CPane:: GetMinSize](../../mfc/reference/cpane-class.md#getminsize)dönüş değeri ile doldurulur.

##  <a name="getpaneicon"></a>CBaseTabbedPane:: GetPaneIcon

Bölme için izin verilen en küçük boyutu alır.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
dışı İzin verilen en küçük boyut ile doldurulmuş `CSize` nesne.

### <a name="remarks"></a>Açıklamalar

Minimum bölme boyutlarının tutarlılığını işleme etkinse ( [CPane:: m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *Boyut* , etkin sekme için izin verilen en düşük boyutla doldurulur. Aksi halde, *Boyut* [CPane:: GetMinSize](../../mfc/reference/cpane-class.md#getminsize)dönüş değeri ile doldurulur.

##  <a name="getpanelist"></a>CBaseTabbedPane:: Getbölmesi listesi

Sekmeli bölmedeki bölmeler listesini döndürür.

```
virtual void GetPaneList(
    CObList& lst,
    CRuntimeClass* pRTCFilter = NULL);
```

### <a name="parameters"></a>Parametreler

*LST*<br/>
dışı Sekmeli bölmedeki bölmeler ile doldurulmuş bir `CObList`.

*pRTCFilter*<br/>
'ndaki NULL değilse, döndürülen listede yalnızca belirtilen çalışma zamanı sınıfının bölmeleri bulunur.

##  <a name="gettabarea"></a>CBaseTabbedPane:: GetTabArea

Üst ve alt sekme alanlarının sınırlayıcı dikdörtgenlerini döndürür.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const = 0;
```

### <a name="parameters"></a>Parametreler

*rectTabAreaTop*<br/>
dışı Üst sekme alanının ekran koordinatlarını alır.

*rectTabAreaBottom*<br/>
dışı Alt sekme alanının ekran koordinatlarını alır.

### <a name="remarks"></a>Açıklamalar

Üst ve alt sekme alanlarının, Ekran koordinatlarındaki sınırlayıcı dörtgenler belirlenmesi için bu yöntemi çağırın.

##  <a name="gettabsnum"></a>CBaseTabbedPane:: GetTabsNum

Sekme penceresindeki sekmelerin sayısını döndürür.

```
virtual int GetTabsNum() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekmeli bölmedeki sekmelerin sayısı.

##  <a name="getunderlyingwindow"></a>CBaseTabbedPane:: GetUnderlyingWindow

Temel alınan (kaydırılan) sekme penceresini alır.

```
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```

### <a name="return-value"></a>Dönüş Değeri

Temel sekme penceresine yönelik bir işaretçi.

##  <a name="getvisibletabsnum"></a>CBaseTabbedPane:: GetVisibleTabsNum

Görünür sekmelerin sayısını döndürür.

```
virtual int GetVisibleTabsNum() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırdan büyük veya sıfıra eşit olacak görünür sekmelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Sekmeli bölmedeki görünür sekmelerin sayısını öğrenmek için bu yöntemi çağırın.

##  <a name="hasautohidemode"></a>CBaseTabbedPane:: HasAutoHideMode

Sekmeli bölmenin otomatik gizleme moduna geçirilip geçirilemeyeceğini belirler.

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme otomatik gizleme moduna geçtiyseniz doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Otomatik gizleme modu devre dışıysa sekmeli bölme başlığı üzerinde bir pin düğmesi gösterilmez.

##  <a name="ishidesingletab"></a>CBaseTabbedPane:: ıshidesingletab

Yalnızca bir sekme görüntüleniyorsa sekmeli bölmenin gizlenip gizlenmeyeceğini belirler.

```
virtual BOOL IsHideSingleTab() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca bir görünür sekme olduğunda sekme penceresi gösterilmezse TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Yalnızca bir sekme açık olduğundan bölme görüntülenmiyorsa, sekmeli bölmenin doğru çalışıp çalışmadığını anlamak için bu yöntemi çağırabilirsiniz.

##  <a name="removepane"></a>CBaseTabbedPane:: RemovePane

Sekmeli bölmeden bir bölmeyi kaldırır.

```
virtual BOOL RemovePane(CWnd* pBar);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[in, out] Sekmeli bölmeden kaldırılacak bölmeye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bölmesi sekmeli bölmeden başarıyla kaldırıldıysa ve sekmeli bölme hala geçerliyse TRUE. Sekmeli bölmeden son bölme kaldırılmışsa ve sekmeli bölme yok edilmek üzere olduğunda FALSE. Dönüş değeri FALSE ise, sekmeli bölmeyi daha fazla kullanmayın.

### <a name="remarks"></a>Açıklamalar

Sekmeli bölmedeki *pBar* parametresi tarafından belirtilen bölmeyi kaldırmak için bu yöntemi çağırın.

##  <a name="setautodestroy"></a>CBaseTabbedPane:: SetAutoDestroy

Sekmeli denetim çubuğunun otomatik olarak yok edileceği olup olmayacağını belirler.

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*bAutoDestroy*<br/>
'ndaki Sekmeli bölme dinamik olarak oluşturulduysa ve süresini denetlemekken doğru. Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Dinamik olarak bir sekmeli bölme oluşturursanız ve ömrünü denetlemekken otomatik yok etme modunu doğru olarak ayarlayın. Otomatik yok etme modu TRUE ise, sekmeli bölme Framework tarafından otomatik olarak yok edilir.

##  <a name="showtab"></a>CBaseTabbedPane:: ShowTab

Bir sekmeyi gösterir veya gizler.

```
virtual BOOL ShowTab(
    CWnd* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
'ndaki Göstermek veya gizlemek için bölmenin bir işaretçisi.

*bShow*<br/>
'ndaki Bölmeyi göstermek için TRUE; Bölmeyi gizlemek için FALSE.

*bDelay*<br/>
'ndaki Sekme düzeninin ayarlanmasını geciktirmek için TRUE. Aksi takdirde, FALSE.

*Bacetkinleştir*<br/>
'ndaki Sekmeyi etkin sekmesine getirmek için TRUE; Aksi takdirde, FALSE.

### <a name="return-value"></a>Dönüş Değeri

Sekme gösterildiyse veya başarıyla gizliyse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırdığınızda, *bShow* parametresinin değerine bağlı olarak bir bölme gösterilir ya da gizlenir. Bir sekmeyi gizlediyseniz ve temel sekme penceresindeki son görünür sekme ise sekmeli bölme gizlenir. Daha önce hiç sekme görünmemiş bir sekme alırsanız sekmeli bölme gösterilir.

##  <a name="recalclayout"></a>CBaseTabbedPane:: RecalcLayout

Bölmenin düzen bilgilerini yeniden hesaplar.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Açıklamalar

Bölme Eğer kayan ise, bu yöntem Framework 'ü, çerçeveyi mini çerçevenin geçerli boyutuna yeniden boyutlandırmasını bildirir.

Bölme yerleştirilmişse, bu yöntem hiçbir şey yapmaz.

##  <a name="setautohidemode"></a>CBaseTabbedPane:: SetAutoHideMode

Sekmeli bölmedeki ayrılabilir bölmeler için otomatik gizleme modunu ayarlar.

```
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,
    DWORD dwAlignment,
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,
    BOOL bUseTimer = TRUE);
```

### <a name="parameters"></a>Parametreler

*bMode*<br/>
'ndaki Otomatik gizleme modunu etkinleştirmek için TRUE; Normal yerleştirme modunu etkinleştirmek için FALSE.

*Dwhizalaması*<br/>
'ndaki Oluşturulacak otomatik gizleme bölmesinin hizalamasını belirtir. Olası değerler listesi için bkz. [CPane:: MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment).

*Pcurrayutohidebar*<br/>
[in, out] Geçerli otomatik gizleme araç çubuğuna bir işaretçi. NULL olabilir.

*bUseTimer*<br/>
'ndaki Kullanıcı bölmeyi otomatik gizleme moduna geçtiğinde ya da bölmeyi hemen gizlemek için otomatik gizleme efektinin kullanılıp kullanılmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizleme moduna geçiş yaparken oluşturulan otomatik gizleme araç çubuğuna yönelik bir işaretçi veya bir araç çubuğu oluşturulmadıysa NULL.

### <a name="remarks"></a>Açıklamalar

Kullanıcı, sekmeli bölmeyi otomatik gizleme moduna veya normal yerleştirme moduna geçirmek için Sabitle düğmesini seçtiğinde, bu yöntemi çağırır.

Sekmeli bölmedeki her bir ayrılabilir bölme için otomatik gizleme modu ayarlanır. Çıkarılabilir olmayan bölmeler yok sayılır. Daha fazla bilgi için bkz. [CMFCBaseTabCtrl:: EnableTabDetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach).

Sekmeli bir bölmeyi program aracılığıyla otomatik olarak gizleyecek şekilde değiştirmek için bu yöntemi çağırın. Bölmenin ana çerçeve penceresine yerleştirilmiş olması gerekir ( [CDockablePane:: GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) , [CPaneDivider](../../mfc/reference/cpanedivider-class.md)için geçerli bir işaretçi döndürmelidir).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)
