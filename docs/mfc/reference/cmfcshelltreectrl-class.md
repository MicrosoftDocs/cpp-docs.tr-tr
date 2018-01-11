---
title: "CMFCShellTreeCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 727b0032687ed22692f07f9b5e9e5fe8b2813071
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcshelltreectrl-class"></a>CMFCShellTreeCtrl sınıfı
`CMFCShellTreeCtrl` Sınıfını genişleten [CTreeCtrl sınıfı](../../mfc/reference/ctreectrl-class.md) Kabuk öğeleri hiyerarşisini görüntüleyerek işlevselliği.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCShellTreeCtrl : public CTreeCtrl  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCShellTreeCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Etkinleştirir veya kısayol menüsünü devre dışı bırakır.|  
|[CMFCShellTreeCtrl::GetFlags](#getflags)|Geçirilen bayraklar birleşimini döndürür [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).|  
|[CMFCShellTreeCtrl::GetItemPath](#getitempath)|Bir öğe yolu alır.|  
|[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)|Bir işaretçi döndürür [CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) bu ile birlikte kullanılan nesnesi `CMFCShellTreeCtrl` bir Gezgin benzeri penceresi oluşturulacak nesne.|  
|[CMFCShellTreeCtrl::OnChildNotify](#onchildnotify)|Bu pencere için geçerli bir bildirim iletisi aldığında, bu üye işlevi bu pencerenin üst pencere tarafından çağrılır. (Geçersiz kılmaları [CWnd::OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify).)|  
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||  
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||  
|[CMFCShellTreeCtrl::Refresh](#refresh)|Yeniler ve geçerli şekilde yeniden boyar `CMFCShellTreeCtrl` nesnesi.|  
|[CMFCShellTreeCtrl::SelectPath](#selectpath)|Bir sağlanan PIDL işaretçisiyle birlikte veya dize yolu göre uygun ağaç denetim öğesi seçer.|  
|[CMFCShellTreeCtrl::SetFlags](#setflags)|Ağaç bağlam filtrelemek için bayrakları ayarlar (tarafından kullanılan bayrakları benzer `IShellFolder::EnumObjects`).|  
|[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)|Geçerli arasında bir ilişki ayarlar `CMFCShellTreeCtrl` nesne ve `CMFCShellListCtrl` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfını genişleten `CTreeCtrl` ağacında Windows Kabuğu öğeleri içerecek şekilde, program etkinleştirerek sınıfı. Bu sınıf ile ilişkili bir `CMFCShellListCtrl` tam Gezgini penceresi oluşturulacak nesne. Ardından, ağacında bir öğeyi seçerek Windows Kabuğu öğelerinin bir listesini ilişkili listesinde görüntülenir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)  
  
 `CMFCShellTreeCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxshelltreeCtrl.h  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCShellTreeCtrl` sınıfı. Bu kod parçacığını parçası olan [Gezgini örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]  
  
##  <a name="enableshellcontextmenu"></a>CMFCShellTreeCtrl::EnableShellContextMenu  
 Kısayol menüsünü etkinleştirir.  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 Kısayol menüsünün etkinleştirilip etkinleştirilmeyeceğini belirten bir Boole değeri.  
  
##  <a name="getflags"></a>CMFCShellTreeCtrl::GetFlags  
 İçin ayarlanan bayraklar döndürür [CMFCShellTreeCtrl sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesi.  
  
```  
DWORD GetFlags() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `DWORD` bayrakları şu anda bileşimini değerini ayarlayın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bayrakları kümesinde `CMFCShellTreeCtrl` yöntemine gönderilen [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066) her nesne yenilenir. Bayraklarıyla değiştirebileceğiniz [CMFCShellTreeCtrl::SetFlags](#setflags) yöntemi.  
  
##  <a name="getitempath"></a>CMFCShellTreeCtrl::GetItemPath  
 Bir öğeyi yolunu alır [CMFCShellTreeCtrl sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesi.  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    HTREEITEM htreeItem = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`strPath`  
 Bir dize parametresi referansı. Yöntemi bu parametreye öğesinin yolu yazar.  
  
 [in]`htreeItem`  
 Yöntemi bu ağaç denetim öğesi yolunu alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem başarısız olursa `strPath` boş dize içeriyor.  
  
 Belirtmezseniz, `hTreeItem`, bu yöntem, seçili öğe için dize almayı dener. Öğe seçiliyse ve `hTreeItem` olan `NULL`, bu yöntem başarısız olur.  
  
##  <a name="getrelatedlist"></a>CMFCShellTreeCtrl::GetRelatedList  
 Bir işaretçi döndürür [CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) bu ile ilişkili olan nesne [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesi.  
  
```  
CMFCShellListCtrl* GetRelatedList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `CMFCShellListCtrl` bu ağaç denetimi nesneyle ilişkili nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanarak bir `CMFCShellListCtrl` nesnesi ile birlikte bir `CMFCShellTreeCtrl` nesnesi, bir Gezgin benzeri penceresi oluşturabilirsiniz. Yöntem kullanmak [CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist) iki sınıf ilişkilendirilecek. İlişkili sonra framework otomatik olarak güncelleştirir `CMFCShellListCtrl` , seçim `CMFCShellTreeCtrl` değişiklikler.  
  
##  <a name="onchildnotify"></a>CMFCShellTreeCtrl::OnChildNotify  

  
```  
virtual BOOL OnChildNotify(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pLResult);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`message`  
 [in]`wParam`  
 [in]`lParam`  
 [in]`pLResult`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ongetitemicon"></a>CMFCShellTreeCtrl::OnGetItemIcon  

  
```  
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pItem`  
 [in]`bSelected`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ongetitemtext"></a>CMFCShellTreeCtrl::OnGetItemText  

  
```  
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pItem`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="refresh"></a>CMFCShellTreeCtrl::Refresh  
 Yeniler ve şekilde yeniden boyar [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md).  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde görüntülenen öğelerin hiyerarşisini yenilemek için bu yöntemi çağırabilmeniz `CMFCShellTreeCtrl`.  
  
##  <a name="selectpath"></a>CMFCShellTreeCtrl::SelectPath  
 Bir öğeyi seçer [CMFCShellTreeCtrl sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md) sağlanan yola göre.  
  
```  
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszPath`  
 Bir öğe yolu belirten bir dize.  
  
 [in]`lpidl`  
 Öğeyi belirten bir PIDL işaretçisiyle birlikte  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK`başarılı olursa; `E_FAIL` Aksi takdirde.  
  
##  <a name="setflags"></a>CMFCShellTreeCtrl::SetFlags  
 Ağaç bağlam filtrelemek için bayrakları ayarlar.  
  
```  
void SetFlags(
    DWORD dwFlags,  
    BOOL bRefresh = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`dwFlags`  
 Ayarlamak için işaretler.  
  
 [in]`bRefresh`  
 Belirten bir Boole değeri olup olmadığını `CMFCShellTreeCtrl` hemen yenilenmesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CMFCShellTreeCtrl` Tüm kümesine bayrakları geçişleri [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066). Farklı bayrakları değerleri hakkında daha fazla bilgi için bkz: [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).  
  
##  <a name="setrelatedlist"></a>CMFCShellTreeCtrl::SetRelatedList  
 İlişkilendiren bir [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi ile bir [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesi.  
  
```  
void SetRelatedList(CMFCShellListCtrl* pShellList);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pShellList`  
 Bir işaretçi bir `CMFCShellListCtrl` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ilişkilendiren bir `CMFCShellListCtrl` ile bir `CMFCShellTreeCtrl`. Bu nesneler Gezgin benzeri pencere olarak görüntülenebilir: kullanıcı bir nesneyi seçtiğinde `CMFCShellTreeCtrl`, öğeleri ilişkili `CMFCShellListCtrl` otomatik olarak güncelleştirilir.  
  
 Yöntem kullanmak [CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist) almak için `CMFCShellListCtrl` ile ilişkili bir `CMFCShellTreeCtrl`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CTreeCtrl sınıfı](../../mfc/reference/ctreectrl-class.md)   
 [CMFCShellListCtrl Sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md)
