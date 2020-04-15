---
title: CMFCRibbonComboBox Sınıfı
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
ms.openlocfilehash: 5846b1c5590a756f0a0820583af3d0b159968ea2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375236"
---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox Sınıfı

Sınıf, `CMFCRibbonComboBox` şerit çubuğuna, şerit paneline veya şerit açılır menüsüne ekleyebileceğiniz bir açılan kutu denetimi uygular.

## <a name="syntax"></a>Sözdizimi

```cpp
class CMFCRibbonComboBox : public CMFCRibbonEdit
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|CMFCRibbonComboBox nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonComboBox::Öğe Ekle](#additem)|Liste kutusuna benzersiz bir öğe ekler.|
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|Liste kutusundan belirtilen bir öğeyi siler.|
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|Liste kutusunun aşağı düştüğünde boyutunu değiştirip değiştiremeyeceğini belirtir.|
|[CMFCRibbonComboBox::FindItem](#finditem)|Liste kutusunda belirtilen dizeyle eşleşen ilk öğenin dizinini döndürür.|
|[CMFCRibbonComboBox::GetCount](#getcount)|Liste kutusundaki öğe sayısını döndürür.|
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|Liste kutusunda şu anda seçili öğenin dizinini alır.|
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|Liste kutusu düşürüldüğünde liste kutusunun yüksekliğini alır.|
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|Açılan kutunun boyutunu ara modda görüntülendiği gibi döndürür.|
|[CMFCRibbonComboBox::GetItem](#getitem)|Liste kutusunda belirtilen bir dizinde bir öğeyle ilişkili dizeyi döndürür.|
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|Liste kutusunda belirtilen bir dizinde bir maddeyle ilişkili verileri döndürür.|
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|Denetimin bir denetim kutusu bulunup içermediğini gösterir.|
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|Liste kutusunun yeniden boyutlandırılıp yeniden boyutlandırılamadığını gösterir.|
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|Kullanıcı liste kutusunda bir öğe seçtiğinde çerçeve tarafından çağrılır.|
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|Liste kutusundaki tüm öğeleri siler ve düzen kutusunu temizler.|
|[CMFCRibbonComboBox::SelectItem](#selectitem)|Liste kutusundabir öğe seçer.|
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|Liste kutusunun yüksekliğini aşağı bırakıldığında ayarlar.|

## <a name="remarks"></a>Açıklamalar

Şerit açılan kutu, kullanıcı tarafından düzenlenebilen statik bir etiket veya etiketle birlikte bir liste kutusundan oluşur. Şerit açılan kutunuzu oluştururken hangi türü istediğinizi belirtmeniz gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCRibbonComboBox` nasıl oluşturup, açılan kutuya bir öğe eklemenin, açılan kutudaki bir öğenin nasıl seçilmeye ve panele açılan kutunun nasıl ekleyeceğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[Cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribboncombobox.h

## <a name="cmfcribboncomboboxadditem"></a><a name="additem"></a>CMFCRibbonComboBox::Öğe Ekle

Liste kutusuna benzersiz bir öğe ekler.

```cpp
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parametreler

*lpszItem*<br/>
[içinde] Eklenecek öğenin dizesi.

*Dwdata*<br/>
[içinde] Eklenecek öğeyle ilişkili veriler.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin sıfır tabanlı dizin.

## <a name="cmfcribboncomboboxcmfcribboncombobox"></a><a name="cmfcribboncombobox"></a>CMFCRibbonComboBox::CMFCRibbonComboBox

Bir `CMFCRibbonComboBox` nesne inşa eder.

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

*Nıd*<br/>
[içinde] Açılan kutunun kimliği.

*bHasEditBox*<br/>
[içinde] Denetim içinde bir edit kutusu istiyorsanız DOĞRU; YANLIŞ aksi takdirde.

*Nwidth*<br/>
[içinde] Açılan kutunun piksel genişliği; veya varsayılan genişlik için -1.

*lpszEtiket*<br/>
[içinde] Açılan kutunun ekran etiketi.

*nImage*<br/>
[içinde] Açılan kutunun küçük görüntü dizini.

### <a name="remarks"></a>Açıklamalar

Varsayılan genişlik 108 pikseldir.

## <a name="cmfcribboncomboboxdeleteitem"></a><a name="deleteitem"></a>CMFCRibbonComboBox::DeleteItem

Liste kutusundan belirtilen bir öğeyi siler.

```cpp
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Silinecek öğenin sıfır tabanlı dizin.

*Dwdata*<br/>
[içinde] Silinecek öğeyle ilişkili veriler.

*lpszMetin*<br/>
[içinde] Silinecek öğenin dizesi. Aynı dizeile birden çok öğe varsa, ilk öğe silinir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe silinmişse TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxenabledropdownlistresize"></a><a name="enabledropdownlistresize"></a>CMFCRibbonComboBox::EnableDropDownListResize

Liste kutusunun aşağı düştüğünde boyutunu değiştirip değiştiremeyeceğini belirtir.

```cpp
void EnableDropDownListResize(BOOL bEnable=FALSE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] DOĞRU yeniden boyutlandırma sağlamak için; Yeniden boyutlandırmayı devre dışı bırakabilmek için YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Yeniden boyutlandırma etkinleştirildiğinde, liste kutusu görüntülediği öğelere uyacak şekilde boyutunu değiştirir.

## <a name="cmfcribboncomboboxfinditem"></a><a name="finditem"></a>CMFCRibbonComboBox::FindItem

Liste kutusunda belirtilen dizeyle eşleşen ilk öğenin dizinini döndürür.

```cpp
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
[içinde] Liste kutusundaki bir öğenin dizesi.

### <a name="return-value"></a>Dönüş Değeri

Maddenin sıfır tabanlı dizin; veya -1 öğe bulunamazsa.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxgetcount"></a><a name="getcount"></a>CMFCRibbonComboBox::GetCount

Liste kutusundaki öğe sayısını döndürür.

```cpp
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusundaki öğe sayısı veya liste kutusunda öğe yoksa 0.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxgetcursel"></a><a name="getcursel"></a>CMFCRibbonComboBox::GetCurSel

Liste kutusunda şu anda seçili öğenin dizinini alır.

```cpp
int GetCurSel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunda şu anda seçili öğenin sıfır tabanlı dizin; veya -1 öğe seçili değilse.

## <a name="cmfcribboncomboboxgetdropdownheight"></a><a name="getdropdownheight"></a>CMFCRibbonComboBox::GetDropDownHeight

Liste kutusu düşürüldüğünde liste kutusunun yüksekliğini alır.

```cpp
int GetDropDownHeight();
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusunun yüksekliği, piksel olarak.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxgetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonComboBox::GetIntermediateSize

Açılan kutunun boyutunu ara modda görüntülendiği gibi döndürür.

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Açılan kutu için aygıt bağlamını işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Açılan kutunun boyutu.

### <a name="remarks"></a>Açıklamalar

Döndürülen boyut, küçük görüntüler görüntülediğinde açılan kutunun boyutuna bağlıdır.

## <a name="cmfcribboncomboboxgetitem"></a><a name="getitem"></a>CMFCRibbonComboBox::GetItem

Liste kutusunda belirtilen bir dizinde bir öğeyle ilişkili dizeyi döndürür.

```cpp
LPCTSTR GetItem(int iIndex) const;
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Liste kutusundaki bir öğenin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Öğeyle ilişkili dize için bir işaretçi; aksi takdirde, dizin parametresi geçersizse veya dizin parametresi -1 ise ve açılan kutuda seçili öğe yoksa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxgetitemdata"></a><a name="getitemdata"></a>CMFCRibbonComboBox::GetItemData

Liste kutusunda belirtilen bir dizinde bir maddeyle ilişkili verileri döndürür.

```cpp
DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Liste kutusundaki bir öğenin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Maddeyle ilişkili veriler; veya madde yoksa veya dizin parametresi -1 ise ve liste kutusunda seçili öğe yoksa 0.

## <a name="cmfcribboncomboboxhaseditbox"></a><a name="haseditbox"></a>CMFCRibbonComboBox::HasEditBox

Denetimin bir denetim kutusu bulunup içermediğini gösterir.

```cpp
BOOL HasEditBox() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetim bir denetim kutusu içeriyorsa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxisresizedropdownlist"></a><a name="isresizedropdownlist"></a>CMFCRibbonComboBox::IsResizeDropDownList

Liste kutusunun yeniden boyutlandırılıp yeniden boyutlandırılamadığını gösterir.

```cpp
BOOL IsResizeDropDownList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste kutusu yeniden boyutlandırılabilirse DOĞRU; aksi takdirde YANLIŞ. [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)

### <a name="remarks"></a>Açıklamalar

[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize) yöntemini kullanarak liste kutusunu yeniden boyutlandırmayı etkinleştirebilirsiniz.

## <a name="cmfcribboncomboboxonselectitem"></a><a name="onselectitem"></a>CMFCRibbonComboBox::OnSelectItem

Kullanıcı liste kutusundabir öğe seçtiğinde çerçeve tarafından çağrılır.

```cpp
virtual void OnSelectItem(int nItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
[içinde] Seçili öğenin dizin.

### <a name="remarks"></a>Açıklamalar

Kullanıcı giriş seçimini işlemek istiyorsanız bu yöntemi geçersiz kılın.

## <a name="cmfcribboncomboboxremoveallitems"></a><a name="removeallitems"></a>CMFCRibbonComboBox::RemoveAllItems

Liste kutusundaki tüm öğeleri siler ve düzen kutusunu temizler.

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxselectitem"></a><a name="selectitem"></a>CMFCRibbonComboBox::SelectItem

Liste kutusundabir öğe seçer.

```cpp
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Liste kutusundaki bir öğenin sıfır tabanlı dizin.

*Dwdata*<br/>
[içinde] Liste kutusundaki bir öğeyle ilişkili veriler.

*lpszMetin*<br/>
[içinde] Liste kutusundaki bir öğenin dizesi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olsaydı DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncomboboxsetdropdownheight"></a><a name="setdropdownheight"></a>CMFCRibbonComboBox::SetDropDownHeight

Liste kutusunun yüksekliğini aşağı bırakıldığında ayarlar.

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>Parametreler

*Nheight*<br/>
[içinde] Liste kutusunun yüksekliği, piksel olarak.

### <a name="remarks"></a>Açıklamalar

Varsayılan yükseklik 150 pikseldir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonEdit Sınıfı](../../mfc/reference/cmfcribbonedit-class.md)
