---
title: CMFCShellListCtrl sınıfı
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
ms.openlocfilehash: 02d4883c6b5445515d891c5e76ccf10b6bb35bba
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504917"
---
# <a name="cmfcshelllistctrl-class"></a>CMFCShellListCtrl sınıfı

Sınıfı `CMFCShellListCtrl` , Windows liste denetimi işlevselliği sağlar ve kabuk öğelerinin listesini görüntüleme özelliğini ekleyerek genişletir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCShellListCtrl : public CMFCListCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCShellListCtrl::D isplayFolder](#displayfolder)|Bir belirtilen klasörde bulunan öğelerin listesini görüntüler.|
|[CMFCShellListCtrl::D isplayParentFolder](#displayparentfolder)|Görüntülenmekte olan klasörün üst öğesi olan klasörde bulunan öğelerin listesini görüntüler.|
|[CMFCShellListCtrl:: EnableShellContextMenu](#enableshellcontextmenu)|Kısayol menüsünü etkinleştirilir veya devre dışı bırakır.|
|[CMFCShellListCtrl:: GetCurrentFolder](#getcurrentfolder)|Geçerli klasörün yolunu alır.|
|[CMFCShellListCtrl:: GetCurrentFolderName](#getcurrentfoldername)|Geçerli klasörün adını alır.|
|[CMFCShellListCtrl:: Getcurrentıtemidlist](#getcurrentitemidlist)|Geçerli liste denetim öğesinin PIDL değerini döndürür.|
|[CMFCShellListCtrl:: GetCurrentShellFolder](#getcurrentshellfolder)|Geçerli kabuk klasörü için bir işaretçi döndürür.|
|[CMFCShellListCtrl:: Getıtempgunlum](#getitempath)|Bir öğenin metinsel yolunu döndürür.|
|[CMFCShellListCtrl:: Getıtemtypes](#getitemtypes)|Liste denetimi tarafından görüntülenen kabuk öğesi türlerini döndürür.|
|[CMFCShellListCtrl:: ısdesktop](#isdesktop)|O anda seçili olan klasörün masaüstü klasörü olup olmadığını denetler.|
|[CMFCShellListCtrl:: OnCompareItems](#oncompareitems)|Framework iki öğeyi karşılaştırırken bu yöntemi çağırır. ( [CMFCListCtrl:: OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).) öğesini geçersiz kılar|
|[CMFCShellListCtrl:: OnFormatFileDate](#onformatfiledate)|Çerçeve liste denetimi tarafından görünen dosya tarihini aldığında çağırılır.|
|[CMFCShellListCtrl:: OnFormatFileSize](#onformatfilesize)|Çerçeve liste denetiminin dosya boyutunu dönüştürdüğünde çağırılır.|
|[CMFCShellListCtrl:: OnGetItemIcon](#ongetitemicon)|Framework bir liste denetim öğesi simgesini aldığında çağırılır.|
|[CMFCShellListCtrl:: Ongetıtemtext](#ongetitemtext)|Çerçeve liste denetim öğesinin metnini dönüştürdüğünde çağırılır.|
|[CMFCShellListCtrl:: OnSetColumns](#onsetcolumns)|Sütunların adlarını ayarladığında Framework tarafından çağırılır.|
|[CMFCShellListCtrl:: Refresh](#refresh)|Liste denetimini yeniler ve yeniden boyar.|
|[CMFCShellListCtrl:: SetItemTypes](#setitemtypes)|Liste denetimi tarafından görünen öğelerin türünü ayarlar.|

## <a name="remarks"></a>Açıklamalar

Sınıfı, programınızın Windows kabuğu öğelerini listelemelerine olanak tanıyarak [CMFCListCtrl sınıfının](../../mfc/reference/cmfclistctrl-class.md) işlevselliğini genişletir. `CMFCShellListCtrl` Kullanılan görüntüleme biçimi, bir Gezgin penceresi için liste görünümü ' ne benzer.

Bir [cmfcshelltreeci](../../mfc/reference/cmfcshelltreectrl-class.md) nesnesi bir `CMFCShellListCtrl` nesne ile ilişkilendirilebilen bir Gezgin penceresi oluşturur. Ardından, içindeki `CMFCShellTreeCtrl` bir öğenin seçilmesi `CMFCShellListCtrl` nesnenin seçili öğenin içeriğini listemasına neden olur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCShellListCtrl` sınıfının bir nesnesinin nasıl oluşturulduğunu ve görüntülenmekte olan klasörün üst klasörünü nasıl görüntüleneceğini gösterir. Bu kod parçacığı, [Gezgin örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

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

**Üstbilgi:** afxshelllistctrl. h

##  <a name="displayfolder"></a>CMFCShellListCtrl::D isplayFolder

Belirtilen klasörde bulunan öğelerin listesini görüntüler.

```
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
'ndaki Bir klasörün yolunu içeren bir dize.

*Lpiteınfo*<br/>
'ndaki Görüntülenecek klasörü açıklayan bir `LPAFX_SHELLITEMINFO` yapıya yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde E_FAıL.

##  <a name="displayparentfolder"></a>CMFCShellListCtrl::D isplayParentFolder

O anda görüntülenen klasörün üst klasörünü göstermek için [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesini güncelleştirir.

```
virtual HRESULT DisplayParentFolder();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde E_FAıL.

##  <a name="enableshellcontextmenu"></a>CMFCShellListCtrl:: EnableShellContextMenu

Kısayol menüsünü etkinleştirilir.

```
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Çerçevenin kısayol menüsünü etkinleştirilip etkinleştirilmediğini belirten bir Boole değeri.

##  <a name="getcurrentfolder"></a>CMFCShellListCtrl:: GetCurrentFolder

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinde seçili olan klasörün yolunu alır.

```
BOOL GetCurrentFolder(CString& strPath) const;
```

### <a name="parameters"></a>Parametreler

*strPath*<br/>
dışı Yöntemin yolu yazdığı dize parametresine yönelik başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; 0 Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

İçinde hiçbir klasör seçili değilse bu yöntem başarısız olur `CMFCShellListCtrl`.

##  <a name="getcurrentfoldername"></a>CMFCShellListCtrl:: GetCurrentFolderName

Şu anda seçili olan klasörün adını [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinde alır.

```
BOOL GetCurrentFolderName(CString& strName) const;
```

### <a name="parameters"></a>Parametreler

*strName*<br/>
dışı Yöntemin adı yazdığı dize parametresine yönelik başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; 0 Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

İçinde hiçbir klasör seçili değilse bu yöntem başarısız olur `CMFCShellListCtrl`.

##  <a name="getcurrentitemidlist"></a>CMFCShellListCtrl:: Getcurrentıtemidlist

Şu anda seçili olan öğenin PIDL değerini döndürür.

```
LPITEMIDLIST GetCurrentItemIdList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli öğenin PIDL öğesi.

##  <a name="getcurrentshellfolder"></a>CMFCShellListCtrl:: GetCurrentShellFolder

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinde seçili olan öğeye yönelik bir işaretçi alır.

```
const IShellFolder* GetCurrentShellFolder() const;
```

### <a name="return-value"></a>Dönüş Değeri

Seçili nesne için [IShellFolder arabirimine](/windows/win32/api/shobjidl_core/nn-shobjidl_core-ishellfolder) yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, şu anda seçili bir nesne yoksa NULL değerini döndürür.

##  <a name="getitempath"></a>CMFCShellListCtrl:: Getıtempgunlum

Bir öğenin yolunu alır.

```
BOOL GetItemPath(
    CString& strPath,
    int iItem) const;
```

### <a name="parameters"></a>Parametreler

*strPath*<br/>
dışı Yolu alan bir dizeye başvuru.

*IItem*<br/>
'ndaki Liste öğesinin dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

*Iitem* tarafından sağlanan dizin, şu anda [CMFCShellListCtrl sınıf](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi tarafından görüntülenen öğeleri temel alır.

##  <a name="getitemtypes"></a>CMFCShellListCtrl:: Getıtemtypes

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi tarafından görünen öğelerin türünü döndürür.

```
SHCONTF GetItemTypes() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçinde`CMFCShellListCtrl`listelenen öğelerin türünü Içeren bir [shcontenf](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf) değeri.

### <a name="remarks"></a>Açıklamalar

İçinde `CMFCShellListCtrl`listelenen öğelerin türünü ayarlamak için [CMFCShellListCtrl:: SetItemTypes](#setitemtypes)çağırın.

##  <a name="isdesktop"></a>CMFCShellListCtrl:: ısdesktop

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinde görüntülenen klasörün masaüstü klasörü olup olmadığını belirler.

```
BOOL IsDesktop() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görüntülenmiş klasör masaüstü klasörse doğru; Aksi takdirde FALSE.

##  <a name="oncompareitems"></a>CMFCShellListCtrl:: OnCompareItems

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC\\atlmfc\\\\src MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>Parametreler

'ndaki *lParam1*<br/>
'ndaki *lParam2*<br/>
'ndaki *ıolumn*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onformatfiledate"></a>CMFCShellListCtrl:: OnFormatFileDate

Çerçeve, bir nesneyle ilişkili tarihi bir dizeye dönüştürmelidir, bu yöntemi çağırır.

```
virtual void OnFormatFileDate(
    const CTime& tmFile,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*tmFile*<br/>
'ndaki Bir dosyayla ilişkili tarih.

*üstbilgisine*<br/>
dışı Biçimlendirilen dosya tarihini içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Bir [CMFCShellListCtrl sınıf](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesi bir dosyayla ilişkili tarihi görüntülediğinde, bu tarihi dize biçimine dönüştürmelidir. Bu dönüştürmeyi yapmak için bu yöntemi kullanır.`CMFCShellListCtrl` Varsayılan olarak, bu yöntem tarihi bir dizeye biçimlendirmek için geçerli yerel ayarı kullanır.

##  <a name="onformatfilesize"></a>CMFCShellListCtrl:: OnFormatFileSize

Framework, bir nesnenin boyutunu bir dizeye dönüştürürken bu yöntemi çağırır.

```
virtual void OnFormatFileSize(
    long lFileSize,
    CString& str);
```

### <a name="parameters"></a>Parametreler

*lFileSize*<br/>
'ndaki Çerçevenin görüntüleyeceği dosyanın boyutu.

*üstbilgisine*<br/>
dışı Biçimlendirilen dosya boyutunu içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Bir [CMFCShellListCtrl sınıfı](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinin bir dosyanın boyutunu görüntülemesi gerektiğinde, dosyanın boyutunu dize biçimine dönüştürmesi gerekir. Bu dönüştürmeyi yapmak için bu yöntemi kullanır.`CMFCShellListCtrl` Varsayılan olarak, bu yöntem dosya boyutunu bayttan kilobayt olarak dönüştürür ve sonra boyutu dizeye biçimlendirmek için geçerli yerel ayarı kullanır.

##  <a name="ongetitemicon"></a>CMFCShellListCtrl:: OnGetItemIcon

Framework, bir kabuk listesi öğesiyle ilişkili simgeyi almak için bu yöntemi çağırır.

```
virtual int OnGetItemIcon(
    int iItem,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parametreler

*IItem*<br/>
'ndaki Öğe dizini.

*pItem*<br/>
'ndaki Öğeyi açıklayan bir LPAFX_SHELLITEMINFO parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simge resminin dizini. işlev başarısız olursa-1.

### <a name="remarks"></a>Açıklamalar

Simge görüntüsü dizini, sistem görüntüsü listesini temel alır.

Varsayılan olarak, bu yöntem *Pitem* parametresini kullanır. *IItem* değeri varsayılan uygulamada kullanılmaz. Özel davranışı uygulamak için *IItem* kullanabilirsiniz.

##  <a name="ongetitemtext"></a>CMFCShellListCtrl:: Ongetıtemtext

Framework, bir kabuk öğesinin metnini alması gerektiğinde bu yöntemi çağırır.

```
virtual CString OnGetItemText(
    int iItem,
    int iColumn,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Parametreler

*IItem*<br/>
'ndaki Öğe dizini.

*ıolumn*<br/>
'ndaki İlgilendiğiniz sütun.

*pItem*<br/>
'ndaki Öğeyi açıklayan bir LPAFX_SHELLITEMINFO parametresi.

### <a name="return-value"></a>Dönüş Değeri

Öğesiyle `CString` ilişkili metni içeren bir.

### <a name="remarks"></a>Açıklamalar

`CMFCShellListCtrl` Nesnedeki her öğe bir veya daha fazla sütunda metin içerebilir. Framework bu yöntemi çağırdığında, ilgilendiğiniz sütunu belirtir. Bu işlevi el ile çağırırsanız, ilgilendiğiniz sütunu da belirtmeniz gerekir.

Varsayılan olarak, bu yöntem hangi öğenin işleyeceğini belirleyen *pItem* parametresini kullanır. *IItem* değeri varsayılan uygulamada kullanılmaz.

##  <a name="onsetcolumns"></a>CMFCShellListCtrl:: OnSetColumns

Çerçeve, sütun adlarını ayarladığında bu yöntemi çağırır.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, çerçeve bir `CMFCShellListCtrl` nesnede dört sütun oluşturur. Bu sütunların adları **ad**, **Boyut**, **tür**ve **değiştirilir**. Sütun sayısını ve bunların adlarını özelleştirmek için bu yöntemi geçersiz kılabilirsiniz.

##  <a name="refresh"></a>CMFCShellListCtrl:: Refresh

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesini yeniler ve yeniden boyar.

```
virtual HRESULT Refresh();
```

### <a name="return-value"></a>Dönüş Değeri

`S_OK`başarılı olursa, Aksi takdirde bir hata değeri.

### <a name="remarks"></a>Açıklamalar

`CMFCShellListCtrl` Nesne tarafından görüntülenecek öğe listesini yenilemek için bu yöntemi çağırın.

##  <a name="setitemtypes"></a>CMFCShellListCtrl:: SetItemTypes

[CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) nesnesinde listelenen öğelerin türünü ayarlar.

```
void SetItemTypes(SHCONTF nTypes);
```

### <a name="parameters"></a>Parametreler

*Ntürler*<br/>
'ndaki `CMFCShellListCtrl` Nesnenin desteklediği öğe türlerinin listesi.

### <a name="remarks"></a>Açıklamalar

Öğe türlerinin listesi hakkında daha fazla bilgi için bkz. [Shcontenf](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl Sınıfı](../../mfc/reference/cmfclistctrl-class.md)<br/>
[CMFCShellTreeCtrl Sınıfı](../../mfc/reference/cmfcshelltreectrl-class.md)
