---
title: CMFCShellTreeCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::EnableShellContextMenu
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetItemPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetRelatedList
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnChildNotify
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemIcon
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemText
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::Refresh
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SelectPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetRelatedList
helpviewer_keywords:
- CMFCShellTreeCtrl [MFC], EnableShellContextMenu
- CMFCShellTreeCtrl [MFC], GetFlags
- CMFCShellTreeCtrl [MFC], GetItemPath
- CMFCShellTreeCtrl [MFC], GetRelatedList
- CMFCShellTreeCtrl [MFC], OnChildNotify
- CMFCShellTreeCtrl [MFC], OnGetItemIcon
- CMFCShellTreeCtrl [MFC], OnGetItemText
- CMFCShellTreeCtrl [MFC], Refresh
- CMFCShellTreeCtrl [MFC], SelectPath
- CMFCShellTreeCtrl [MFC], SetFlags
- CMFCShellTreeCtrl [MFC], SetRelatedList
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
ms.openlocfilehash: 1fc422c3aca3efe1fb177e7a3567530d70c27119
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58779761"
---
# <a name="cmfcshelltreectrl-class"></a>CMFCShellTreeCtrl sınıfı

`CMFCShellTreeCtrl` Sınıfını genişleten [CTreeCtrl sınıfı](../../mfc/reference/ctreectrl-class.md) Kabuk öğeleri hiyerarşisini görüntüleyerek işlevselliği.

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.
## <a name="syntax"></a>Sözdizimi

```
class CMFCShellTreeCtrl : public CTreeCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCShellTreeCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Etkinleştirir veya kısayol menüsünden devre dışı bırakır.|
|[CMFCShellTreeCtrl::GetFlags](#getflags)|Geçirilen bayrakların birleşimi döndürür [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects).|
|[CMFCShellTreeCtrl::GetItemPath](#getitempath)|Bir öğenin yolunu alır.|
|[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)|Bir işaretçi döndürür [CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) bu ile birlikte kullanılan nesne `CMFCShellTreeCtrl` Gezgin benzeri pencere oluşturmak için nesne.|
|[CMFCShellTreeCtrl::OnChildNotify](#onchildnotify)|Bu pencere için geçerli bir bildirim iletisi aldığında, bu üye işlevi bu pencerenin ana pencere tarafından çağırılır. (Geçersiz kılmaları [CWnd::OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify).)|
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||
|[CMFCShellTreeCtrl::Refresh](#refresh)|Yenilenir ve geçerli halinde yeniden boyar `CMFCShellTreeCtrl` nesne.|
|[CMFCShellTreeCtrl::SelectPath](#selectpath)|Sağlanan PIDL işaretçisiyle birlikte veya dize yolu göre uygun ağaç denetim öğesi seçer.|
|[CMFCShellTreeCtrl::SetFlags](#setflags)|Bayrakları Ağacı Bağlam filtrelemek için ayarlar (tarafından kullanılan bayraklar benzer `IShellFolder::EnumObjects`).|
|[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)|Geçerli arasında bir ilişki ayarlar `CMFCShellTreeCtrl` nesnesi ve bir `CMFCShellListCtrl` nesne.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf genişletir `CTreeCtrl` programınızı ağacında Windows Kabuk öğeleri içerecek şekilde etkinleştirerek sınıfı. Bu sınıf ile ilişkili bir `CMFCShellListCtrl` eksiksiz bir Gezgini penceresi oluşturulacak nesne. Ardından, ilişkili listesinde ağaçta bir öğenin seçilmesi Windows Kabuk öğeleri listesi görüntülenir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxshelltreeCtrl.h

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnenin oluşturulacağı gösterilmektedir `CMFCShellTreeCtrl` sınıfı. Bu kod parçacığı parçasıdır [Gezgini örneği](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

##  <a name="enableshellcontextmenu"></a>  CMFCShellTreeCtrl::EnableShellContextMenu

Kısayol menüsünü etkinleştirir.

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Kısayol menüsünün etkinleştirilip etkinleştirilmeyeceğini belirleyen bir Boole değeri.

##  <a name="getflags"></a>  CMFCShellTreeCtrl::GetFlags

İçin ayarlanan işaretlere döndürür [CMFCShellTreeCtrl sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md) nesne.

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda bayrakların birleşimi belirten bir DWORD değeri ayarlayın.

### <a name="remarks"></a>Açıklamalar

Bayrakları kümesinde `CMFCShellTreeCtrl` yöntemine gönderilen [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) her nesne yenilenir. Bayraklarıyla değiştirebilirsiniz [CMFCShellTreeCtrl::SetFlags](#setflags) yöntemi.

##  <a name="getitempath"></a>  CMFCShellTreeCtrl::GetItemPath

Bir öğenin yolunu alır [CMFCShellTreeCtrl sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md) nesne.

```
BOOL GetItemPath(
    CString& strPath,
    HTREEITEM htreeItem = NULL) const;
```

### <a name="parameters"></a>Parametreler

*strPath*<br/>
[out] Bir dize parametresi bir başvuru. Yöntemi, bu parametre için öğenin yolu yazar.

*htreeItem*<br/>
[in] Yöntemi, bu ağaç denetim öğesi yolunu alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem başarısız olursa *strPath* boş bir dize içeriyor.

Siz belirtmezseniz *hTreeItem*, bu yöntem, geçerli seçilmiş öğe için dize almayı dener. Hiçbir öğe seçili değilse ve *hTreeItem* NULL ise bu yöntem başarısız olur.

##  <a name="getrelatedlist"></a>  CMFCShellTreeCtrl::GetRelatedList

Bir işaretçi döndürür [CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) bununla ilişkili nesne [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) nesne.

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `CMFCShellListCtrl` bu ağaç denetimi nesnesiyle ilişkili nesne.

### <a name="remarks"></a>Açıklamalar

Kullanarak bir `CMFCShellListCtrl` nesnesi ile birlikte bir `CMFCShellTreeCtrl` nesnesi bir Gezgin benzeri pencere oluşturabilirsiniz. Bu yöntemi kullanmak [CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist) iki sınıf ilişkilendirilecek. İlişkili oldukları sonra framework otomatik olarak güncelleştirir `CMFCShellListCtrl` , seçimdeki `CMFCShellTreeCtrl` değişiklikler.

##  <a name="onchildnotify"></a>  CMFCShellTreeCtrl::OnChildNotify

```
virtual BOOL OnChildNotify(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* pLResult);
```

### <a name="parameters"></a>Parametreler

[in] *iletisi*<br/>
[in] *wParam*<br/>
[in] *lParam*<br/>
[in] *pLResult*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="ongetitemicon"></a>  CMFCShellTreeCtrl::OnGetItemIcon

```
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,
    BOOL bSelected);
```

### <a name="parameters"></a>Parametreler

[in] *pItem*<br/>
[in] *bSelected*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="ongetitemtext"></a>  CMFCShellTreeCtrl::OnGetItemText

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parametreler

[in] *pItem*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="refresh"></a>  CMFCShellTreeCtrl::Refresh

Yenilenir ve halinde yeniden boyar [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md).

```
void Refresh();
```

### <a name="remarks"></a>Açıklamalar

Görüntülenen öğelerin hiyerarşisini yenilemek için bu yöntemi çağırın `CMFCShellTreeCtrl`.

##  <a name="selectpath"></a>  CMFCShellTreeCtrl::SelectPath

Bir öğeyi seçer [CMFCShellTreeCtrl sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md) sağlanan yola göre.

```
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
[in] Bir öğenin konumunu belirten bir dize.

*lpidl*<br/>
[in] Öğeyi belirten bir PIDL işaretçisiyle birlikte

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; E_FAIL Aksi takdirde.

##  <a name="setflags"></a>  CMFCShellTreeCtrl::SetFlags

Ağacı Bağlam filtrelemek için bayraklarını ayarlar.

```
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>Parametreler

*CertOpenStore*<br/>
[in] Ayarlanacak bayraklar.

*bRefresh*<br/>
[in] Belirten Boolean bir değer olup olmadığını `CMFCShellTreeCtrl` hemen yenilenmesi.

### <a name="remarks"></a>Açıklamalar

`CMFCShellTreeCtrl` Tüm kümesine bayrakları geçişleri [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects). Farklı bayrakları değerler hakkında daha fazla bilgi için bkz. [IShellFolder::EnumObjects](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects).

##  <a name="setrelatedlist"></a>  CMFCShellTreeCtrl::SetRelatedList

İlişkilendirir bir [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi ile bir [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) nesne.

```
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>Parametreler

*pShellList*<br/>
[in] Bir işaretçi bir `CMFCShellListCtrl` nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ilişkilendirir bir `CMFCShellListCtrl` ile bir `CMFCShellTreeCtrl`. Bu nesneleri bir Gezgin benzeri penceresi olarak görüntülenebilir: kullanıcı, nesneyi seçerse `CMFCShellTreeCtrl`, ilişkili öğeleri de `CMFCShellListCtrl` otomatik olarak güncelleştirilir.

Bu yöntemi kullanmak [CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist) alınacak `CMFCShellListCtrl` ile ilişkili bir `CMFCShellTreeCtrl`.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CTreeCtrl Sınıfı](../../mfc/reference/ctreectrl-class.md)<br/>
[CMFCShellListCtrl Sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md)
