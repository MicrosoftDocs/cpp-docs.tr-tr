---
description: 'Daha fazla bilgi edinin: CMFCRibbonComboBox sınıfı'
title: CMFCRibbonComboBox sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
helpviewer_keywords:
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
ms.openlocfilehash: be4078145817d06fafddb76f2cefbd0df0083503
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293676"
---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox sınıfı

Sınıfı, şerit `CMFCRibbonComboBox` çubuğuna, şerit paneline veya Şerit açılan menüsüne ekleyebileceğiniz bir Birleşik giriş kutusu denetimi uygular.

## <a name="syntax"></a>Syntax

```cpp
class CMFCRibbonComboBox : public CMFCRibbonEdit
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonComboBox:: CMFCRibbonComboBox](#cmfcribboncombobox)|Bir CMFCRibbonComboBox nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonComboBox:: AddItem](#additem)|Liste kutusuna benzersiz bir öğe ekler.|
|[CMFCRibbonComboBox::D Eleteıtem](#deleteitem)|Liste kutusundan belirtilen bir öğeyi siler.|
|[CMFCRibbonComboBox:: EnableDropDownListResize](#enabledropdownlistresize)|Liste kutusunun, düştüğünde boyutu değiştiremeyeceğini belirtir.|
|[CMFCRibbonComboBox:: FindItem](#finditem)|Liste kutusundaki, belirtilen dizeyle eşleşen ilk öğenin dizinini döndürür.|
|[CMFCRibbonComboBox:: GetCount](#getcount)|Liste kutusundaki öğe sayısını döndürür.|
|[CMFCRibbonComboBox:: GetCurSel](#getcursel)|Liste kutusunda şu anda seçili olan öğenin dizinini alır.|
|[CMFCRibbonComboBox:: GetDropDownHeight](#getdropdownheight)|Liste kutusu kapatıldığında liste kutusunun yüksekliğini alır.|
|[CMFCRibbonComboBox:: GetIntermediateSize](#getintermediatesize)|Ara modda gösterildiği gibi Birleşik giriş kutusunun boyutunu döndürür.|
|[CMFCRibbonComboBox:: GetItem](#getitem)|Liste kutusunda belirtilen dizindeki bir öğeyle ilişkili dizeyi döndürür.|
|[CMFCRibbonComboBox:: GetItemData](#getitemdata)|Liste kutusunda belirtilen dizindeki bir öğeyle ilişkili verileri döndürür.|
|[CMFCRibbonComboBox:: HasEditBox](#haseditbox)|Denetimin bir düzenleme kutusu içerip içermediğini gösterir.|
|[CMFCRibbonComboBox:: IsResizeDropDownList](#isresizedropdownlist)|Liste kutusunun yeniden boyutlandırılıp boyutlandırılamayacağını gösterir.|
|[CMFCRibbonComboBox:: Onselectıtem](#onselectitem)|Kullanıcı liste kutusunda bir öğe seçtiğinde Framework tarafından çağırılır.|
|[CMFCRibbonComboBox:: Removeallıtems](#removeallitems)|Tüm öğeleri liste kutusundan siler ve düzenleme kutusunu temizler.|
|[CMFCRibbonComboBox:: SelectItem](#selectitem)|Liste kutusunda bir öğe seçer.|
|[CMFCRibbonComboBox:: SetDropDownHeight](#setdropdownheight)|Aşağı bırakıldığında liste kutusunun yüksekliğini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Şerit açılan kutusu, Kullanıcı tarafından düzenlenebilen statik bir etiketle veya etiketle birleştirilmiş bir liste kutusundan oluşur. Şerit açılan kutusunu oluştururken istediğiniz türü belirtmeniz gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu `CMFCRibbonComboBox` , Birleşik giriş kutusuna bir öğe eklemeyi, Birleşik giriş kutusunda bir öğe seçmenizi ve bir panele Birleşik giriş kutusu eklemeyi gösterir.

[!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbondüğmesi](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribboncombobox. h

## <a name="cmfcribboncomboboxadditem"></a><a name="additem"></a> CMFCRibbonComboBox:: AddItem

Liste kutusuna benzersiz bir öğe ekler.

```cpp
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parametreler

*lpszItem*<br/>
'ndaki Eklenecek öğenin dizesi.

*dwData*<br/>
'ndaki Eklenecek öğeyle ilişkili veriler.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin sıfır tabanlı dizini.

## <a name="cmfcribboncomboboxcmfcribboncombobox"></a><a name="cmfcribboncombobox"></a> CMFCRibbonComboBox:: CMFCRibbonComboBox

Bir `CMFCRibbonComboBox` nesnesi oluşturur.

```cpp
public:
CMFCRibbonComboBox(
    UINT nID,
    BOOL bHasEditBox=TRUE,
    Int nWidth=-1,
    LPCTSTR lpszLabel=NULL,
    Int nImage=-1);

protected:
CMFCRibbonComboBox();
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
'ndaki Birleşik giriş kutusunun KIMLIĞI.

*bHasEditBox*<br/>
'ndaki Denetim içinde bir düzenleme kutusu istiyorsanız TRUE; Aksi takdirde FALSE.

*nWidth*<br/>
'ndaki Birleşik giriş kutusunun piksel cinsinden genişliği; Varsayılan genişlik için-1.

*lpszLabel*<br/>
'ndaki Birleşik giriş kutusunun görüntüleme etiketi.

*Ngörüntü*<br/>
'ndaki Birleşik giriş kutusunun küçük resim dizini.

### <a name="remarks"></a>Açıklamalar

Varsayılan genişlik 108 pikseldir.

## <a name="cmfcribboncomboboxdeleteitem"></a><a name="deleteitem"></a> CMFCRibbonComboBox::D Eleteıtem

Liste kutusundan belirtilen bir öğeyi siler.

```cpp
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Silinecek öğenin sıfır tabanlı dizini.

*dwData*<br/>
'ndaki Silinecek öğeyle ilişkili veriler.

*lpszText*<br/>
'ndaki Silinecek öğenin dizesi. Aynı dizeye sahip birden fazla öğe varsa, ilk öğe silinir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe silinmişse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxenabledropdownlistresize"></a><a name="enabledropdownlistresize"></a> CMFCRibbonComboBox:: EnableDropDownListResize

Liste kutusunun, düştüğünde boyutu değiştiremeyeceğini belirtir.

```cpp
void EnableDropDownListResize(BOOL bEnable=FALSE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Yeniden boyutlandırmayı etkinleştirmek için TRUE; Yeniden boyutlandırmayı devre dışı bırakmak için FALSE.

### <a name="remarks"></a>Açıklamalar

Yeniden boyutlandırma etkin olduğunda, liste kutusu boyutu görüntülenen öğelere sığacak şekilde değişir.

## <a name="cmfcribboncomboboxfinditem"></a><a name="finditem"></a> CMFCRibbonComboBox:: FindItem

Liste kutusundaki, belirtilen dizeyle eşleşen ilk öğenin dizinini döndürür.

```cpp
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
'ndaki Liste kutusundaki bir öğenin dizesi.

### <a name="return-value"></a>Dönüş Değeri

Öğenin sıfır tabanlı dizini; veya öğe bulunmazsa-1.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxgetcount"></a><a name="getcount"></a> CMFCRibbonComboBox:: GetCount

Liste kutusundaki öğe sayısını döndürür.

```cpp
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki öğelerin sayısı veya liste kutusu hiçbir öğe içermiyorsa 0.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxgetcursel"></a><a name="getcursel"></a> CMFCRibbonComboBox:: GetCurSel

Liste kutusunda şu anda seçili olan öğenin dizinini alır.

```cpp
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunda şu anda seçili olan öğenin sıfır tabanlı dizini; veya hiçbir öğe seçilmediyse-1.

## <a name="cmfcribboncomboboxgetdropdownheight"></a><a name="getdropdownheight"></a> CMFCRibbonComboBox:: GetDropDownHeight

Liste kutusu kapatıldığında liste kutusunun yüksekliğini alır.

```cpp
int GetDropDownHeight();
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunun piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxgetintermediatesize"></a><a name="getintermediatesize"></a> CMFCRibbonComboBox:: GetIntermediateSize

Ara modda gösterildiği gibi Birleşik giriş kutusunun boyutunu döndürür.

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Birleşik giriş kutusu için bir cihaz bağlamı işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Birleşik giriş kutusunun boyutu.

### <a name="remarks"></a>Açıklamalar

Döndürülen boyut, küçük resimler görüntülediğinde Birleşik giriş kutusunun boyutuna göre belirlenir.

## <a name="cmfcribboncomboboxgetitem"></a><a name="getitem"></a> CMFCRibbonComboBox:: GetItem

Liste kutusunda belirtilen dizindeki bir öğeyle ilişkili dizeyi döndürür.

```cpp
LPCTSTR GetItem(int iIndex) const;
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Liste kutusundaki bir öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Öğeyle ilişkili dizeye yönelik bir işaretçi; Aksi takdirde, Index parametresi geçersizse veya Index parametresi-1 ise ve Birleşik giriş kutusunda seçili öğe yoksa NULL olur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxgetitemdata"></a><a name="getitemdata"></a> CMFCRibbonComboBox:: GetItemData

Liste kutusunda belirtilen dizindeki bir öğeyle ilişkili verileri döndürür.

```cpp
DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Liste kutusundaki bir öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Öğeyle ilişkili veriler; veya öğe yoksa 0 ise veya dizin parametresi-1 ise ve liste kutusunda seçili öğe yoksa.

## <a name="cmfcribboncomboboxhaseditbox"></a><a name="haseditbox"></a> CMFCRibbonComboBox:: HasEditBox

Denetimin bir düzenleme kutusu içerip içermediğini gösterir.

```cpp
BOOL HasEditBox() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim bir düzenleme kutusu içeriyorsa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxisresizedropdownlist"></a><a name="isresizedropdownlist"></a> CMFCRibbonComboBox:: IsResizeDropDownList

Liste kutusunun yeniden boyutlandırılıp boyutlandırılamayacağını gösterir.

```cpp
BOOL IsResizeDropDownList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusu yeniden boyutlandırılabiliyorsa TRUE; Aksi halde yanlış. [CMFCRibbonComboBox:: EnableDropDownListResize](#enabledropdownlistresize)

### <a name="remarks"></a>Açıklamalar

[CMFCRibbonComboBox:: EnableDropDownListResize](#enabledropdownlistresize) yöntemini kullanarak liste kutusu yeniden boyutlandırmayı etkinleştirebilirsiniz.

## <a name="cmfcribboncomboboxonselectitem"></a><a name="onselectitem"></a> CMFCRibbonComboBox:: Onselectıtem

Kullanıcı liste kutusunda bir öğe seçtiğinde Framework tarafından çağırılır.

```cpp
virtual void OnSelectItem(int nItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
'ndaki Seçili öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Bir kullanıcı girişi seçimini işlemek istiyorsanız bu yöntemi geçersiz kılın.

## <a name="cmfcribboncomboboxremoveallitems"></a><a name="removeallitems"></a> CMFCRibbonComboBox:: Removeallıtems

Tüm öğeleri liste kutusundan siler ve düzenleme kutusunu temizler.

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxselectitem"></a><a name="selectitem"></a> CMFCRibbonComboBox:: SelectItem

Liste kutusunda bir öğe seçer.

```cpp
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Liste kutusundaki bir öğenin sıfır tabanlı dizini.

*dwData*<br/>
'ndaki Liste kutusundaki bir öğeyle ilişkili veriler.

*lpszText*<br/>
'ndaki Liste kutusundaki bir öğenin dizesi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxsetdropdownheight"></a><a name="setdropdownheight"></a> CMFCRibbonComboBox:: SetDropDownHeight

Aşağı bırakıldığında liste kutusunun yüksekliğini ayarlar.

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>Parametreler

*nHeight*<br/>
'ndaki Liste kutusunun piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

Varsayılan yükseklik 150 pikseldir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonEdit sınıfı](../../mfc/reference/cmfcribbonedit-class.md)
