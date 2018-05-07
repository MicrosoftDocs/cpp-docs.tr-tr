---
title: CMFCShellListCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayParentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::EnableShellContextMenu
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolderName
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentItemIdList
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentShellFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemPath
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemTypes
- AFXSHELLLISTCTRL/CMFCShellListCtrl::IsDesktop
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnCompareItems
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileDate
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileSize
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemIcon
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemText
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnSetColumns
- AFXSHELLLISTCTRL/CMFCShellListCtrl::Refresh
- AFXSHELLLISTCTRL/CMFCShellListCtrl::SetItemTypes
dev_langs:
- C++
helpviewer_keywords:
- CMFCShellListCtrl [MFC], DisplayFolder
- CMFCShellListCtrl [MFC], DisplayParentFolder
- CMFCShellListCtrl [MFC], EnableShellContextMenu
- CMFCShellListCtrl [MFC], GetCurrentFolder
- CMFCShellListCtrl [MFC], GetCurrentFolderName
- CMFCShellListCtrl [MFC], GetCurrentItemIdList
- CMFCShellListCtrl [MFC], GetCurrentShellFolder
- CMFCShellListCtrl [MFC], GetItemPath
- CMFCShellListCtrl [MFC], GetItemTypes
- CMFCShellListCtrl [MFC], IsDesktop
- CMFCShellListCtrl [MFC], OnCompareItems
- CMFCShellListCtrl [MFC], OnFormatFileDate
- CMFCShellListCtrl [MFC], OnFormatFileSize
- CMFCShellListCtrl [MFC], OnGetItemIcon
- CMFCShellListCtrl [MFC], OnGetItemText
- CMFCShellListCtrl [MFC], OnSetColumns
- CMFCShellListCtrl [MFC], Refresh
- CMFCShellListCtrl [MFC], SetItemTypes
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9073c3443b1c74a27c9de9be142c67fab7f40ba8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcshelllistctrl-class"></a>CMFCShellListCtrl sınıfı
`CMFCShellListCtrl` Sınıf Windows listesi denetim işlevselliği sunar ve Kabuk öğelerinin bir listesini görüntülemek için özelliği ekleyerek genişletir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|Sağlanan bir klasörde yer alan öğeleri listesini görüntüler.|  
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|Şu anda görüntülenen klasörü üst klasörde yer alan öğeleri listesini görüntüler.|  
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Etkinleştirir veya kısayol menüsünü devre dışı bırakır.|  
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|Geçerli klasör yolunu alır.|  
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|Geçerli klasör adını alır.|  
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|Geçerli liste denetim öğesi PIDL işaretçisiyle birlikte döndürür.|  
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|Bir işaretçi geçerli kabuk klasörünün döndürür.|  
|[CMFCShellListCtrl::GetItemPath](#getitempath)|Bir öğenin metin yolunu döndürür.|  
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|Liste denetimi tarafından görüntülenen Kabuk öğesi türlerini döndürür.|  
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|Seçili klasörü Masaüstü klasöründe olup olmadığını denetler.|  
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|İki öğeyi karşılaştırır zaman çerçevesi bu yöntemi çağırır. (Geçersiz kılmaları [CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).)|  
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|Liste denetimi tarafından görüntülenen dosya tarihi framework aldığında çağrılır.|  
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|Liste denetimi dosya boyutunu framework dönüştürür çağrılır.|  
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|Çerçeve bir liste denetim öğesi simgesini aldığında çağrılır.|  
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|Liste Denetim öğesi metni framework dönüştürür çağrılır.|  
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|Sütun adlarını ayarlar çerçevesi tarafından çağrılır.|  
|[CMFCShellListCtrl::Refresh](#refresh)|Yeniler ve liste denetimi şekilde yeniden boyar.|  
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|Liste denetimi tarafından görüntülenen öğelerin türünü ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCShellListCtrl` Sınıfını genişleten işlevselliğini [CMFCListCtrl sınıfı](../../mfc/reference/cmfclistctrl-class.md) Windows Kabuk öğeleri listelemek, program etkinleştirerek. Bir liste görünümü Gezgini penceresi için kullanılan görüntü biçimi gibidir.  
  
 A [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) nesne ilişkilendirilebilir bir `CMFCShellListCtrl` tam Gezgini penceresi oluşturulacak nesne. Ardından, bir öğeyi seçerek `CMFCShellTreeCtrl` neden olacak `CMFCShellListCtrl` seçili öğenin içeriğini listelemek için nesne.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCShellListCtrl` sınıf ve o anda görüntülenen klasörün üst klasörünü görüntüleme. Bu kod parçacığını parçası olan [Gezgini örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_3.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
 `CMFCShellListCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxshelllistCtrl.h  
  
##  <a name="displayfolder"></a>  CMFCShellListCtrl::DisplayFolder  
 Sağlanan klasörde yer alan öğeleri listesini görüntüler.  
  
```  
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszPath`  
 Bir klasörün yolunu içeren bir dize.  
  
 [in] `lpItemInfo`  
 Bir işaretçi bir `LPAFX_SHELLITEMINFO` görüntülemek için bir klasör açıklar yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK` başarılı olursa; `E_FAIL` Aksi takdirde.  
  
##  <a name="displayparentfolder"></a>  CMFCShellListCtrl::DisplayParentFolder  
 Güncelleştirmeleri [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) şu anda görüntülenen klasörün üst klasörünü görüntülenecek nesne.  
  
```  
virtual HRESULT DisplayParentFolder();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK` başarılı olursa; `E_FAIL` Aksi takdirde.  
  
##  <a name="enableshellcontextmenu"></a>  CMFCShellListCtrl::EnableShellContextMenu  
 Kısayol menüsünü etkinleştirir.  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 Framework kısayol menüsünü etkinleştirir olup olmadığını belirten bir Boole değeri.  
  
##  <a name="getcurrentfolder"></a>  CMFCShellListCtrl::GetCurrentFolder  
 Şu anda seçili olan klasörün yolunu alır [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi.  
  
```  
BOOL GetCurrentFolder(CString& strPath) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `strPath`  
 Yolun yöntemi nereye yazdığını bir dize parametresi referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Seçilen klasör varsa bu yöntem başarısız `CMFCShellListCtrl`.  
  
##  <a name="getcurrentfoldername"></a>  CMFCShellListCtrl::GetCurrentFolderName  
 Şu anda seçili olan klasörün adını alır [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi.  
  
```  
BOOL GetCurrentFolderName(CString& strName) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `strName`  
 Yöntem adı nereye yazdığını bir dize parametresi referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Seçilen klasör varsa bu yöntem başarısız `CMFCShellListCtrl`.  
  
##  <a name="getcurrentitemidlist"></a>  CMFCShellListCtrl::GetCurrentItemIdList  
 Seçili öğenin PIDL işaretçisiyle birlikte döndürür.  
  
```  
LPITEMIDLIST GetCurrentItemIdList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli öğeye PIDL işaretçisiyle birlikte.  
  
##  <a name="getcurrentshellfolder"></a>  CMFCShellListCtrl::GetCurrentShellFolder  
 Seçili öğe için bir işaretçi alır [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi.  
  
```  
const IShellFolder* GetCurrentShellFolder() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [IShellFolder arabirimi](http://msdn.microsoft.com/library/windows/desktop/bb775075) seçili nesne için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem `NULL` hiçbir nesne şu anda seçili değilse.  
  
##  <a name="getitempath"></a>  CMFCShellListCtrl::GetItemPath  
 Öğenin yolunu alır.  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    int iItem) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `strPath`  
 Bir başvuru bir dizeye yolunu alır.  
  
 [in] `iItem`  
 Liste öğesi dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` başarılı olursa; `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından sağlanan dizin `iItem` tarafından şu anda görüntülenen öğelerin dayalı [CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi.  
  
##  <a name="getitemtypes"></a>  CMFCShellListCtrl::GetItemTypes  
 Tarafından görüntülenen öğelerin türünü döndürür [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi.  
  
```  
SHCONTF GetItemTypes() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539) listelenen öğelerin türünü içeren değer `CMFCShellListCtrl`.  
  
### <a name="remarks"></a>Açıklamalar  
 Listelenen öğelerin türünü ayarlamak için bir `CMFCShellListCtrl`, çağrı [CMFCShellListCtrl::SetItemTypes](#setitemtypes).  
  
##  <a name="isdesktop"></a>  CMFCShellListCtrl::IsDesktop  
 Klasörü, olup olmadığını belirler görüntülenen [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesne Masaüstü klasördür.  
  
```  
BOOL IsDesktop() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Görüntülenen klasör Masaüstü klasörse; `FALSE` Aksi takdirde.  
  
##  <a name="oncompareitems"></a>  CMFCShellListCtrl::OnCompareItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lParam1`  
 [in] `lParam2`  
 [in] `iColumn`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onformatfiledate"></a>  CMFCShellListCtrl::OnFormatFileDate  
 Çerçeve bir dizeye bir nesneyle ilişkili tarih dönüştürmeniz gerekir, bu yöntemi çağırır.  
  
```  
virtual void OnFormatFileDate(
    const CTime& tmFile,  
    CString& str);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `tmFile`  
 Bir dosyayla ilişkili tarih.  
  
 [out] `str`  
 Biçimlendirilmiş dosyası tarih içeren bir dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman bir [CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) nesne bir dosyayla ilişkili tarihi görüntüler, bunu, tarihin dize biçimine dönüştürmeniz gerekir. `CMFCShellListCtrl` Bu dönüştürme yapmak için bu yöntemi kullanır. Varsayılan olarak, bu yöntem tarih biçiminde bir dizeye için geçerli yerel ayarı kullanır.  
  
##  <a name="onformatfilesize"></a>  CMFCShellListCtrl::OnFormatFileSize  
 Bir dizeyi bir nesnenin boyutu dönüştürdüğünde framework bu yöntemi çağırır.  
  
```  
virtual void OnFormatFileSize(
    long lFileSize,  
    CString& str);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lFileSize`  
 Framework görüntüler dosya boyutu.  
  
 [out] `str`  
 Biçimlendirilmiş dosya boyutu içeren bir dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman bir [CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) nesne gereken bir dosyanın boyutunu görüntülemek, dosya boyutu bir dize biçimine dönüştürmeniz gerekir. `CMFCShellListCtrl` Bu dönüştürme yapmak için bu yöntemi kullanır. Varsayılan olarak, bu yöntem dosya boyutunu bayt, kaynağı için kilobayt dönüştürür ve boyutu dizeye biçimlendirmek için geçerli yerel ayarı kullanır.  
  
##  <a name="ongetitemicon"></a>  CMFCShellListCtrl::OnGetItemIcon  
 Çerçeve bir kabuk listesi öğesiyle ilişkili simgeyi almak için bu yöntemi çağırır.  
  
```  
virtual int OnGetItemIcon(
    int iItem,  
    LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iItem`  
 Öğe dizini.  
  
 [in] `pItem`  
 A `LPAFX_SHELLITEMINFO` öğeyi açıklayan parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa simge görüntüsünün dizinini; işlev başarısız olursa -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Simge görüntüsü dizini sistem görüntüsü listede temel alır.  
  
 Varsayılan olarak, bu yöntem dayanan `pItem` parametresi. Değeri `iItem` varsayılan uygulamasında kullanılmaz. Kullanabileceğiniz `iItem` özel davranışı uygulamak için.  
  
##  <a name="ongetitemtext"></a>  CMFCShellListCtrl::OnGetItemText  
 Kabuk öğenin metnini almasının gerektiği zaman çerçevesi bu yöntemi çağırır.  
  
```  
virtual CString OnGetItemText(
    int iItem,  
    int iColumn,  
    LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iItem`  
 Öğe dizini.  
  
 [in] `iColumn`  
 İlgilenilen sütun.  
  
 [in] `pItem`  
 A `LPAFX_SHELLITEMINFO` öğeyi açıklayan parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` öğeyle ilişkili metni içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Her öğe `CMFCShellListCtrl` nesnesi bir veya daha fazla sütun metin sahip olabilir. Bu yöntem framework çağırır onu ilgilendiği sütun belirtir. Bu işlev el ile çağırırsanız, ilgilendiğiniz sütun belirtmeniz gerekir.  
  
 Varsayılan olarak, bu yöntem dayanan `pItem` olduğu için işlem öğesi belirlemek için parametre. Değeri `iItem` varsayılan uygulamasında kullanılmaz.  
  
##  <a name="onsetcolumns"></a>  CMFCShellListCtrl::OnSetColumns  
 Sütun adlarını ayarladığında framework bu yöntemi çağırır.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, dört sütun framework oluşturur bir `CMFCShellListCtrl` nesnesi. Bu sütun adlarının `Name`, `Size`, `Type`, ve `Modified`. Sütunları ve adlarını sayısını özelleştirmek için bu yöntemin üzerine yazabilir.  
  
##  <a name="refresh"></a>  CMFCShellListCtrl::Refresh  
 Yeniler ve şekilde yeniden boyar [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi.  
  
```  
virtual HRESULT Refresh();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK` başarılı olursa; Aksi takdirde bir hata değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından görüntülenen öğelerin listesini yenilemek için bu yöntemi çağırabilmeniz `CMFCShellListCtrl` nesnesi.  
  
##  <a name="setitemtypes"></a>  CMFCShellListCtrl::SetItemTypes  
 Listelenen öğelerin türünü ayarlar [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi.  
  
```  
void SetItemTypes(SHCONTF nTypes);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nTypes`  
 Öğe listesi türleri `CMFCShellListCtrl` nesne destekler.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğe türleri listesi hakkında daha fazla bilgi için bkz: [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl sınıfı](../../mfc/reference/cmfclistctrl-class.md)   
 [CMFCShellTreeCtrl Sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md)
