---
title: CMFCShellTreeTreeCtrl Sınıfı
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
ms.openlocfilehash: c6f5856e92c2aca1d23ee6a37b99ea9700ea6db0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753448"
---
# <a name="cmfcshelltreectrl-class"></a>CMFCShellTreeTreeCtrl Sınıfı

Sınıf, `CMFCShellTreeCtrl` Shell öğelerinin bir hiyerarşisini görüntüleyerek [CTreeCtrl Sınıfı](../../mfc/reference/ctreectrl-class.md) işlevselliğini genişletir.

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCShellTreeCtrl : public CTreeCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCShellTreeTreeCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Kısayol menüsünü etkinleştirer veya devre dışı kılabilir.|
|[CMFCShellTreeCtrl::GetFlags](#getflags)|IShellFolder'a geçirilen bayrakların birleşimini [döndürür::EnumObjects.](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)|
|[CMFCShellTreeTreeCtrl::GetItemPath](#getitempath)|Bir öğeye giden yolu alır.|
|[CMFCShellTreeTreeCtrl::GetRelatedList](#getrelatedlist)|Explorer benzeri bir pencere oluşturmak için bu `CMFCShellTreeCtrl` nesneyle birlikte kullanılan [CMFCShellListCtrl Sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesine bir işaretçiyi döndürür.|
|[CMFCShellTreeTreeCtrl::OnChildNotify](#onchildnotify)|Bu altöğe işlev, bu pencere için geçerli bir bildirim iletisi aldığında bu pencerenin üst penceresi tarafından çağrılır. (CWnd geçersiz [kılar::OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify).)|
|[CMFCShellTreeTreeCtrl::OnGetItemIcon](#ongetitemicon)||
|[CMFCShellTreeTreeCtrl::OnGetItemText](#ongetitemtext)||
|[CMFCShellTreeTreeCtrl::Yenile](#refresh)|Geçerli `CMFCShellTreeCtrl` nesneyi yeniler ve yeniden boyar.|
|[CMFCShellTreeTreeCtrl::SelectPath](#selectpath)|Verilen PIDL veya dize yoluna göre uygun ağaç denetim öğesini seçer.|
|[CMFCShellTreeCtrl::SetFlags](#setflags)|Ağaç bağlamını filtrelemek için bayraklar ayarlar `IShellFolder::EnumObjects`(kullanılan bayraklara benzer).|
|[CMFCShellTreeTreeCtrl::SetRelatedList](#setrelatedlist)|Geçerli `CMFCShellTreeCtrl` nesne ve nesne arasında `CMFCShellListCtrl` bir ilişki ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, `CTreeCtrl` programınızın Windows Shell öğelerini ağaca eklemesini sağlayarak sınıfı genişletir. Bu sınıf, tam `CMFCShellListCtrl` bir Explorer penceresi oluşturmak için bir nesne ile ilişkili olabilir. Ardından, ağaçtaki bir öğeyi seçmek, ilişkili listede Windows Shell öğelerinin bir listesini görüntüler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxshelltreeCtrl.h

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCShellTreeCtrl` nasıl oluşturulacak olduğunu gösterir. Bu kod parçacığı [Explorer örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

## <a name="cmfcshelltreectrlenableshellcontextmenu"></a><a name="enableshellcontextmenu"></a>CMFCShellTreeTreeCtrl::EnableShellContextMenu

Kısayol menüsünü etkinleştiri.

```cpp
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Kısayol menüsünü etkinleştirip etkinleştirmeyeceğini belirten bir Boolean.

## <a name="cmfcshelltreectrlgetflags"></a><a name="getflags"></a>CMFCShellTreeCtrl::GetFlags

[CMFCShellTreeCtrl Sınıf](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesi için ayarlanan bayrakları döndürür.

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda ayarlanan bayrakların birleşimini belirten bir DWORD değeri.

### <a name="remarks"></a>Açıklamalar

Ayarlanan `CMFCShellTreeCtrl` bayraklar IShellFolder yöntemine [gönderilir::Nesne yenilendiğinde EnumObjects.](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) [CMFCShellTreeCtrl::SetFlags](#setflags) yöntemiyle bayrakları değiştirebilirsiniz.

## <a name="cmfcshelltreectrlgetitempath"></a><a name="getitempath"></a>CMFCShellTreeTreeCtrl::GetItemPath

[CMFCShellTreeCtrl Sınıf](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesindeki bir öğenin yolunu alır.

```
BOOL GetItemPath(
    CString& strPath,
    HTREEITEM htreeItem = NULL) const;
```

### <a name="parameters"></a>Parametreler

*strPath*<br/>
[çıkış] Dize parametresine başvuru. Yöntem, maddenin yolunu bu parametreye yazar.

*htreeItem*<br/>
[içinde] Yöntem, bu ağaç denetim öğesi için yolu alır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; 0 aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu yöntem başarısız olursa, *strPath* boş dize içerir.

*hTreeItem*belirtmezseniz, bu yöntem şu anda seçili öğe için dize elde etmeye çalışır. Hiçbir öğe seçili değilse ve *hTreeItem* NULL ise, bu yöntem başarısız olur.

## <a name="cmfcshelltreectrlgetrelatedlist"></a><a name="getrelatedlist"></a>CMFCShellTreeTreeCtrl::GetRelatedList

Bu [CMFCShellTreeTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesi ile ilişkili [CMFCShellListCtrl Sınıf](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesine bir işaretçi döndürür.

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu ağaç `CMFCShellListCtrl` denetim nesnesi ile ilişkili nesneye bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCShellListCtrl` nesneyi nesneyle `CMFCShellTreeCtrl` birlikte kullanarak Explorer benzeri bir pencere oluşturabilirsiniz. [CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist) yöntemini kullanarak iki sınıfı ilişkilendirin. Bunlar ilişkilendirildikten sonra, çerçeve `CMFCShellListCtrl` `CMFCShellTreeCtrl` değişikliklerdeki eğer seçimini otomatik olarak güncelleştirir.

## <a name="cmfcshelltreectrlonchildnotify"></a><a name="onchildnotify"></a>CMFCShellTreeTreeCtrl::OnChildNotify

```
virtual BOOL OnChildNotify(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* pLResult);
```

### <a name="parameters"></a>Parametreler

[içinde] *mesaj*<br/>
[içinde] *wParam*<br/>
[içinde] *lParam*<br/>
[içinde] *pLResult*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcshelltreectrlongetitemicon"></a><a name="ongetitemicon"></a>CMFCShellTreeTreeCtrl::OnGetItemIcon

```
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,
    BOOL bSelected);
```

### <a name="parameters"></a>Parametreler

[içinde] *pItem*<br/>
[içinde] *bSelected*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcshelltreectrlongetitemtext"></a><a name="ongetitemtext"></a>CMFCShellTreeTreeCtrl::OnGetItemText

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parametreler

[içinde] *pItem*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcshelltreectrlrefresh"></a><a name="refresh"></a>CMFCShellTreeTreeCtrl::Yenile

[CMFCShellTreeCtrl'i](../../mfc/reference/cmfcshelltreectrl-class.md)yeniler ve yeniden boyar.

```cpp
void Refresh();
```

### <a name="remarks"></a>Açıklamalar

'de görüntülenen öğelerin hiyerarşisini yenilemek `CMFCShellTreeCtrl`için bu yöntemi çağırın.

## <a name="cmfcshelltreectrlselectpath"></a><a name="selectpath"></a>CMFCShellTreeTreeCtrl::SelectPath

[CMFCShellTreeCtrl Sınıfında](../../mfc/reference/cmfcshelltreectrl-class.md) verilen yolu temel alan bir öğe seçer.

```
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
[içinde] Bir öğenin yolunu belirten bir dize.

*lpidl*<br/>
[içinde] Öğeyi belirten bir PIDL

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; E_FAIL otherwise.

## <a name="cmfcshelltreectrlsetflags"></a><a name="setflags"></a>CMFCShellTreeCtrl::SetFlags

Ağaç bağlamını filtrelemek için bayraklar ayarlar.

```cpp
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
[içinde] Ayarlanan bayraklar.

*bYenil*<br/>
[içinde] Bir Boolean bu hemen `CMFCShellTreeCtrl` yenilenmesi gerektiğini belirtir.

### <a name="remarks"></a>Açıklamalar

Tüm `CMFCShellTreeCtrl` ayarbayrakları [IShellFolder'a geçer::EnumObjects.](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) Farklı bayrakların değerleri hakkında daha fazla bilgi için [Bkz. IShellFolder::EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects).

## <a name="cmfcshelltreectrlsetrelatedlist"></a><a name="setrelatedlist"></a>CMFCShellTreeTreeCtrl::SetRelatedList

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi [cmfcShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesi ile ilişkilendirin.

```cpp
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>Parametreler

*pShellList*<br/>
[içinde] Bir `CMFCShellListCtrl` nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `CMFCShellListCtrl` bir `CMFCShellTreeCtrl`ile ilişkilendiren bir . Bu nesneler Explorer benzeri bir pencere olarak görüntülenebilir: kullanıcı bir `CMFCShellTreeCtrl`nesne seçerse, `CMFCShellListCtrl` ilgili öğeler otomatik olarak güncelleştirilir.

[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist) yöntemini kullanarak `CMFCShellListCtrl` ilişkili bir `CMFCShellTreeCtrl`.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CTreeCtrl Sınıfı](../../mfc/reference/ctreectrl-class.md)<br/>
[CMFCShellListCtrl Sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md)
