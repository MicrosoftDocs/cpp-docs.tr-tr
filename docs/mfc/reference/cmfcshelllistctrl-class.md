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
ms.openlocfilehash: c2fcd07f831133ff478dcccb4272ef24496e3cac
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066493"
---
# <a name="cmfcshelllistctrl-class"></a>CMFCShellListCtrl sınıfı

`CMFCShellListCtrl` Sınıf Windows liste denetleme işlevlerini sağlar ve bir kabuk öğeleri listesi görüntüleme özelliğini ekleyerek bunu genişletir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCShellListCtrl : public CMFCListCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|Belirtilen klasörde bulunan öğeleri listesini görüntüler.|
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|Şu anda görüntülenen klasörün üst klasörde bulunan öğeleri listesini görüntüler.|
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Etkinleştirir veya kısayol menüsünden devre dışı bırakır.|
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|Geçerli klasör yolunu alır.|
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|Geçerli klasör adını alır.|
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|Geçerli liste denetim öğesi PIDL işaretçisiyle birlikte döndürür.|
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|Geçerli kabuk klasörü için bir işaretçi döndürür.|
|[CMFCShellListCtrl::GetItemPath](#getitempath)|Bir öğe metinsel yolunu döndürür.|
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|Liste denetimi tarafından görüntülenen Kabuk öğesi türlerini döndürür.|
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|Şu anda seçili klasör Masaüstü klasöründe olup olmadığını denetler.|
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|İki öğeleri karşılaştırırken framework bu yöntemi çağırır. (Geçersiz kılmaları [CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).)|
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|Çerçeve listesi denetimi tarafından görüntülenen dosya tarih aldığında çağrılır.|
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|Liste denetimi dosya boyutunu framework dönüştürür çağrılır.|
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|Çerçeve listesi denetim öğesini simgesini aldığında çağrılır.|
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|Çerçeve listesi denetim öğesini metnini dönüştürür çağrılır.|
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|Sütun adlarını ayarlar framework tarafından çağırılır.|
|[CMFCShellListCtrl::Refresh](#refresh)|Yenilenir ve liste denetimi halinde yeniden boyar.|
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|Liste denetimi tarafından görüntülenen öğelerin türünü ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CMFCShellListCtrl` Sınıf işlevselliğini genişleten [CMFCListCtrl sınıfı](../../mfc/reference/cmfclistctrl-class.md) etkinleştirerek programınızın Windows Kabuk öğeleri listesi. Bir liste görünümünün bir Gezgin penceresi için kullanılan görüntü biçimi gibidir.

A [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) nesne ilişkili bir `CMFCShellListCtrl` eksiksiz bir Gezgini penceresi oluşturulacak nesne. Ardından, bir öğeyi seçerek `CMFCShellTreeCtrl` açacak `CMFCShellListCtrl` seçilen öğenin içeriğini listelemek için nesne.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnenin oluşturulacağı gösterilmektedir `CMFCShellListCtrl` sınıfı ve şu anda görüntülenen klasörün üst klasörü görüntüleme. Bu kod parçacığı parçasıdır [Gezgini örneği](../../visual-cpp-samples.md).

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

Belirtilen klasörde bulunan öğeleri listesini görüntüler.

```
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
[in] Bir klasörün yolunu içeren bir dize.

*lpItemInfo*<br/>
[in] Bir işaretçi bir `LPAFX_SHELLITEMINFO` açıklayan görüntülemek için bir klasör yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; E_FAIL Aksi takdirde.

##  <a name="displayparentfolder"></a>  CMFCShellListCtrl::DisplayParentFolder

Güncelleştirmeleri [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) şu anda görüntülenen klasörün üst klasörü görüntülemek için nesne.

```
virtual HRESULT DisplayParentFolder();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; E_FAIL Aksi takdirde.

##  <a name="enableshellcontextmenu"></a>  CMFCShellListCtrl::EnableShellContextMenu

Kısayol menüsünü etkinleştirir.

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Framework kısayol menüsünü etkinleştirir olup olmadığını belirten bir Boole değeri.

##  <a name="getcurrentfolder"></a>  CMFCShellListCtrl::GetCurrentFolder

Şu anda seçili olan klasörün yolunu alır [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesne.

```
BOOL GetCurrentFolder(CString& strPath) const;
```

### <a name="parameters"></a>Parametreler

*strPath*<br/>
[out] Bir dize parametresi, yöntemin yol nereye yazdığını başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Seçili klasör varsa, bu yöntem başarısız `CMFCShellListCtrl`.

##  <a name="getcurrentfoldername"></a>  CMFCShellListCtrl::GetCurrentFolderName

Şu anda seçili klasörde bulunan adını alır [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesne.

```
BOOL GetCurrentFolderName(CString& strName) const;
```

### <a name="parameters"></a>Parametreler

*strName*<br/>
[out] Yöntem adı nereye yazdığını bir dize parametresi bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Seçili klasör varsa, bu yöntem başarısız `CMFCShellListCtrl`.

##  <a name="getcurrentitemidlist"></a>  CMFCShellListCtrl::GetCurrentItemIdList

Seçili öğenin PIDL işaretçisiyle birlikte döndürür.

```
LPITEMIDLIST GetCurrentItemIdList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğenin PIDL işaretçisiyle birlikte.

##  <a name="getcurrentshellfolder"></a>  CMFCShellListCtrl::GetCurrentShellFolder

Şu anda seçili öğeye bir işaretçi alır [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesne.

```
const IShellFolder* GetCurrentShellFolder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi [IShellFolder arabirimi](https://msdn.microsoft.com/library/windows/desktop/bb775075) seçili nesne için.

### <a name="remarks"></a>Açıklamalar

Şu anda hiçbir nesne seçili değilse bu yöntem NULL döndürür.

##  <a name="getitempath"></a>  CMFCShellListCtrl::GetItemPath

Bir öğenin yolunu alır.

```
BOOL GetItemPath(
    CString& strPath,
    int iItem) const;
```

### <a name="parameters"></a>Parametreler

*strPath*<br/>
[out] Bir başvuru bir dizeye yolunu alır.

*iItem*<br/>
[in] Liste öğesi dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE; FALSE Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Tarafından sağlanan dizin *iItem* tarafından şu anda görüntülenen öğeler dayalı [CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) nesne.

##  <a name="getitemtypes"></a>  CMFCShellListCtrl::GetItemTypes

Tarafından görüntülenen öğelerin türünü döndürür [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesne.

```
SHCONTF GetItemTypes() const;
```

### <a name="return-value"></a>Dönüş Değeri

A [SHCONTF](/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shcontf) listelenen öğelerin türünü içeren değer `CMFCShellListCtrl`.

### <a name="remarks"></a>Açıklamalar

Listelenen öğelerin türünü ayarlamak için bir `CMFCShellListCtrl`, çağrı [CMFCShellListCtrl::SetItemTypes](#setitemtypes).

##  <a name="isdesktop"></a>  CMFCShellListCtrl::IsDesktop

Klasör, olup olmadığını belirler. görüntülenen [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Masaüstü klasöründe nesnedir.

```
BOOL IsDesktop() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntülenen klasörü Masaüstü klasöründe ise TRUE; FALSE Aksi takdirde.

##  <a name="oncompareitems"></a>  CMFCShellListCtrl::OnCompareItems

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>Parametreler

[in] *lParam1*<br/>
[in] *lParam2*<br/>
[in] *iColumn*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onformatfiledate"></a>  CMFCShellListCtrl::OnFormatFileDate

Framework bu yöntemi çağırır tarihi bir dizeye bir nesneyle ilişkilendirilmiş dönüştürmeniz gerekir.

```
virtual void OnFormatFileDate(
    const CTime& tmFile,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*tmFile*<br/>
[in] Bir dosya ile ilişkilendirilmiş tarih.

*str*<br/>
[out] Bir dosya tarih içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Olduğunda bir [CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi bir dosya ile ilişkilendirilmiş tarihi görüntüler, onu o tarih dize biçimine dönüştürmeniz gerekir. `CMFCShellListCtrl` Bu dönüştürme yapmak için bu yöntemi kullanır. Varsayılan olarak, bu yöntem bir dize olarak tarihi biçimlendirmek için geçerli yerel ayarı kullanır.

##  <a name="onformatfilesize"></a>  CMFCShellListCtrl::OnFormatFileSize

Framework bu yöntemi çağırır, bir nesnenin boyutunu bir dizeye dönüştürür.

```
virtual void OnFormatFileSize(
    long lFileSize,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*lFileSize*<br/>
[in] Framework görüntüleyecek dosyasının boyutu.

*str*<br/>
[out] Biçimlendirilmiş dosya boyutunu içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Olduğunda bir [CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) nesne gereken bir dosyanın boyutunu görüntülemek, dosya boyutu bir dize biçimine dönüştürmeniz gerekir. `CMFCShellListCtrl` Bu dönüştürme yapmak için bu yöntemi kullanır. Varsayılan olarak, bu yöntem, dosya boyutunu bayt için kilobayt dönüştürür ve ardından boyutu dize olarak biçimlendirmek için geçerli yerel ayarı kullanır.

##  <a name="ongetitemicon"></a>  CMFCShellListCtrl::OnGetItemIcon

Framework bir kabuk liste öğesi ile ilişkilendirilen simgesini almak için bu yöntemi çağırır.

```
virtual int OnGetItemIcon(
    int iItem,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parametreler

*iItem*<br/>
[in] Öğe dizini.

*pItem*<br/>
[in] Öğenin açıkladığı LPAFX_SHELLITEMINFO parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simge görüntüsü dizini; işlev başarısız olursa -1.

### <a name="remarks"></a>Açıklamalar

Simge görüntü dizini, sistem görüntüsü listede temel alır.

Varsayılan olarak, bu yöntem dayanan *pItem* parametresi. Değerini *iItem* varsayılan uygulamasında kullanılmaz. Kullanabileceğiniz *iItem* özel davranışı uygulamak.

##  <a name="ongetitemtext"></a>  CMFCShellListCtrl::OnGetItemText

Framework bu yöntemi çağırır Kabuk öğenin metnini almanız gerekir.

```
virtual CString OnGetItemText(
    int iItem,
    int iColumn,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parametreler

*iItem*<br/>
[in] Öğe dizini.

*iColumn*<br/>
[in] İlgilendiğiniz sütun.

*pItem*<br/>
[in] Öğenin açıkladığı LPAFX_SHELLITEMINFO parametresi.

### <a name="return-value"></a>Dönüş Değeri

A `CString` öğesiyle ilişkili metin içeriyor.

### <a name="remarks"></a>Açıklamalar

Her öğe `CMFCShellListCtrl` nesnesi, bir veya daha fazla sütun metin olabilir. Framework bu yöntemi çağırdığında, ilgileniyor sütunu belirtir. Bu işlev bir el ile çağırırsanız, ilgilendiğiniz sütun de belirtmeniz gerekir.

Varsayılan olarak, bu yöntem dayanan *pItem* , işlenecek öğe belirlemek için parametre. Değerini *iItem* varsayılan uygulamasında kullanılmaz.

##  <a name="onsetcolumns"></a>  CMFCShellListCtrl::OnSetColumns

Sütun adlarını ayarladığında framework bu yöntemi çağırır.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, çerçeve dört sütun oluşturur. bir `CMFCShellListCtrl` nesne. Bu sütunların adları **adı**, **boyutu**, **türü**, ve **değiştirilen**. Sütunları ve adları sayısını özelleştirmek için bu yöntemi geçersiz kılabilirsiniz.

##  <a name="refresh"></a>  CMFCShellListCtrl::Refresh

Yenilenir ve halinde yeniden boyar [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesne.

```
virtual HRESULT Refresh();
```

### <a name="return-value"></a>Dönüş Değeri

`S_OK` başarılıysa; Aksi takdirde bir hata değeri.

### <a name="remarks"></a>Açıklamalar

Tarafından görüntülenen öğelerin listesini yenilemek için bu yöntemi çağırın `CMFCShellListCtrl` nesne.

##  <a name="setitemtypes"></a>  CMFCShellListCtrl::SetItemTypes

Listelenen öğelerin türünü ayarlar [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesne.

```
void SetItemTypes(SHCONTF nTypes);
```

### <a name="parameters"></a>Parametreler

*nTypes*<br/>
[in] Bir liste öğesi türlerinden `CMFCShellListCtrl` nesne destekler.

### <a name="remarks"></a>Açıklamalar

Öğe türleri listesi hakkında daha fazla bilgi için bkz. [SHCONTF](/windows/desktop/api/shobjidl_core/ne-shobjidl_core-_shcontf).

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl Sınıfı](../../mfc/reference/cmfclistctrl-class.md)<br/>
[CMFCShellTreeCtrl Sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md)
