---
title: CBaseTabbedPane Sınıfı
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
ms.openlocfilehash: ce7c48263ed511545757c94d61552e6206e74a00
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352863"
---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane Sınıfı

Sekmeli pencerelerin oluşturulmasını desteklemek için [CDockablePane Sınıfının](../../mfc/reference/cdockablepane-class.md) işlevselliğini genişletir.

## <a name="syntax"></a>Sözdizimi

```
class CBaseTabbedPane : public CDockablePane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CBaseTabbedPane::CBaseTabbedPane`|Varsayılan oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CBaseTabbedPane::AddTab](#addtab)|Sekmeli bölmeye yeni bir sekme ekler.|
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Boş sekmeli bölmenin yok edilip edilmeyeceğini belirtir.|
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|Kayıt defterinden yüklenen sekme ayarlarını sekmeli bölmeye uygular.|
|[CBaseTabbedPane::CanFloat](#canfloat)|Bölmenin yüzdürüp yüzemeyeceğini belirler. [(Overrides CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Sekmeli bölmenin alt yazısının etkin sekmeyle aynı metni gösterip göstermeyeceğini belirler.|
|[CBaseTabbedPane::ConvertToTabbedBelgesi](#converttotabbeddocument)|[(CDockablePane geçersiz kılar::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|
|[CBaseTabbedPane::DetachPane](#detachpane)|Bir veya daha fazla takılabilir bölmeyi MDI sekmeli belgelere dönüştürür.|
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|Sekmeli bölmenin resim yazısı metnini etkin sekmedeki etiket metniyle eşitleme yeteneğini etkinleştirer veya devre dışı kılabilir.|
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|İç sekme sırasını varsayılan duruma geri yükler.|
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|Sekme sıfır tabanlı sekme dizini tarafından tanımlandığında sekmede bulunan bir bölmeyi döndürür.|
|||
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|Bölme kimliğiyle tanımlanan bir bölme döndürür.|
|[CBaseTabbedPane::FloatTab](#floattab)|Bir bölmeyi yüzer, ancak bölme şu anda çıkarılabilir bir sekmede bulunursa.|
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|Bölmedeki sekmelerin varsayılan sırasını verir.|
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|İlk görüntülenen sekmeye bir işaretçi alır.|
|[CBaseTabbedPane::GetMinSize](#getminsize)|Bölme için izin verilen minimum boyutu alır. (CPane geçersiz [kılar::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|Bölme simgesine bir tutamaç döndürür. [(CBasePane geçersiz kılar::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|
|[CBaseTabbedPane::GetPaneList](#getpanelist)|Sekmeli bölmede bulunan bölmelerin listesini verir.|
|[CBaseTabbedPane::GetTabArea](#gettabarea)|Üst ve alt sekme alanları için sınırlayıcı dikdörtgenleri döndürür.|
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|Sekme penceresindesek sayısını döndürür.|
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|Altta yatan (sarılmış) sekme penceresini alır.|
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|Görüntülenen sekme sayısını döndürür.|
|[CBaseTabbedPane::HasAutoHideMode](#hasautohidemode)|Sekmeli bölmenin otomatik gizleme moduna geçirilip geçirilmeyeceğini belirler.|
|[CBaseTabbedPane::IsHideTekTab](#ishidesingletab)|Yalnızca bir sekme görüntüleniyorsa sekmeli bölmenin gizli olup olmadığını belirler.|
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Serileştirme sırasında dahili olarak kullanılır.|
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|Bölmeiçin düzen bilgilerini yeniden hesaplar. [(CPane geçersiz kılar::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|
|[CBaseTabbedPane::RemovePane](#removepane)|Sekmeli bölmeden bir bölme kaldırır.|
|`CBaseTabbedPane::SaveSiblingBarIDs`|Serileştirme sırasında dahili olarak kullanılır.|
|`CBaseTabbedPane::Serialize`|[(CDockablePane geçersiz kılar::Serialize](cdockablepane-class.md).)|
|`CBaseTabbedPane::SerializeTabWindow`|Serileştirme sırasında dahili olarak kullanılır.|
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|Sekmeli denetim çubuğunun otomatik olarak yok edilip edilmeyeceğini belirler.|
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|Yerleştirme bölmesini görüntülenen ve otomatik gizleme modu arasında geçiş yapın. [(CDockablePane geçersiz kılar::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|
|[CBaseTabbedPane::ShowTab](#showtab)|Bir sekmeyi gösterir veya gizler.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf soyut bir sınıftır ve anında kullanılamaz. Sekmeli bölmelerin her türlü ortak hizmetleri uygular.

Şu anda, kitaplık iki türemiş sekmeli bölme sınıfları içerir: [CTabbedPane Sınıf](../../mfc/reference/ctabbedpane-class.md) ve [CMFCOutlookBar Sınıf.](../../mfc/reference/cmfcoutlookbar-class.md)

Bir `CBaseTabbedPane` nesne bir işaretçiyi [CMFCBaseTabCtrl Sınıf](../../mfc/reference/cmfcbasetabctrl-class.md) nesnesine kaydırıyor. [CMFCBaseTabCtrl Sınıf](../../mfc/reference/cmfcbasetabctrl-class.md) sonra sekmeli bölmenin bir alt penceresi olur.

Sekmeli bölmelerin nasıl oluşturulacağı hakkında daha fazla bilgi için [CDockablePane Class,](../../mfc/reference/cdockablepane-class.md) [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md)ve [CMFCOutlookBar Class'a](../../mfc/reference/cmfcoutlookbar-class.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[Cdockablepane](../../mfc/reference/cdockablepane-class.md)

`CBaseTabbedPane`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxBaseTabbedPane.h

## <a name="cbasetabbedpaneaddtab"></a><a name="addtab"></a>CBaseTabbedPane::AddTab

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
[içinde, dışarı] Eklemek için bölmeye bir işaretçi. Bu yöntemi aradıktan sonra bu işaretçi geçersiz olabilir. Daha fazla bilgi için Açıklamalar bölümüne bakın.

*bGörünür*<br/>
[içinde] Sekmeyi görünür kılmak için TRUE; aksi takdirde, YANLIŞ.

*bSetActive*<br/>
[içinde] Sekmeyi etkin sekme yapmak için TRUE; aksi takdirde, YANLIŞ.

*bDetachable*<br/>
[içinde] SEKMEYI çıkarılabilir yapmak için DOĞRU; aksi takdirde, YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Bölme başarıyla bir sekme olarak eklendiyse ve işlemde yok edilmediyse DOĞRU. Eklenen bölme bir tür `CBaseTabbedPane`nesnesi ise FALSE . Daha fazla bilgi için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Sekmeli bölmeye yeni bir sekme olarak bölme eklemek için bu yöntemi çağırın. *pNewBar* türdeki `CBaseTabbedPane`bir nesneye işaret ediyorsa, tüm sekmeleri sekmeli bölmeye kopyalanır ve *pNewBar* yok edilir. Bu nedenle, *pNewBar* geçersiz bir işaretçi olur ve kullanılmamalıdır.

## <a name="cbasetabbedpaneallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a>CBaseTabbedPane::AllowDestroyEmptyTabbedPane

Boş sekmeli bölmenin yok edilip edilmeyeceğini belirtir.

```
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

Boş sekmeli bölme yok edilebiliyorsa DOĞRU; aksi takdirde, YANLIŞ. Varsayılan uygulama her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Boş sekmeli bölmenin yok edilmesine izin verilmezse, çerçeve bölmeyi bunun yerine gizler.

## <a name="cbasetabbedpaneapplyrestoredtabinfo"></a><a name="applyrestoredtabinfo"></a>CBaseTabbedPane::ApplyRestoredTabInfo

Kayıt defterinden sekme ayarlarını yükler ve bunları sekmeli bölmeye uygular.

```
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```

### <a name="parameters"></a>Parametreler

*bUseTabIndexes*<br/>
[içinde] Bu parametre iç çerçeve tarafından kullanılır.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kayıt defterinden yerleştirme durumu bilgilerini yeniden yüklerken çerçeve tarafından çağrılır. Yöntem, sekmeli bölme için sekme sırası ve sekme adları hakkında bilgi alır.

## <a name="cbasetabbedpanecanfloat"></a><a name="canfloat"></a>CBaseTabbedPane::CanFloat

Sekmeli bölmenin yüzdürüp yüzemeyeceğini belirtir.

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme yüzebilirse DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cbasetabbedpanecansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a>CBaseTabbedPane::CanSetCaptionTextToTabName

Sekmeli bölmenin alt yazısının etkin sekmeyle aynı metni gösterip göstermeyeceğini belirler.

```
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekmeli bölmenin resim yazısı metni etkin sekme metnine ayarlanmışsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Yöntem, sekmeli bölme başlığında görüntülenen metnin etkin sekme etiketini yineleyip yinelenmediğini belirlemek için kullanılır. [CBaseTabbedPane::EnableSetCaptionTextToTabName'i](#enablesetcaptiontexttotabname)arayarak bu işlevi etkinleştirebilir veya devre dışı bırakabilirsiniz.

## <a name="cbasetabbedpaneconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>CBaseTabbedPane::ConvertToTabbedBelgesi

Bir veya daha fazla takılabilir bölmeyi MDI sekmeli belgelere dönüştürür.

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>Parametreler

*bActiveTabOnly*<br/>
[içinde] Sekmeli bölmeyi dönüştürdüğünüzde, yalnızca etkin sekmeyi dönüştürmek için TRUE'yu belirtin. Bölmedeki tüm sekmeleri dönüştürmek için FALSE belirtin.

## <a name="cbasetabbedpanedetachpane"></a><a name="detachpane"></a>CBaseTabbedPane::DetachPane

Sekmeli bölmeden bir bölme ayırır.

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde] Ayırmak için bölmeye işaretçi.

*bHide*<br/>
[içinde] Çerçevenin ayrıldıktan sonra bölmeyi gizleyip gizlemediğini belirten boolean parametresi.

### <a name="return-value"></a>Dönüş Değeri

Doğru çerçeve başarıyla bölmeyi ayırırsa; *pBar* NULL ise veya sekmeli bölmede olmayan bir bölmeye başvuruyorsa YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Çerçeve, mümkünse ayrılmış bölmeyi yüzdürer. Daha fazla bilgi için [Bkz. CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).

## <a name="cbasetabbedpaneenablesetcaptiontexttotabname"></a><a name="enablesetcaptiontexttotabname"></a>CBaseTabbedPane::EnableSetCaptionTextToTabName

Sekmeli bölmenin resim yazısı metnini etkin sekmedeki etiket metniyle eşitleme yeteneğini etkinleştirer veya devre dışı kılabilir.

```
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Sekmeli bölme başlığını etkin sekme başlığıyla senkronize etmek için TRUE; aksi takdirde, YANLIŞ.

## <a name="cbasetabbedpanefilldefaulttabsorderarray"></a><a name="filldefaulttabsorderarray"></a>CBaseTabbedPane::FillDefaultTabsOrderArray

İç sekme sırasını varsayılan duruma geri yükler.

```
void FillDefaultTabsOrderArray();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve bir Outlook çubuğunu ilk duruma geri yüklediğinde bu yöntem çağrılır.

## <a name="cbasetabbedpanefindpanebyid"></a><a name="findpanebyid"></a>CBaseTabbedPane::FindPaneByID

Bölme kimliğiyle tanımlanan bir bölme döndürür.

```
virtual CWnd* FindPaneByID(UINT uBarID);
```

### <a name="parameters"></a>Parametreler

*uBarID*<br/>
[içinde] Bulmak için bölmenin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa bölmeye bir işaretçi; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bölmedeki tüm sekmeleri karşılaştırır ve *uBarID* parametresi tarafından belirtilen kimlikle bir sekmeyi döndürür.

## <a name="cbasetabbedpanefindbarbytabnumber"></a><a name="findbarbytabnumber"></a>CBaseTabbedPane::FindBarByTabNumber

Sekmede bulunan bir bölmeyi döndürür.

```
virtual CWnd* FindBarByTabNumber(
    int nTabNum,
    BOOL bGetWrappedBar = FALSE);
```

### <a name="parameters"></a>Parametreler

*nTabNum*<br/>
[içinde] Alınacak sekmenin sıfır tabanlı dizinini belirtir.

*bGetWrappedBar*<br/>
[içinde] Bölmenin kendisi yerine bölmenin temel (sarılmış) penceresini döndürmek için TRUE; aksi takdirde YANLIŞ. Bu yalnızca [CDockablePaneAdapter'dan](../../mfc/reference/cdockablepaneadapter-class.md)türetilen bölmeler için geçerlidir.

### <a name="return-value"></a>Dönüş Değeri

Bölme bulunursa, aranmakta olan bölmeye geçerli bir işaretçi döndürülür; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

*nTabNum* parametresi tarafından belirtilen sekmede bulunan bölmeyi almak için bu yöntemi arayın.

## <a name="cbasetabbedpanefloattab"></a><a name="floattab"></a>CBaseTabbedPane::FloatTab

Bir bölmeyi yüzer, ancak bölme şu anda çıkarılabilir bir sekmede bulunursa.

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde, dışarı] Kaydırmak için bölmeye bir işaretçi.

*nTabID*<br/>
[içinde] Float için sekme sıfır tabanlı dizini belirtir.

*dockMethod*<br/>
[içinde] Bölmeyi float yapmak için kullanılacak yöntemi belirtir. Daha fazla bilgi için Açıklamalar bölümüne bakın.

*bHide*<br/>
[içinde] Doğru yüzen önce bölmeyi gizlemek için; aksi takdirde, YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Bölme yüzdürse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Şu anda çıkarılabilir bir sekmede bulunan bir bölmeyi kaydırmak için bu yöntemi arayın.

Bir bölmeyi programlı olarak ayırmak istiyorsanız, *dockMethod* parametresi için DM_SHOW belirtin. Bölmeyi daha önce yüzdüğü konumda float etmek istiyorsanız, *dockMethod* parametresi olarak DM_DBL_CLICK belirtin.

## <a name="cbasetabbedpanegetdefaulttabsorder"></a><a name="getdefaulttabsorder"></a>CBaseTabbedPane::GetDefaultTabsOrder

Bölmedeki sekmelerin varsayılan sırasını verir.

```
const CArray<int,int>& GetDefaultTabsOrder();
```

### <a name="return-value"></a>Dönüş Değeri

Bölmedeki sekmelerin varsayılan sırasını belirten bir `CArray` nesne.

### <a name="remarks"></a>Açıklamalar

Outlook çubuğu ilk duruma sıfırlandığında çerçeve bu yöntemi çağırır.

## <a name="cbasetabbedpanegetfirstvisibletab"></a><a name="getfirstvisibletab"></a>CBaseTabbedPane::GetFirstVisibleTab

İlk görüntülenen sekmeye bir işaretçi alır.

```
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```

### <a name="parameters"></a>Parametreler

*iTabNum*<br/>
[içinde] Tamsayıya gönderme. Bu yöntem, görüntülenen ilk sekmenin sıfır tabanlı dizinini bu parametreye veya görüntülenen sekme yoksa -1'e yazar.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ilk görüntülenen sekmeye işaretçi; aksi takdirde, NULL.

## <a name="cbasetabbedpanegetminsize"></a><a name="getminsize"></a>CBaseTabbedPane::GetMinSize

Bölme için izin verilen minimum boyutu alır.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
[çıkış] İzin `CSize` verilen en az boyutla doldurulmuş bir nesne.

### <a name="remarks"></a>Açıklamalar

Minimum bölme boyutlarının tutarlı kullanımı etkinse [(CPane:m_bHandleMinSize),](../../mfc/reference/cpane-class.md#m_bhandleminsize) *boyut* etkin sekme için izin verilen minimum boyutla doldurulur. Aksi *takdirde, boyut* CPane'nin iade değeriyle doldurulur::GetMinSize . [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize)

## <a name="cbasetabbedpanegetpaneicon"></a><a name="getpaneicon"></a>CBaseTabbedPane::GetPaneIcon

Bölme için izin verilen minimum boyutu alır.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
[çıkış] İzin `CSize` verilen en az boyutla doldurulmuş bir nesne.

### <a name="remarks"></a>Açıklamalar

Minimum bölme boyutlarının tutarlı kullanımı etkinse [(CPane:m_bHandleMinSize),](../../mfc/reference/cpane-class.md#m_bhandleminsize) *boyut* etkin sekme için izin verilen minimum boyutla doldurulur. Aksi *takdirde, boyut* CPane'nin iade değeriyle doldurulur::GetMinSize . [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize)

## <a name="cbasetabbedpanegetpanelist"></a><a name="getpanelist"></a>CBaseTabbedPane::GetPaneList

Sekmeli bölmede bulunan bölmelerin listesini verir.

```
virtual void GetPaneList(
    CObList& lst,
    CRuntimeClass* pRTCFilter = NULL);
```

### <a name="parameters"></a>Parametreler

*Lst*<br/>
[çıkış] `CObList` Sekmeli bölmede bulunan bölmelerle doldurulmuş bir bölme.

*pRTCFiltre*<br/>
[içinde] NULL değilse, döndürülen liste yalnızca belirtilen çalışma zamanı sınıfına ait bölmeleri içerir.

## <a name="cbasetabbedpanegettabarea"></a><a name="gettabarea"></a>CBaseTabbedPane::GetTabArea

Üst ve alt sekme alanları için sınırlayıcı dikdörtgenleri döndürür.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const = 0;
```

### <a name="parameters"></a>Parametreler

*rectTabAreaTop*<br/>
[çıkış] Üst sekme alanının ekran koordinatlarını alır.

*rectTabAreaBottom*<br/>
[çıkış] Alt sekme alanının ekran koordinatlarını alır.

### <a name="remarks"></a>Açıklamalar

Üst ve alt sekme alanları için ekran koordinatlarında sınırlayıcı dikdörtgenleri belirlemek için bu yöntemi arayın.

## <a name="cbasetabbedpanegettabsnum"></a><a name="gettabsnum"></a>CBaseTabbedPane::GetTabsNum

Sekme penceresindesek sayısını döndürür.

```
virtual int GetTabsNum() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekmeli bölmedeki sekme sayısı.

## <a name="cbasetabbedpanegetunderlyingwindow"></a><a name="getunderlyingwindow"></a>CBaseTabbedPane::GetUnderlyingWindow

Altta yatan (sarılmış) sekme penceresini alır.

```
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```

### <a name="return-value"></a>Dönüş Değeri

Alttaki sekme penceresiiçin bir işaretçi.

## <a name="cbasetabbedpanegetvisibletabsnum"></a><a name="getvisibletabsnum"></a>CBaseTabbedPane::GetVisibleTabsNum

Görünür sekme sayısını döndürür.

```
virtual int GetVisibleTabsNum() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırdan büyük veya eşit olacak görünür sekmelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Sekmeli bölmedeki görünür sekme sayısını belirlemek için bu yöntemi arayın.

## <a name="cbasetabbedpanehasautohidemode"></a><a name="hasautohidemode"></a>CBaseTabbedPane::HasAutoHideMode

Sekmeli bölmenin otomatik hide moduna geçirilip geçirilmeyeceğini belirler.

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme otomatik hide moduna geçilebiliyorsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Otomatik hide modu devre dışı bırakılırsa, sekmeli bölme başlığında pin düğmesi görüntülenmez.

## <a name="cbasetabbedpaneishidesingletab"></a><a name="ishidesingletab"></a>CBaseTabbedPane::IsHideTekTab

Yalnızca bir sekme görüntüleniyorsa sekmeli bölmenin gizli olup olmadığını belirler.

```
virtual BOOL IsHideSingleTab() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnızca bir görünür sekme olduğunda sekme penceresi görünmüyorsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Yalnızca bir sekme açık olduğundan bölme görüntülenmiyorsa, sekmeli bölmenin doğru çalışıp çalışmadığını belirlemek için bu yöntemi arayabilirsiniz.

## <a name="cbasetabbedpaneremovepane"></a><a name="removepane"></a>CBaseTabbedPane::RemovePane

Sekmeli bölmeden bir bölme kaldırır.

```
virtual BOOL RemovePane(CWnd* pBar);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde, dışarı] Sekmeli bölmeden kaldırmak için bölmeye bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bölme sekmeli bölmeden başarıyla kaldırıldıysa ve sekmeli bölme hala geçerliyse DOĞRU. Son bölme sekmeli bölmeden çıkarılmışsa ve sekmeli bölme yok olmak üzereyse YANLIŞ. İade değeri FALSE ise, sekmeli bölmeyi artık kullanmayın.

### <a name="remarks"></a>Açıklamalar

*pBar* parametresi tarafından belirtilen bölmeyi sekmeli bölmeden kaldırmak için bu yöntemi çağırın.

## <a name="cbasetabbedpanesetautodestroy"></a><a name="setautodestroy"></a>CBaseTabbedPane::SetAutoDestroy

Sekmeli denetim çubuğunun otomatik olarak yok edilip edilmeyeceğini belirler.

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*bAutoDestroy*<br/>
[içinde] Sekmeli bölme dinamik olarak oluşturulduysa ve ömrünü kontrol etmiyorsanız DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Otomatik yok etme modunu dinamik olarak sekmeli bir bölme oluşturuyorsanız ve ömrünü kontrol etmiyorsanız TRUE olarak ayarlayın. Otomatik yok et modu TRUE ise, sekmeli bölme çerçeve tarafından otomatik olarak yok edilir.

## <a name="cbasetabbedpaneshowtab"></a><a name="showtab"></a>CBaseTabbedPane::ShowTab

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
[içinde] Göstermek veya gizlemek için bölmeye bir işaretçi.

*bGöster*<br/>
[içinde] BÖLMEYI GÖSTERMEK IÇIN DOĞRU; Bölmeyi gizlemek için YANLIŞ.

*bGecikme*<br/>
[içinde] Sekme düzeninin ayarını geciktirmek için TRUE; aksi takdirde, YANLIŞ.

*bEtkinleştir*<br/>
[içinde] Sekmeyi etkin sekme yapmak için TRUE; aksi takdirde, YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Sekme başarıyla gösteriliyorsa veya gizleniyorsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırdığınızda, *bShow* parametresinin değerine bağlı olarak bir bölme gösterilir veya gizlenir. Bir sekme gizliyorsanız ve bu, alttaki sekme penceresindeki son görünür sekmeyse, sekmeli bölme gizlenir. Daha önce görünür sekme yokken bir sekme gösterirseniz, sekmeli bölme gösterilir.

## <a name="cbasetabbedpanerecalclayout"></a><a name="recalclayout"></a>CBaseTabbedPane::RecalcLayout

Bölmeiçin düzen bilgilerini yeniden hesaplar.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Açıklamalar

Bölme kayan ise, bu yöntem bölmeyi mini çerçevenin geçerli boyutuna yeniden boyutlandırmak için çerçeveyi belirtir.

Bölme sabitlenmişse, bu yöntem hiçbir şey yapmaz.

## <a name="cbasetabbedpanesetautohidemode"></a><a name="setautohidemode"></a>CBaseTabbedPane::SetAutoHideMode

Sekmeli bölmedeki çıkarılabilir bölmeler için otomatik gizleme modunu ayarlar.

```
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,
    DWORD dwAlignment,
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,
    BOOL bUseTimer = TRUE);
```

### <a name="parameters"></a>Parametreler

*bMode*<br/>
[içinde] Otomatik gizleme modunu etkinleştirmek için TRUE; Normal yerleştirme modunu etkinleştirmek için FALSE.

*dwHizalama*<br/>
[içinde] Oluşturulacak otomatik gizleme bölmesinin hizalanmasını belirtir. Olası değerlerin listesi için [Bkz. CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment).

*pCurrAutoHideBar*<br/>
[içinde, dışarı] Geçerli otomatik gizleme araç çubuğuna işaretçi. NULL olabilir.

*bUseTimer*<br/>
[içinde] Kullanıcı bölmeyi otomatik gizleme moduna geçtiğinde otomatik gizleme efektini mi yoksa bölmeyi hemen gizlemeye mi kullanılacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Otomatik gizleme moduna geçerken oluşturulan otomatik gizleme araç çubuğuna işaretçi veya araç çubuğu oluşturulmazsa NULL.

### <a name="remarks"></a>Açıklamalar

Bir kullanıcı otomatik gizleme moduna veya normal yerleştirme moduna sekmeli bölmeyi değiştirmek için pin düğmesini seçtiğinde çerçeve bu yöntemi çağırır.

Otomatik gizleme modu, sekmeli bölmedeki her çıkarılabilir bölme için ayarlanır. Çıkarılamaz bölmeler yoksayılır. Daha fazla bilgi için [CMFCBaseTabCtrl::EnableTabDetach'](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach)a bakın.

Otomatik gizleme moduna sekmeli bölmeyi programlamak için değiştirmek için bu yöntemi arayın. Bölme ana çerçeve penceresine sabitlenmelidir ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) [CPaneDivider'a](../../mfc/reference/cpanedivider-class.md)geçerli bir işaretçi döndürmelidir).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)
