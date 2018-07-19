---
title: CMFCShellTreeCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c0508f0042f63441b3a9bdf66cd29ca0a9a73e6
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849808"
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
|[CMFCShellTreeCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Etkinleştirir veya kısayol menüsünden devre dışı bırakır.|  
|[CMFCShellTreeCtrl::GetFlags](#getflags)|Geçirilen bayrakların birleşimi döndürür [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).|  
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
 Aşağıdaki örnek, bir nesnenin oluşturulacağı gösterilmektedir `CMFCShellTreeCtrl` sınıfı. Bu kod parçacığı parçasıdır [Gezgini örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]  
  
##  <a name="enableshellcontextmenu"></a>  CMFCShellTreeCtrl::EnableShellContextMenu  
 Kısayol menüsünü etkinleştirir.  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 Kısayol menüsünün etkinleştirilip etkinleştirilmeyeceğini belirleyen bir Boole değeri.  
  
##  <a name="getflags"></a>  CMFCShellTreeCtrl::GetFlags  
 İçin ayarlanan işaretlere döndürür [CMFCShellTreeCtrl sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md) nesne.  
  
```  
DWORD GetFlags() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda bayrakların birleşimi belirten bir DWORD değeri ayarlayın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bayrakları kümesinde `CMFCShellTreeCtrl` yöntemine gönderilen [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066) her nesne yenilenir. Bayraklarıyla değiştirebilirsiniz [CMFCShellTreeCtrl::SetFlags](#setflags) yöntemi.  
  
##  <a name="getitempath"></a>  CMFCShellTreeCtrl::GetItemPath  
 Bir öğenin yolunu alır [CMFCShellTreeCtrl sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md) nesne.  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    HTREEITEM htreeItem = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *strPath*  
 Bir dize parametresi bir başvuru. Yöntemi, bu parametre için öğenin yolu yazar.  
  
 [in] *htreeItem*  
 Yöntemi, bu ağaç denetim öğesi yolunu alır.  
  
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
 [in] *iletisi*  
 [in] *wParam*  
 [in] *lParam*  
 [in] *pLResult*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ongetitemicon"></a>  CMFCShellTreeCtrl::OnGetItemIcon  

  
```  
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pItem*  
 [in] *bSelected*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ongetitemtext"></a>  CMFCShellTreeCtrl::OnGetItemText  

  
```  
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pItem*  
  
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
 [in] *lpszPath*  
 Bir öğenin konumunu belirten bir dize.  
  
 [in] *lpidl*  
 Öğeyi belirten bir PIDL işaretçisiyle birlikte  
  
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
 [in] *CertOpenStore*  
 Ayarlanacak bayraklar.  
  
 [in] *bRefresh*  
 Belirten Boolean bir değer olup olmadığını `CMFCShellTreeCtrl` hemen yenilenmesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CMFCShellTreeCtrl` Tüm kümesine bayrakları geçişleri [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066). Farklı bayrakları değerler hakkında daha fazla bilgi için bkz. [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).  
  
##  <a name="setrelatedlist"></a>  CMFCShellTreeCtrl::SetRelatedList  
 İlişkilendirir bir [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi ile bir [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) nesne.  
  
```  
void SetRelatedList(CMFCShellListCtrl* pShellList);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pShellList*  
 Bir işaretçi bir `CMFCShellListCtrl` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ilişkilendirir bir `CMFCShellListCtrl` ile bir `CMFCShellTreeCtrl`. Bu nesneleri bir Gezgin benzeri penceresi olarak görüntülenebilir: kullanıcı, nesneyi seçerse `CMFCShellTreeCtrl`, ilişkili öğeleri de `CMFCShellListCtrl` otomatik olarak güncelleştirilir.  
  
 Bu yöntemi kullanmak [CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist) alınacak `CMFCShellListCtrl` ile ilişkili bir `CMFCShellTreeCtrl`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CTreeCtrl sınıfı](../../mfc/reference/ctreectrl-class.md)   
 [CMFCShellListCtrl Sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md)
