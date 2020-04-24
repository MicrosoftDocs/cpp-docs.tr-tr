---
title: CMFCShellListCtrl Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 445556535217b0887a02227a0773c287911922a2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753480"
---
# <a name="cmfcshelllistctrl-class"></a>CMFCShellListCtrl Sınıfı

Sınıf, `CMFCShellListCtrl` Windows listesi denetimi işlevini sağlar ve kabuk öğelerinin listesini görüntüleme özelliğini ekleyerek genişletir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCShellListCtrl : public CMFCListCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|Sağlanan bir klasörde bulunan öğelerin listesini görüntüler.|
|[CMFCShellListCtrl::DisplayEbeveynKlasör](#displayparentfolder)|Şu anda görüntülenen klasörün üst öğesi olan klasörde bulunan öğelerin listesini görüntüler.|
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Kısayol menüsünü etkinleştirer veya devre dışı kılabilir.|
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|Geçerli klasörün yolunu alır.|
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|Geçerli klasörün adını alır.|
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|Geçerli liste denetim öğesinin PIDL'sini döndürür.|
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|Bir işaretçiyi geçerli Kabuk klasörüne döndürür.|
|[CMFCShellListCtrl::GetItemPath](#getitempath)|Bir öğenin metin yolunu döndürür.|
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|Liste denetimi tarafından görüntülenen Shell madde türlerini döndürür.|
|[CMFCShellListCtrl::Masaüstü](#isdesktop)|Şu anda seçili klasörün masaüstü klasörü olup olmadığını denetler.|
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|Çerçeve, iki öğeyi karşıladığında bu yöntemi çağırır. [(CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems)geçersiz kılar .)|
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|Çerçeve, liste denetimi tarafından görüntülenen dosya tarihini aldığında çağrılır.|
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|Çerçeve, liste denetiminin dosya boyutunu dönüştürdüğünde çağrılır.|
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|Çerçeve, liste denetim öğesisimgesini aldığında çağrılır.|
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|Çerçeve, liste denetim öğesinin metnini dönüştürdüğünde çağrılır.|
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|Sütunların adlarını ayarlarken çerçeve tarafından çağrılır.|
|[CMFCShellListCtrl::Yenile](#refresh)|Liste denetimini yeniler ve yeniden boyar.|
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|Liste denetimi tarafından görüntülenen öğelerin türünü ayarlar.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CMFCShellListCtrl` programınızın Windows kabuk öğelerini listelemesini sağlayarak [CMFCListCtrl Sınıfının](../../mfc/reference/cmfclistctrl-class.md) işlevselliğini genişletir. Kullanılan görüntü biçimi, Explorer penceresi için bir liste görünümüne benzer.

[CmFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesi, tam `CMFCShellListCtrl` bir Explorer penceresi oluşturmak için bir nesneyle ilişkilendirilebilir. Daha sonra, öğeyi `CMFCShellTreeCtrl` seçmek nesnenin `CMFCShellListCtrl` seçili öğenin içeriğini listelemesine neden olur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCShellListCtrl` nasıl oluşturulup görüntüleneceğini ve şu anda görüntülenen klasörün üst klasörünün nasıl görüntüleneceğini gösterir. Bu kod parçacığı [Explorer örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_2.cpp)]
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_3.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Clistctrl](../../mfc/reference/clistctrl-class.md)

[CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

`CMFCShellListCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxshelllistCtrl.h

## <a name="cmfcshelllistctrldisplayfolder"></a><a name="displayfolder"></a>CMFCShellListCtrl::DisplayFolder

Sağlanan klasörde bulunan öğelerin listesini görüntüler.

```
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
[içinde] Bir klasörün yolunu içeren bir dize.

*lpItemInfo*<br/>
[içinde] Görüntülenecek bir `LPAFX_SHELLITEMINFO` klasörü açıklayan bir yapıya işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; E_FAIL otherwise.

## <a name="cmfcshelllistctrldisplayparentfolder"></a><a name="displayparentfolder"></a>CMFCShellListCtrl::DisplayEbeveynKlasör

[CmFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesini güncellenince, şu anda görüntülenen klasörün üst klasörünü görüntüler.

```
virtual HRESULT DisplayParentFolder();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; E_FAIL otherwise.

## <a name="cmfcshelllistctrlenableshellcontextmenu"></a><a name="enableshellcontextmenu"></a>CMFCShellListCtrl::EnableShellContextMenu

Kısayol menüsünü etkinleştiri.

```cpp
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Çerçevenin kısayol menüsünü etkinleştirip etkinleştirmediğini belirten bir Boolean.

## <a name="cmfcshelllistctrlgetcurrentfolder"></a><a name="getcurrentfolder"></a>CMFCShellListCtrl::GetCurrentFolder

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinde şu anda seçili klasörün yolunu alır.

```
BOOL GetCurrentFolder(CString& strPath) const;
```

### <a name="parameters"></a>Parametreler

*strPath*<br/>
[çıkış] Yöntemin yolu yazdığı dize parametresine yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; 0 aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CMFCShellListCtrl`'de seçili bir klasör yoksa başarısız olur.

## <a name="cmfcshelllistctrlgetcurrentfoldername"></a><a name="getcurrentfoldername"></a>CMFCShellListCtrl::GetCurrentFolderName

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinde şu anda seçili klasörün adını alır.

```
BOOL GetCurrentFolderName(CString& strName) const;
```

### <a name="parameters"></a>Parametreler

*strName*<br/>
[çıkış] Yöntemin adı yazdığı dize parametresine yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; 0 aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CMFCShellListCtrl`'de seçili bir klasör yoksa başarısız olur.

## <a name="cmfcshelllistctrlgetcurrentitemidlist"></a><a name="getcurrentitemidlist"></a>CMFCShellListCtrl::GetCurrentItemIdList

Şu anda seçili öğenin PIDL'sini döndürür.

```
LPITEMIDLIST GetCurrentItemIdList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğenin PIDL'si.

## <a name="cmfcshelllistctrlgetcurrentshellfolder"></a><a name="getcurrentshellfolder"></a>CMFCShellListCtrl::GetCurrentShellFolder

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinde şu anda seçili öğeiçin bir işaretçi alır.

```
const IShellFolder* GetCurrentShellFolder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili nesne için [IShellFolder Arabirimine](/windows/win32/api/shobjidl_core/nn-shobjidl_core-ishellfolder) işaretçi.

### <a name="remarks"></a>Açıklamalar

Şu anda nesne seçili değilse, bu yöntem NULL döndürür.

## <a name="cmfcshelllistctrlgetitempath"></a><a name="getitempath"></a>CMFCShellListCtrl::GetItemPath

Bir öğenin yolunu alır.

```
BOOL GetItemPath(
    CString& strPath,
    int iItem) const;
```

### <a name="parameters"></a>Parametreler

*strPath*<br/>
[çıkış] Yolu alan bir dize için bir başvuru.

*iÖğe*<br/>
[içinde] Liste öğesinin dizini.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

*iItem* tarafından sağlanan dizin, [CMFCShellListCtrl Sınıf](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi tarafından görüntülenen öğeleri temel almaktadır.

## <a name="cmfcshelllistctrlgetitemtypes"></a><a name="getitemtypes"></a>CMFCShellListCtrl::GetItemTypes

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi tarafından görüntülenen öğelerin türünü döndürür.

```
SHCONTF GetItemTypes() const;
```

### <a name="return-value"></a>Dönüş Değeri

'de `CMFCShellListCtrl`listelenen maddelerin türünü içeren bir [SHCONTF](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf) değeri

### <a name="remarks"></a>Açıklamalar

Bir listelenen öğelerin türünü `CMFCShellListCtrl`ayarlamak için, [CMFCShellListCtrl arayın::SetItemTypes](#setitemtypes).

## <a name="cmfcshelllistctrlisdesktop"></a><a name="isdesktop"></a>CMFCShellListCtrl::Masaüstü

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinde görüntülenen klasörün masaüstü klasörü olup olmadığını belirler.

```
BOOL IsDesktop() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntülenen klasör masaüstü klasörü ise TRUE; YANLIŞ aksi takdirde.

## <a name="cmfcshelllistctrloncompareitems"></a><a name="oncompareitems"></a>CMFCShellListCtrl::OnCompareItems

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>Parametreler

[içinde] *lParam1*<br/>
[içinde] *lParam2*<br/>
[içinde] *iSütun*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcshelllistctrlonformatfiledate"></a><a name="onformatfiledate"></a>CMFCShellListCtrl::OnFormatFileDate

Çerçeve, bir nesneyle ilişkili tarihi bir dize dönüştürmesi gerektiğinde bu yöntemi çağırır.

```
virtual void OnFormatFileDate(
    const CTime& tmFile,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*tmDosya*<br/>
[içinde] Bir dosyayla ilişkili tarih.

*Str*<br/>
[çıkış] Biçimlendirilmiş dosya tarihini içeren bir dize.

### <a name="remarks"></a>Açıklamalar

[CMFCShellListCtrl Class](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi bir dosyayla ilişkili tarihi görüntülediğinde, bu tarihi bir dize biçimine dönüştürmesi gerekir. Bu `CMFCShellListCtrl` dönüştürme yapmak için bu yöntemi kullanır. Varsayılan olarak, bu yöntem, tarihi bir dize olarak biçimlendirmek için geçerli yerel alanı kullanır.

## <a name="cmfcshelllistctrlonformatfilesize"></a><a name="onformatfilesize"></a>CMFCShellListCtrl::OnFormatFileSize

Çerçeve, bir nesnenin boyutunu bir dize dönüştürdüğünde bu yöntemi çağırır.

```
virtual void OnFormatFileSize(
    long lFileSize,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*lFileSize*<br/>
[içinde] Çerçevenin göstereceği dosyanın boyutu.

*Str*<br/>
[çıkış] Biçimlendirilmiş dosya boyutunu içeren bir dize.

### <a name="remarks"></a>Açıklamalar

[CMFCShellListCtrl Class](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinin dosya boyutunu görüntülemesi gerektiğinde, dosya boyutunu dize biçimine dönüştürmesi gerekir. Bu `CMFCShellListCtrl` dönüştürme yapmak için bu yöntemi kullanır. Varsayılan olarak, bu yöntem dosya boyutunu baytlardan kilobaytlara dönüştürür ve ardından boyutu dize biçimlendirmek için geçerli yerel alanı kullanır.

## <a name="cmfcshelllistctrlongetitemicon"></a><a name="ongetitemicon"></a>CMFCShellListCtrl::OnGetItemIcon

Çerçeve, kabuk listesi öğesi ile ilişkili simgeyi almak için bu yöntemi çağırır.

```
virtual int OnGetItemIcon(
    int iItem,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parametreler

*iÖğe*<br/>
[içinde] Madde dizini.

*pItem*<br/>
[içinde] Maddeyi açıklayan LPAFX_SHELLITEMINFO bir parametre.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simge görüntüsünün dizini; -1 fonksiyon başarısız olursa.

### <a name="remarks"></a>Açıklamalar

Simge görüntü dizini sistem görüntü listesini temel almaktadır.

Varsayılan olarak, bu yöntem *pItem* parametreye dayanır. *iItem* değeri varsayılan uygulamada kullanılmaz. özel davranış uygulamak için *iItem'i* kullanabilirsiniz.

## <a name="cmfcshelllistctrlongetitemtext"></a><a name="ongetitemtext"></a>CMFCShellListCtrl::OnGetItemText

Bir kabuk öğesinin metnini alması gerektiğinde çerçeve bu yöntemi çağırır.

```
virtual CString OnGetItemText(
    int iItem,
    int iColumn,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parametreler

*iÖğe*<br/>
[içinde] Madde dizini.

*ıcolumn*<br/>
[içinde] İlgi sütunu.

*pItem*<br/>
[içinde] Maddeyi açıklayan LPAFX_SHELLITEMINFO bir parametre.

### <a name="return-value"></a>Dönüş Değeri

Maddeyle ilişkili metni içeren a. `CString`

### <a name="remarks"></a>Açıklamalar

Nesnedeki her `CMFCShellListCtrl` öğenin bir veya daha fazla sütunda metni olabilir. Çerçeve bu yöntemi aradığında, ilgilendiği sütunu belirtir. Bu işlevi el ile ararsanız, ilgilendiğiniz sütunu da belirtmeniz gerekir.

Varsayılan olarak, bu yöntem, hangi maddenin işlenmesi gerektiğini belirlemek için *pItem* parametresine dayanır. *iItem* değeri varsayılan uygulamada kullanılmaz.

## <a name="cmfcshelllistctrlonsetcolumns"></a><a name="onsetcolumns"></a>CMFCShellListCtrl::OnSetColumns

Çerçeve, sütunların adlarını ayarlarken bu yöntemi çağırır.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, çerçeve bir `CMFCShellListCtrl` nesnede dört sütun oluşturur. Bu sütunların adları **Ad**, **Boyut**, **Tür**ve **Modifiye**. Sütun sayısını ve adlarını özelleştirmek için bu yöntemi geçersiz kılabilirsiniz.

## <a name="cmfcshelllistctrlrefresh"></a><a name="refresh"></a>CMFCShellListCtrl::Yenile

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesini yeniler ve yeniden boyar.

```
virtual HRESULT Refresh();
```

### <a name="return-value"></a>Dönüş Değeri

`S_OK`başarılı olursa; aksi takdirde bir hata değeri.

### <a name="remarks"></a>Açıklamalar

`CMFCShellListCtrl` Nesne tarafından görüntülenen öğelerin listesini yenilemek için bu yöntemi arayın.

## <a name="cmfcshelllistctrlsetitemtypes"></a><a name="setitemtypes"></a>CMFCShellListCtrl::SetItemTypes

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinde listelenen öğelerin türünü ayarlar.

```cpp
void SetItemTypes(SHCONTF nTypes);
```

### <a name="parameters"></a>Parametreler

*nTypes*<br/>
[içinde] Nesnenin desteklediği madde `CMFCShellListCtrl` türlerinin listesi.

### <a name="remarks"></a>Açıklamalar

Madde türleri listesi hakkında daha fazla bilgi için [SHCONTF'ye](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl Sınıfı](../../mfc/reference/cmfclistctrl-class.md)<br/>
[CMFCShellTreeTreeCtrl Sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md)
