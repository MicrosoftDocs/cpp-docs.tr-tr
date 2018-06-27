---
title: CBaseTabbedPane sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edb9fe1942f9fe8b462ce9fc6a56e37538866174
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954994"
---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane sınıfı
İşlevselliğini genişleten [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md) sekmeli windows oluşturulmasını desteklemek için.  
  
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
|[CBaseTabbedPane::AddTab](#addtab)|Yeni bir sekme sekmeli bölmesine ekler.|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Boş bir sekmeli bölmesinde yok edilmesi belirtir.|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|Kayıt defterinden sekmeli bölmesine yüklenen Sekme ayarlarını uygular.|  
|[CBaseTabbedPane::CanFloat](#canfloat)|Bölmesinde kaydırabilirsiniz olup olmadığını belirler. (Geçersiz kılmaları [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Sekmeli bölmesi için resim yazısı aynı metin etkin sekme görüntülemek olup olmadığını belirler.|  
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(Geçersiz kılmaları [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|  
|[CBaseTabbedPane::DetachPane](#detachpane)|Bir veya daha fazla dockable bölmeleri MDI sekmeli belgelere dönüştürür.|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|Etkinleştirir veya sekmeli bölmesinde başlık metni etkin sekmede etiket metnini eşitlemek yeteneği devre dışı bırakır.|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|İç sekme sırası varsayılan durumuna geri yükler.|  
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|Sekme sıfır tabanlı sekmesini dizini tarafından tanımlandığında, bir sekmede bulunan bir bölme döndürür.|  
|||  
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|Bölmesinde kimliği ile tanımlanan bir bölme döndürür|  
|[CBaseTabbedPane::FloatTab](#floattab)|Bölmesinde şu anda çıkarılabilir bir sekmede bulunuyorsa ancak yalnızca bir bölme kayar.|  
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|Sekmelerin varsayılan düzenini bölmesinde döndürür.|  
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|İlk görüntülenen sekme için bir işaretçi alır.|  
|[CBaseTabbedPane::GetMinSize](#getminsize)|Bölmesinde boyutu izin verilen en düşük alır. (Geçersiz kılmaları [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|  
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|Bir tanıtıcı bölmesinde simgesini döndürür. (Geçersiz kılmaları [CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|  
|[CBaseTabbedPane::GetPaneList](#getpanelist)|Sekmeli bölmede bulunan bölmeleri listesini döndürür.|  
|[CBaseTabbedPane::GetTabArea](#gettabarea)|Üst ve alt sekme alanlar için sınırlayıcı dikdörtgenler döndürür.|  
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|Sekmeleri sayısını sekmesini penceresinde döndürür.|  
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|Temel alınan (Sarmalanan) sekmesi penceresi alır.|  
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|Görüntülenen sekmeler sayısını döndürür.|  
|[CBaseTabbedPane::HasAutoHideMode](#hasautohidemode)|Sekmeli bölmesinde otomatik olarak gizle moduna geçiş olup olmadığını belirler.|  
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|Bir sekmesinde görüntülenen yalnızca sekmeli bölmenin gizli olup olmadığını belirler.|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Seri hale getirme sırasında dahili olarak kullanılır.|  
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|Bölmesinin düzeni bilgileri yeniden hesaplar. (Geçersiz kılmaları [CPane::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|  
|[CBaseTabbedPane::RemovePane](#removepane)|Bir bölme sekmeli bölmesinden kaldırır.|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|Seri hale getirme sırasında dahili olarak kullanılır.|  
|`CBaseTabbedPane::Serialize`|(Geçersiz kılmaları [CDockablePane::Serialize](http://msdn.microsoft.com/en-us/09787e59-e446-4e76-894b-206d303dcfd6).)|  
|`CBaseTabbedPane::SerializeTabWindow`|Seri hale getirme sırasında dahili olarak kullanılır.|  
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|Sekmeli denetim çubuğu otomatik olarak yok olup olmadığını belirler.|  
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|Yerleştirme bölmesinde görüntülenen arasında geçiş yapar ve otomatik olarak gizle modu. (Geçersiz kılmaları [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|  
|[CBaseTabbedPane::ShowTab](#showtab)|Gösterir veya bir sekme gizler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir Özet sınıf ve örneği oluşturulamıyor. Sekmeli bölmeleri her türlü ortak Hizmetleri uygular.  
  
 Şu anda iki türetilmiş sekmeli bölmesinde sınıf kitaplığı içerir: [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md) ve [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 A `CBaseTabbedPane` nesne sarmalar gösteren bir işaretçi bir [CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md) nesnesi. [CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md) sekmeli bölmesinin alt pencere haline gelir.  
  
 Sekmeli panolar oluşturma hakkında daha fazla bilgi için bkz: [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md), [CTabbedPane sınıfı](../../mfc/reference/ctabbedpane-class.md), ve [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).  
  
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
 Yeni bir sekme sekmeli bölmesine ekler.  
  
```  
virtual BOOL AddTab(
    CWnd* pNewBar,  
    BOOL bVisible = TRUE,  
    BOOL bSetActive = TRUE,  
    BOOL bDetachable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *pNewBar*  
 Bir işaretçi bölmesine eklemek için. Bu yöntem çağırdıktan sonra bu işaretçinin geçersiz hale gelebilir. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 [in] *bVisible*  
 `TRUE` sekme görünür hale getirmek için; Aksi takdirde `FALSE`.  
  
 [in] *bSetActive*  
 `TRUE` etkin sekme sekmesini oluşturmak için; Aksi takdirde `FALSE`.  
  
 [in] *bDetachable*  
 `TRUE` Sekme çıkarılabilir yapmak için; Aksi takdirde `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde bir sekme başarıyla eklendi ve değildi işleminde yok. `FALSE` Eklenmekte olan bölmesinde bir nesne türü ise `CBaseTabbedPane`. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bölme sekmeli bölmesinde yeni bir sekmede olarak eklemek için bu yöntemi çağırın. Varsa *pNewBar* türünde bir nesneye işaret `CBaseTabbedPane`, tüm sekmeler sekmeli bölmesinden kopyalanır ve ardından *pNewBar* yok. Bu nedenle, *pNewBar* geçersiz bir işaretçi haline gelir ve kullanılmamalıdır.  
  
##  <a name="allowdestroyemptytabbedpane"></a>  CBaseTabbedPane::AllowDestroyEmptyTabbedPane  
 Boş bir sekmeli bölmesinde yok edilmesi belirtir.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` boş bir sekmeli bölmesinde yok Aksi takdirde `FALSE`. Varsayılan uygulama her zaman döndürür `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Boş bir sekmeli bölmesinde yok edilmesi için izin verilmiyorsa framework bölmesi yerine gizler.  
  
##  <a name="applyrestoredtabinfo"></a>  CBaseTabbedPane::ApplyRestoredTabInfo  
 Sekme ayarları kayıt defterinden yükler ve bunları sekmeli bölmesine uygular.  
  
```  
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bUseTabIndexes*  
 Bu parametre, framework tarafından dahili olarak kullanılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, takma durumu bilgilerini kayıt defterinden yüklediğinde çerçevesi tarafından çağrılır. Yöntemi, sekme sırasını ve sekmeli bölmesi için sekme adları hakkında bilgi edinir.  
  
##  <a name="canfloat"></a>  CBaseTabbedPane::CanFloat  
 Sekmeli bölmesinde kaydırabilirsiniz olup olmadığını belirtir.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde kaydırabilirsiniz; Aksi takdirde `FALSE`.  
  
##  <a name="cansetcaptiontexttotabname"></a>  CBaseTabbedPane::CanSetCaptionTextToTabName  
 Sekmeli bölmesi için resim yazısı aynı metin etkin sekme görüntülemek olup olmadığını belirler.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Sekmeli bölmesinin başlık metnini etkin sekme metne ayarlarsanız; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekmeli bölmesinde resim yazısı çoğaltmaların üzerinde etkin sekme etiketini görüntülenen metin olup olmadığını belirlemek için kullanılan yöntem. Etkinleştirmek veya çağırarak bu işlevi devre dışı [CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname).  
  
##  <a name="converttotabbeddocument"></a>  CBaseTabbedPane::ConvertToTabbedDocument  
 Bir veya daha fazla dockable bölmeleri MDI sekmeli belgelere dönüştürür.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bActiveTabOnly*  
 Sekmeli bölmesinde dönüştürürken belirtin `TRUE` yalnızca etkin sekme dönüştürülemiyor. Belirtin `FALSE` bölmesinde tüm sekmeler dönüştürülemiyor.  
  
##  <a name="detachpane"></a>  CBaseTabbedPane::DetachPane  
 Sekmeli bölmesinde bölmesinden ayırır.  
  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 İşaretçi bölmesine ayrılmadı.  
  
 [in] *bHide*  
 Ayrılmış sonra framework bölmesini gizler olup olmadığını belirten Boolean parametresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` framework başarıyla bölmesinde ayırır `FALSE` varsa *pBar* olan `NULL` veya sekmeli bölmede değil bölmesine başvuruyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework ayrılmış bölmesinde mümkünse kayar. Daha fazla bilgi için bkz: [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).  
  
##  <a name="enablesetcaptiontexttotabname"></a>  CBaseTabbedPane::EnableSetCaptionTextToTabName  
 Etkinleştirir veya sekmeli bölmesinde başlık metni etkin sekmede etiket metnini eşitlemek yeteneği devre dışı bırakır.  
  
```  
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 `TRUE` Sekmeli Bölmesi Başlığı etkin sekme resim yazısı ile eşitlemek için; Aksi takdirde `FALSE`.  
  
##  <a name="filldefaulttabsorderarray"></a>  CBaseTabbedPane::FillDefaultTabsOrderArray  
 İç sekme sırası varsayılan durumuna geri yükler.  
  
```  
void FillDefaultTabsOrderArray();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve bir Outlook Çubuğu ilk durumuna geri yüklerken bu yöntem çağrılır.  
  
##  <a name="findpanebyid"></a>  CBaseTabbedPane::FindPaneByID  
 Bölmesinde kimliği ile tanımlanan bir bölme döndürür  
  
```  
virtual CWnd* FindPaneByID(UINT uBarID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uBarID*  
 Bulunacak bölmesinde Kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi onu bulunduysa bölmesine; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bölmesinde tüm sekmeler karşılaştırır ve tarafından belirtilen Kimliğe sahip bir döndürür *uBarID* parametresi.  
  
##  <a name="findbarbytabnumber"></a>  CBaseTabbedPane::FindBarByTabNumber  
 Bir sekmede bulunduğu bir bölme döndürür.  
  
```  
virtual CWnd* FindBarByTabNumber(
    int nTabNum,  
    BOOL bGetWrappedBar = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nTabNum*  
 Almak üzere sekmesini sıfır tabanlı dizini belirtir.  
  
 [in] *bGetWrappedBar*  
 `TRUE` temel alınan (Sarmalanan) pencereyi bölmesinde yerine bölmesinin döndürmek için; Aksi takdirde `FALSE`. Bu yalnızca türetilmiş bölmeleri geçerlidir [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölmesinde bulunursa, geçerli bir işaretçi Aranan bölmesine verilir; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirtilen sekmesinde bulunan bölmesinde almak için bu yöntemi çağırın *nTabNum* parametresi.  
  
##  <a name="floattab"></a>  CBaseTabbedPane::FloatTab  
 Bölmesinde şu anda çıkarılabilir bir sekmede bulunuyorsa ancak yalnızca bir bölme kayar.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *pBar*  
 Float bölmesine bir işaretçi.  
  
 [in] *nTabID*  
 Float sekmesine sıfır tabanlı dizini belirtir.  
  
 [in] *dockMethod*  
 Bölmesinde yüzer duruma getirmek için kullanılacak yöntemi belirtir. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 [in] *bHide*  
 `TRUE` Kayan önce bölmesini gizlemek için; Aksi takdirde `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde kaydırılmış Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çıkarılabilir bir sekmede şu anda bulunduğu bir bölme float için bu yöntemi çağırın.  
  
 Bir bölme program aracılığıyla ayırmak istiyorsanız, belirtin `DM_SHOW` için *dockMethod* parametresi. Burada, kaydırılmış daha önce aynı konumda bölmesinde float istiyorsanız belirtin `DM_DBL_CLICK` olarak *dockMethod* parametresi.  
  
##  <a name="getdefaulttabsorder"></a>  CBaseTabbedPane::GetDefaultTabsOrder  
 Sekmelerin varsayılan düzenini bölmesinde döndürür.  
  
```  
const CArray<int,int>& GetDefaultTabsOrder();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CArray` bölmesinde sekmeleri varsayılan sırasını belirtir nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir Outlook Çubuğu ilk durumuna sıfırladığınızda framework bu yöntemi çağırır.  
  
##  <a name="getfirstvisibletab"></a>  CBaseTabbedPane::GetFirstVisibleTab  
 İlk görüntülenen sekme için bir işaretçi alır.  
  
```  
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iTabNum*  
 Tamsayı referansı. Bu yöntem ilk görüntülenen sekmeyi sıfır tabanlı dizini bu parametresi veya -1 görüntülenen Hayır ise sekmesinde bulunan yazar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, ilk görüntülenen sekmeyi için; bir işaretçi Aksi takdirde `NULL`.  
  
##  <a name="getminsize"></a>  CBaseTabbedPane::GetMinSize  
 Bölmesinde boyutu izin verilen en düşük alır.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *boyutu*  
 A `CSize` boyutu izin verilen en düşük girilir nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Minimum bölmesinde boyutları tutarlı işlenmesini etkinse ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *boyutu* etkin sekme boyutu izin verilen en düşük ile doldurulur. Aksi takdirde, *boyutu* dönüş değeri ile doldurulur [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpaneicon"></a>  CBaseTabbedPane::GetPaneIcon  
 Bölmesinde boyutu izin verilen en düşük alır.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *boyutu*  
 A `CSize` boyutu izin verilen en düşük girilir nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Minimum bölmesinde boyutları tutarlı işlenmesini etkinse ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *boyutu* etkin sekme boyutu izin verilen en düşük ile doldurulur. Aksi takdirde, *boyutu* dönüş değeri ile doldurulur [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpanelist"></a>  CBaseTabbedPane::GetPaneList  
 Sekmeli bölmede bulunan bölmeleri listesini döndürür.  
  
```  
virtual void GetPaneList(
    CObList& lst,  
    CRuntimeClass* pRTCFilter = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *lst*  
 A `CObList` sekmeli bölmede bulunan bölmeleri ile doldurulur.  
  
 [in] *pRTCFilter*  
 Değilse `NULL`, döndürülen liste belirtilen çalışma zamanı sınıfı olan bölme içerir.  
  
##  <a name="gettabarea"></a>  CBaseTabbedPane::GetTabArea  
 Üst ve alt sekme alanlar için sınırlayıcı dikdörtgenler döndürür.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *rectTabAreaTop*  
 Ekran koordinatları üst sekme alanı alır.  
  
 [out] *rectTabAreaBottom*  
 Ekran koordinatları alt sekme alanı alır.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınırlayıcı dikdörtgenler üst ve alt sekme alanlar için ekran koordinatları belirlemek için bu yöntemi çağırın.  
  
##  <a name="gettabsnum"></a>  CBaseTabbedPane::GetTabsNum  
 Sekmeleri sayısını sekmesini penceresinde döndürür.  
  
```  
virtual int GetTabsNum() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sekmeli bölmedeki sekmeleri sayısı.  
  
##  <a name="getunderlyingwindow"></a>  CBaseTabbedPane::GetUnderlyingWindow  
 Temel alınan (Sarmalanan) sekmesi penceresi alır.  
  
```  
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel alınan sekmesi penceresi için bir işaretçi.  
  
##  <a name="getvisibletabsnum"></a>  CBaseTabbedPane::GetVisibleTabsNum  
 Görünür sekmeleri sayısını döndürür.  
  
```  
virtual int GetVisibleTabsNum() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Büyük veya sıfıra eşit olacak görünür sekme sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Sekmeli bölmesinde görünür sekmeleri sayısını belirlemek için bu yöntemi çağırın.  
  
##  <a name="hasautohidemode"></a>  CBaseTabbedPane::HasAutoHideMode  
 Sekmeli bölmesinde autohide moduna geçiş olup olmadığını belirler.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde autohide moduna Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 AutoHide modu devre dışı bırakılırsa, PIN düğmesi sekmeli bölmesinde resim yazısını görüntülenir.  
  
##  <a name="ishidesingletab"></a>  CBaseTabbedPane::IsHideSingleTab  
 Bir sekmesinde görüntülenen yalnızca sekmeli bölmenin gizli olup olmadığını belirler.  
  
```  
virtual BOOL IsHideSingleTab() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` tek bir görünür sekme olduğunda sekmesi penceresi görüntülenmiyorsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Tek bir sekme açık olduğundan bölmesinde görüntülenmiyorsa sekmeli bölmesinde doğru şekilde çalışıp çalışmadığını belirlemek için bu yöntemi çağırabilirsiniz.  
  
##  <a name="removepane"></a>  CBaseTabbedPane::RemovePane  
 Bir bölme sekmeli bölmesinden kaldırır.  
  
```  
virtual BOOL RemovePane(CWnd* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] *pBar*  
 Sekmeli bölmesinden kaldırmak için bölmesinde bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde sekmeli bölmesinden başarıyla kaldırıldıysa ve sekmeli bölmesinde hala geçerli ise. `FALSE` Son bölmesinde sekmeli bölmesinden kaldırıldı ve yaklaşık yok edilmesi için sekmeli bölmesinde ise. Dönüş değeri ise `FALSE`, sekmeli bölmesi artık kullanmayın.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirtilen bölmesinde kaldırmak için bu yöntemi çağırın *pBar* sekmeli bölmesinden parametresi.  
  
##  <a name="setautodestroy"></a>  CBaseTabbedPane::SetAutoDestroy  
 Sekmeli denetim çubuğu otomatik olarak yok olup olmadığını belirler.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bAutoDestroy*  
 `TRUE` Sekmeli bölmesinde dinamik olarak oluşturulmuş ve yaşam süresi denetleme değil Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama modu için otomatik olarak ortadan `TRUE` sekmeli bölmesinde dinamik olarak oluşturursanız ve yaşam süresi denetleme değil. Varsa otomatik destroy modu `TRUE`, sekmeli bölmesinde otomatik olarak çerçevesi tarafından yok olacaktır.  
  
##  <a name="showtab"></a>  CBaseTabbedPane::ShowTab  
 Gösterir veya bir sekme gizler.  
  
```  
virtual BOOL ShowTab(
    CWnd* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 Bir işaretçi göstermek veya gizlemek için bölmesine.  
  
 [in] *bBilgi Göster*  
 `TRUE` bölmesini göstermek için; `FALSE` bölmesini gizlemek için.  
  
 [in] *bDelay*  
 `TRUE` sekme düzenini ayarlama geciktirmek için; Aksi takdirde `FALSE`.  
  
 [in] *bActivate*  
 `TRUE` etkin sekme sekmesini oluşturmak için; Aksi takdirde `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` sekmesinde gösterilen veya başarıyla; gizli değilse Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırdığınızda, bir bölme gösterilen veya gizli, bağlı olarak değeri *bBilgi Göster* parametresi. Sekme gizleme ve temel sekmesini penceresindeki Son görünür sekmesi ise, sekmeli bölmesi gizlenir. Vardı, daha önce hiç sekmeleri görünür bir sekme gösterirse, sekmeli bölmesinde gösterilir.  
  
##  <a name="recalclayout"></a>  CBaseTabbedPane::RecalcLayout  
 Bölmesinin düzeni bilgileri yeniden hesaplar.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bölmesinde kayan açtıysanız, bu yöntem kısa çerçeve geçerli boyutunu bölmesini yeniden boyutlandırmak için framework bildirir.  
  
 Bölmenin yerleştirilmiş olup, bu yöntem hiçbir şey yapmaz.  
  
##  <a name="setautohidemode"></a>  CBaseTabbedPane::SetAutoHideMode  
 Çıkarılabilir bölmeleri için otomatik olarak gizle modu sekmeli bölmede ayarlar.  
  
```  
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bMode*  
 `TRUE` otomatik olarak Gizle modunu etkinleştirmek için; `FALSE` normal takma modunu etkinleştirmek için.  
  
 [in] *dwAlignment*  
 Oluşturulacak otomatik gizleme bölmesinde hizalamasını belirtir. Olası değerler listesi için bkz: [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment).  
  
 [in] [out] *pCurrAutoHideBar*  
 Geçerli otomatik olarak gizle Araç için bir işaretçi. Olabilir `NULL`.  
  
 [in] *bUseTimer*  
 Kullanıcı bölmesinde otomatik olarak gizle moduna geçtiğinde otomatik olarak gizle etkisi kullanın ya da bölmesini hemen gizlemek için belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Otomatik olarak gizle moduna geçerken oluşturulan otomatik olarak gizle Araç için bir işaretçi veya `NULL` hiçbir araç oluşturulur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı sekmeli bölmesinde otomatik olarak gizle modu veya normal takma moduna geçiş için PIN düğmesini seçtiğinde framework bu yöntemi çağırır.  
  
 Sekmeli bölmesinde çıkarılabilir her bölme için otomatik olarak Gizle modunu ayarlayın. Çıkarılabilir olmayan bölmeleri göz ardı edilir. Daha fazla bilgi için bkz: [CMFCBaseTabCtrl::EnableTabDetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach).  
  
 Sekmeli bölmesinde program aracılığıyla otomatik olarak gizle moduna geçmek için bu yöntemi çağırın. Bölmesi ana çerçeve penceresi yuvalanmış gerekir ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) için geçerli bir işaretçi döndürmelidir [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)
