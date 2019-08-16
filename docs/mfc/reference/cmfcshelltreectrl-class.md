---
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
ms.openlocfilehash: 97136342049a54d45af893962025f01eda4366d4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504903"
---
# <a name="cmfcshelltreectrl-class"></a>Cmfcshelltreeci sınıfı

Sınıfı `CMFCShellTreeCtrl` , kabuk öğelerinin hiyerarşisini görüntüleyerek [ctreecu sınıfı](../../mfc/reference/ctreectrl-class.md) işlevselliğini genişletir.

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC\\atlmfc\\\\src MFC** klasöründe bulunan kaynak koduna bakın.
## <a name="syntax"></a>Sözdizimi

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
|[Cmfcshelltreeci:: GetRelatedList](#getrelatedlist)|Gezgin benzeri bir pencere oluşturmak için bu `CMFCShellTreeCtrl` nesneyle birlikte kullanılan [CMFCShellListCtrl sınıf](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesine bir işaretçi döndürür.|
|[Cmfcshelltreecfy:: Onchildnotıfy](#onchildnotify)|Bu üye işlevi, bu pencere için geçerli olan bir bildirim iletisi aldığında bu pencerenin üst penceresi tarafından çağırılır. ( [CWnd:: OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify)geçersiz kılar.)|
|[Cmfcshelltreect:: OnGetItemIcon](#ongetitemicon)||
|[Cmfcshelltreecy:: Ongetıtemtext](#ongetitemtext)||
|[Cmfcshelltreeci:: Refresh](#refresh)|Geçerli `CMFCShellTreeCtrl` nesneyi yeniler ve yeniden boyar.|
|[Cmfcshelltreeci:: SelectPath](#selectpath)|Sağlanan PIDL veya dize yolunu temel alarak uygun ağaç denetim öğesini seçer.|
|[Cmfcshelltreeci:: SetFlags](#setflags)|Ağaç bağlamını filtrelemek için bayrakları ayarlar (tarafından `IShellFolder::EnumObjects`kullanılan bayraklara benzer).|
|[Cmfcshelltreeci:: SetRelatedList](#setrelatedlist)|Geçerli `CMFCShellTreeCtrl` nesne`CMFCShellListCtrl` ile nesne arasında bir ilişki ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, `CTreeCtrl` programınızı ağaca Windows Shell öğelerini dahil etmek üzere etkinleştirerek sınıfını genişletir. Bu sınıf, Tüm Gezgin penceresi oluşturmak `CMFCShellListCtrl` için bir nesneyle ilişkilendirilebilir. Daha sonra ağaçta bir öğenin seçilmesi, ilişkili listedeki Windows kabuğu öğelerinin bir listesini görüntüler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxshelltreecm. h

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCShellTreeCtrl` sınıfının bir nesnesinin nasıl oluşturulacağını gösterir. Bu kod parçacığı, [Gezgin örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

##  <a name="enableshellcontextmenu"></a>Cmfcshelltreeci:: EnableShellContextMenu

Kısayol menüsünü etkinleştirilir.

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Kısayol menüsünün etkinleştirilip etkinleştirilmeyeceğini belirten bir Boole değeri.

##  <a name="getflags"></a>Cmfcshelltreeci:: GetFlags

[Cmfcshelltreecind Class](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesi için ayarlanan bayrakları döndürür.

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda ayarlanmış olan bayrakların birleşimini belirten bir DWORD değeri.

### <a name="remarks"></a>Açıklamalar

İçinde ayarlanan bayraklar, `CMFCShellTreeCtrl` nesne yenilendiğinde [IShellFolder:: EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) yöntemine gönderilir. Bayrakları [Cmfcshelltreec,:: SetFlags](#setflags) yöntemiyle değiştirebilirsiniz.

##  <a name="getitempath"></a>Cmfcshelltreecl:: Getıtempgunlum

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

*Htreeitem*belirtmezseniz, bu yöntem seçili olan öğe için dizeyi almaya çalışır. Hiçbir öğe seçilmezse ve *Htreeitem* null ise, bu yöntem başarısız olur.

##  <a name="getrelatedlist"></a>Cmfcshelltreeci:: GetRelatedList

Bu [Cmfcshelltreecind](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesiyle Ilişkili [CMFCShellListCtrl sınıf](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesine bir işaretçi döndürür.

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu ağaç denetim nesnesiyle `CMFCShellListCtrl` ilişkili nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi bir `CMFCShellListCtrl` `CMFCShellTreeCtrl` nesneyle birlikte kullanarak bir gezgin benzeri pencere oluşturabilirsiniz. İki sınıfı ilişkilendirmek için [Cmfcshelltreecp:: SetRelatedList](#setrelatedlist) yöntemini kullanın. İlişkilendirildikten sonra çerçeve, `CMFCShellListCtrl` `CMFCShellTreeCtrl` değişiklikler içinde seçimde otomatik olarak güncelleştirilir.

##  <a name="onchildnotify"></a>Cmfcshelltreecfy:: Onchildnotıfy

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

##  <a name="ongetitemicon"></a>Cmfcshelltreect:: OnGetItemIcon

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

##  <a name="ongetitemtext"></a>Cmfcshelltreecy:: Ongetıtemtext

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pitem*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="refresh"></a>Cmfcshelltreeci:: Refresh

[Cmfcshelltreeci](../../mfc/reference/cmfcshelltreectrl-class.md)'yi yeniler ve yeniden boyar.

```
void Refresh();
```

### <a name="remarks"></a>Açıklamalar

İçinde görünen öğelerin hiyerarşisini yenilemek için bu yöntemi çağırın `CMFCShellTreeCtrl`.

##  <a name="selectpath"></a>Cmfcshelltreeci:: SelectPath

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

Başarılı olursa S_OK; Aksi takdirde E_FAıL.

##  <a name="setflags"></a>Cmfcshelltreeci:: SetFlags

Ağaç bağlamını filtrelemek için bayrakları ayarlar.

```
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
'ndaki Ayarlanacak bayraklar.

*bRefresh*<br/>
'ndaki Hemen yenilenmesi gerekip gerekmediğini `CMFCShellTreeCtrl` belirten bir Boole değeri.

### <a name="remarks"></a>Açıklamalar

Tüm küme bayraklarını [IShellFolder:: EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)'e geçirir.`CMFCShellTreeCtrl` Farklı bayrakların değerleri hakkında daha fazla bilgi için, bkz. [IShellFolder:: EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects).

##  <a name="setrelatedlist"></a>Cmfcshelltreeci:: SetRelatedList

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesini bir [Cmfcshelltreeci](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesiyle ilişkilendirir.

```
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>Parametreler

*pShellList*<br/>
'ndaki Bir `CMFCShellListCtrl` nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `CMFCShellListCtrl` `CMFCShellTreeCtrl`ile ile ilişkilendirir. Bu nesneler gezgin benzeri bir pencere olarak görüntülenebilir: Kullanıcı öğesinde `CMFCShellTreeCtrl`bir nesne seçerse, `CMFCShellListCtrl` içindeki ilişkili öğeler otomatik olarak güncelleştirilir.

`CMFCShellListCtrl` İle`CMFCShellTreeCtrl`ilişkili ' i almak için [cmfcshelltreecmı:: GetRelatedList](#getrelatedlist) yöntemini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CTreeCtrl Sınıfı](../../mfc/reference/ctreectrl-class.md)<br/>
[CMFCShellListCtrl Sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md)
