---
description: 'Daha fazla bilgi edinin: Cmfcshelltreeci sınıfı'
title: Cmfcshelltreeci sınıfı
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
ms.openlocfilehash: 86b18d1cb919eaa36c3aed0d6e1623bab530a0aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339676"
---
# <a name="cmfcshelltreectrl-class"></a>Cmfcshelltreeci sınıfı

`CMFCShellTreeCtrl`Sınıfı, kabuk öğelerinin hiyerarşisini görüntüleyerek [Ctreecu sınıfı](../../mfc/reference/ctreectrl-class.md) işlevselliğini genişletir.

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMFCShellTreeCtrl : public CTreeCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcshelltreeci:: EnableShellContextMenu](#enableshellcontextmenu)|Kısayol menüsünü etkinleştirilir veya devre dışı bırakır.|
|[Cmfcshelltreeci:: GetFlags](#getflags)|[IShellFolder:: EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)'e geçirilen bayrakların birleşimini döndürür.|
|[Cmfcshelltreecl:: Getıtempgunlum](#getitempath)|Bir öğenin yolunu alır.|
|[Cmfcshelltreeci:: GetRelatedList](#getrelatedlist)|Gezgin benzeri bir pencere oluşturmak için bu nesneyle birlikte kullanılan [CMFCShellListCtrl sınıf](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesine bir işaretçi döndürür `CMFCShellTreeCtrl` .|
|[Cmfcshelltreecfy:: Onchildnotıfy](#onchildnotify)|Bu üye işlevi, bu pencere için geçerli olan bir bildirim iletisi aldığında bu pencerenin üst penceresi tarafından çağırılır. ( [CWnd:: OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify)geçersiz kılar.)|
|[Cmfcshelltreect:: OnGetItemIcon](#ongetitemicon)||
|[Cmfcshelltreecy:: Ongetıtemtext](#ongetitemtext)||
|[Cmfcshelltreeci:: Refresh](#refresh)|Geçerli nesneyi yeniler ve yeniden boyar `CMFCShellTreeCtrl` .|
|[Cmfcshelltreeci:: SelectPath](#selectpath)|Sağlanan PIDL veya dize yolunu temel alarak uygun ağaç denetim öğesini seçer.|
|[Cmfcshelltreeci:: SetFlags](#setflags)|Ağaç bağlamını filtrelemek için bayrakları ayarlar (tarafından kullanılan bayraklara benzer `IShellFolder::EnumObjects` ).|
|[Cmfcshelltreeci:: SetRelatedList](#setrelatedlist)|Geçerli nesne ile nesne arasında bir ilişki ayarlar `CMFCShellTreeCtrl` `CMFCShellListCtrl` .|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, `CTreeCtrl` programınızı ağaca Windows Shell öğelerini dahil etmek üzere etkinleştirerek sınıfını genişletir. Bu sınıf, `CMFCShellListCtrl` Tüm Gezgin penceresi oluşturmak için bir nesneyle ilişkilendirilebilir. Daha sonra ağaçta bir öğenin seçilmesi, ilişkili listedeki Windows kabuğu öğelerinin bir listesini görüntüler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxshelltreecm. h

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulacağını gösterir `CMFCShellTreeCtrl` . Bu kod parçacığı, [Gezgin örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

## <a name="cmfcshelltreectrlenableshellcontextmenu"></a><a name="enableshellcontextmenu"></a> Cmfcshelltreeci:: EnableShellContextMenu

Kısayol menüsünü etkinleştirilir.

```cpp
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Kısayol menüsünün etkinleştirilip etkinleştirilmeyeceğini belirten bir Boole değeri.

## <a name="cmfcshelltreectrlgetflags"></a><a name="getflags"></a> Cmfcshelltreeci:: GetFlags

[Cmfcshelltreecind Class](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesi için ayarlanan bayrakları döndürür.

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda ayarlanmış olan bayrakların birleşimini belirten bir DWORD değeri.

### <a name="remarks"></a>Açıklamalar

İçinde ayarlanan bayraklar, `CMFCShellTreeCtrl` nesne yenilendiğinde [IShellFolder:: EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) yöntemine gönderilir. Bayrakları [Cmfcshelltreec,:: SetFlags](#setflags) yöntemiyle değiştirebilirsiniz.

## <a name="cmfcshelltreectrlgetitempath"></a><a name="getitempath"></a> Cmfcshelltreecl:: Getıtempgunlum

[Cmfcshelltreecft sınıf](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesindeki bir öğenin yolunu alır.

```
BOOL GetItemPath(
    CString& strPath,
    HTREEITEM htreeItem = NULL) const;
```

### <a name="parameters"></a>Parametreler

*strPath*<br/>
dışı Dize parametresine bir başvuru. Yöntemi öğenin yolunu bu parametreye yazar.

*htreeItem*<br/>
'ndaki Yöntemi bu ağaç denetimi öğesinin yolunu alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; 0 Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu yöntem başarısız olursa, *strPath* boş dizeyi içerir.

*Htreeitem* belirtmezseniz, bu yöntem seçili olan öğe için dizeyi almaya çalışır. Hiçbir öğe seçilmezse ve *Htreeitem* null ise, bu yöntem başarısız olur.

## <a name="cmfcshelltreectrlgetrelatedlist"></a><a name="getrelatedlist"></a> Cmfcshelltreeci:: GetRelatedList

Bu [Cmfcshelltreecind](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesiyle Ilişkili [CMFCShellListCtrl sınıf](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesine bir işaretçi döndürür.

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CMFCShellListCtrl`Bu ağaç denetim nesnesiyle ilişkili nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CMFCShellListCtrl` bir nesneyle birlikte kullanarak bir `CMFCShellTreeCtrl` Gezgin benzeri pencere oluşturabilirsiniz. İki sınıfı ilişkilendirmek için [Cmfcshelltreecp:: SetRelatedList](#setrelatedlist) yöntemini kullanın. İlişkilendirildikten sonra çerçeve, `CMFCShellListCtrl` değişiklikler içinde seçimde otomatik olarak güncelleştirilir `CMFCShellTreeCtrl` .

## <a name="cmfcshelltreectrlonchildnotify"></a><a name="onchildnotify"></a> Cmfcshelltreecfy:: Onchildnotıfy

```
virtual BOOL OnChildNotify(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* pLResult);
```

### <a name="parameters"></a>Parametreler

'ndaki *ileti*<br/>
'ndaki *wParam*<br/>
'ndaki *lParam*<br/>
'ndaki *plResult*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcshelltreectrlongetitemicon"></a><a name="ongetitemicon"></a> Cmfcshelltreect:: OnGetItemIcon

```
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,
    BOOL bSelected);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pitem*<br/>
'ndaki *Bselected*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcshelltreectrlongetitemtext"></a><a name="ongetitemtext"></a> Cmfcshelltreecy:: Ongetıtemtext

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pitem*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcshelltreectrlrefresh"></a><a name="refresh"></a> Cmfcshelltreeci:: Refresh

[Cmfcshelltreeci](../../mfc/reference/cmfcshelltreectrl-class.md)'yi yeniler ve yeniden boyar.

```cpp
void Refresh();
```

### <a name="remarks"></a>Açıklamalar

İçinde görünen öğelerin hiyerarşisini yenilemek için bu yöntemi çağırın `CMFCShellTreeCtrl` .

## <a name="cmfcshelltreectrlselectpath"></a><a name="selectpath"></a> Cmfcshelltreeci:: SelectPath

Sağlanan yolu temel alan [Cmfcshelltreec, sınıfında](../../mfc/reference/cmfcshelltreectrl-class.md) bir öğe seçer.

```
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
'ndaki Bir öğenin yolunu belirten dize.

*lpidl*<br/>
'ndaki Öğeyi belirten bir PIDL

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde E_FAIL.

## <a name="cmfcshelltreectrlsetflags"></a><a name="setflags"></a> Cmfcshelltreeci:: SetFlags

Ağaç bağlamını filtrelemek için bayrakları ayarlar.

```cpp
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
'ndaki Ayarlanacak bayraklar.

*bRefresh*<br/>
'ndaki Hemen yenilenmesi gerekip gerekmediğini belirten bir Boole değeri `CMFCShellTreeCtrl`  .

### <a name="remarks"></a>Açıklamalar

`CMFCShellTreeCtrl`Tüm küme bayraklarını [IShellFolder:: EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)'e geçirir. Farklı bayrakların değerleri hakkında daha fazla bilgi için, bkz. [IShellFolder:: EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects).

## <a name="cmfcshelltreectrlsetrelatedlist"></a><a name="setrelatedlist"></a> Cmfcshelltreeci:: SetRelatedList

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesini bir [Cmfcshelltreeci](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesiyle ilişkilendirir.

```cpp
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>Parametreler

*pShellList*<br/>
'ndaki Bir `CMFCShellListCtrl` nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `CMFCShellListCtrl` ile ile ilişkilendirir `CMFCShellTreeCtrl` . Bu nesneler gezgin benzeri bir pencere olarak görüntülenebilir: Kullanıcı öğesinde bir nesne seçerse, `CMFCShellTreeCtrl` içindeki ilişkili öğeler `CMFCShellListCtrl` otomatik olarak güncelleştirilir.

İle ilişkili ' i almak için [Cmfcshelltreecmı:: GetRelatedList](#getrelatedlist) yöntemini kullanın `CMFCShellListCtrl` `CMFCShellTreeCtrl` .

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[Ctreeckclass sınıfı](../../mfc/reference/ctreectrl-class.md)<br/>
[CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md)
