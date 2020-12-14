---
description: 'Daha fazla bilgi edinin: CVSListBox sınıfı'
title: CVSListBox sınıfı
ms.date: 11/19/2018
f1_keywords:
- CVSListBox
- AFXVSLISTBOX/CVSListBox
- AFXVSLISTBOX/CVSListBox::CVSListBox
- AFXVSLISTBOX/CVSListBox::AddItem
- AFXVSLISTBOX/CVSListBox::EditItem
- AFXVSLISTBOX/CVSListBox::GetCount
- AFXVSLISTBOX/CVSListBox::GetItemData
- AFXVSLISTBOX/CVSListBox::GetItemText
- AFXVSLISTBOX/CVSListBox::GetSelItem
- AFXVSLISTBOX/CVSListBox::RemoveItem
- AFXVSLISTBOX/CVSListBox::SelectItem
- AFXVSLISTBOX/CVSListBox::SetItemData
- AFXVSLISTBOX/CVSListBox::GetListHwnd
helpviewer_keywords:
- CVSListBox [MFC], CVSListBox
- CVSListBox [MFC], AddItem
- CVSListBox [MFC], EditItem
- CVSListBox [MFC], GetCount
- CVSListBox [MFC], GetItemData
- CVSListBox [MFC], GetItemText
- CVSListBox [MFC], GetSelItem
- CVSListBox [MFC], RemoveItem
- CVSListBox [MFC], SelectItem
- CVSListBox [MFC], SetItemData
- CVSListBox [MFC], GetListHwnd
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
ms.openlocfilehash: 6912eccd4cc8e7c78407d0cda0a0dc1305d0bde8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344984"
---
# <a name="cvslistbox-class"></a>CVSListBox sınıfı

`CVSListBox`Sınıfı, düzenlenebilir bir liste denetimini destekler.

## <a name="syntax"></a>Syntax

```
class CVSListBox : public CVSListBoxBase
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CVSListBox:: CVSListBox](#cvslistbox)|Bir `CVSListBox` nesnesi oluşturur.|
|`CVSListBox::~CVSListBox`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CVSListBox:: AddItem](#additem)|Liste denetimine bir dize ekler. (Geçersiz kılmalar `CVSListBoxBase::AddItem` .)|
|[CVSListBox:: EditItem](#edititem)|Bir liste denetim öğesi metni üzerinde bir düzenleme işlemi başlatır. (Geçersiz kılmalar `CVSListBoxBase::EditItem` .)|
|[CVSListBox:: GetCount](#getcount)|Düzenlenebilir liste denetimindeki dize sayısını alır. (Geçersiz kılmalar `CVSListBoxBase::GetCount` .)|
|[CVSListBox:: GetItemData](#getitemdata)|Düzenlenebilir bir liste denetim öğesiyle ilişkili uygulamaya özgü 32 bitlik bir değer alır. (Geçersiz kılmalar `CVSListBoxBase::GetItemData` .)|
|[CVSListBox:: GetItemText](#getitemtext)|Düzenlenebilir liste denetim öğesinin metnini alır. (Geçersiz kılmalar `CVSListBoxBase::GetItemText` .)|
|[CVSListBox:: Getselıdıtem](#getselitem)|Seçili olan öğenin sıfır tabanlı dizinini düzenlenebilir liste denetiminde alır. (Geçersiz kılmalar `CVSListBoxBase::GetSelItem` .)|
|`CVSListBox::PreTranslateMessage`|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini çevirir. Daha fazla bilgi ve Yöntem sözdizimi için bkz. [CWnd::P reTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz kılmalar `CVSListBoxBase::PreTranslateMessage` .)|
|[CVSListBox:: RemoveItem](#removeitem)|Düzenlenebilir liste denetiminden bir öğeyi kaldırır. (Geçersiz kılmalar `CVSListBoxBase::RemoveItem` .)|
|[CVSListBox:: SelectItem](#selectitem)|Düzenlenebilir bir liste denetim dizesi seçer. (Geçersiz kılmalar `CVSListBoxBase::SelectItem` .)|
|[CVSListBox:: SetItemData](#setitemdata)|Uygulamaya özgü 32 bitlik bir değeri düzenlenebilir liste denetim öğesiyle ilişkilendirir. (Geçersiz kılmalar `CVSListBoxBase::SetItemData` .)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CVSListBox:: GetListHwnd](#getlisthwnd)|Geçerli katıştırılmış liste görünümü denetimine yönelik tanıtıcıyı döndürür.|

## <a name="remarks"></a>Açıklamalar

`CVSListBox`Sınıfı, kullanıcının liste denetimindeki öğeleri oluşturmasını, değiştirmesini, silmesini veya yeniden düzenlemesini sağlayan bir düzenleme düğmeleri kümesi sağlar.

Düzenlenebilir liste denetiminin bir resmi aşağıda verilmiştir. "Item2" başlıklı ikinci liste girişi, düzenlenmek üzere seçilidir.

![CVSListBox denetimi](../../mfc/reference/media/cvslistbox.png "CVSListBox denetimi")

Düzenlenebilir bir liste denetimi eklemek için kaynak Düzenleyicisi 'ni kullanırsanız, düzenleyicinin **araç kutusu** bölmesinin önceden tanımlanmış bir düzenlenebilir liste denetimi sağlamadığına dikkat edin. Bunun yerine, **Grup kutusu** denetimi gibi bir statik denetim ekleyin. Çerçeve, düzenlenebilir liste denetiminin boyutunu ve konumunu belirtmek için statik denetimi bir yer tutucu olarak kullanır.

Bir iletişim kutusu şablonunda düzenlenebilir liste denetimini kullanmak için `CVSListBox` iletişim kutusu sınıfınızda bir değişken bildirin. Değişken ve denetim arasındaki veri değişimini desteklemek için, `DDX_Control` iletişim kutusunun yönteminde bir makro girişi tanımlayın `DoDataExchange` . Varsayılan olarak, düzenlenebilir liste denetimi düzenleme düğmeleri olmadan oluşturulur. Düzenleme düğmelerini etkinleştirmek için devralınmış CVSListBoxBase:: SetStandardButtons metodunu kullanın.

Daha fazla bilgi için bkz. Samples dizini, `New Controls` örnek, PAGE3. cpp ve Page3. h dosyaları.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CStatic](../../mfc/reference/cstatic-class.md)

`CVSListBoxBase`

[CVSListBox](../../mfc/reference/cvslistbox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxvslistbox. h

## <a name="cvslistboxadditem"></a><a name="additem"></a> CVSListBox:: AddItem

Liste denetimine bir dize ekler.

```
virtual int AddItem(
    const CString& strIext,
    DWORD_PTR dwData=0,
    int iIndex=-1);
```

### <a name="parameters"></a>Parametreler

*Çarpıcı*<br/>
'ndaki Bir dizeye başvuru.

*dwData*<br/>
'ndaki Dizeyle ilişkili, uygulamaya özgü 32 bitlik bir değer. Varsayılan değer 0’dır.

*IIndex*<br/>
'ndaki Dizeyi tutacak konumun sıfır tabanlı dizini. *IIndex* parametresi-1 ise, dize listenin sonuna eklenir. Varsayılan değer -1'dir.

### <a name="return-value"></a>Dönüş Değeri

Liste denetimindeki dize konumunun sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

*DwData* parametresi tarafından belirtilen değeri almak Için [CVSListBox:: GetItemData](#getitemdata) metodunu kullanın. Bu değer, uygulamaya özgü bir tamsayı veya diğer verilere yönelik bir işaretçi olabilir.

## <a name="cvslistboxcvslistbox"></a><a name="cvslistbox"></a> CVSListBox:: CVSListBox

Bir `CVSListBox` nesnesi oluşturur.

```
CVSListBox();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cvslistboxedititem"></a><a name="edititem"></a> CVSListBox:: EditItem

Bir liste denetim öğesi metni üzerinde bir düzenleme işlemi başlatır.

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Liste denetim öğesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Düzenleme işlemi başarıyla başlarsa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir öğe etiketine çift tıklayarak ya da bir öğe odağa sahip olduğunda **F2** veya **boşluk** tuşuna basarak bir düzenleme işlemi başlatır.

## <a name="cvslistboxgetcount"></a><a name="getcount"></a> CVSListBox:: GetCount

Düzenlenebilir liste denetimindeki dize sayısını alır.

```
virtual int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste denetimindeki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Dizin sıfır tabanlı olduğundan, sayının son öğenin dizin değerinden bir daha büyük olduğunu unutmayın.

## <a name="cvslistboxgetitemdata"></a><a name="getitemdata"></a> CVSListBox:: GetItemData

Düzenlenebilir bir liste denetim öğesiyle ilişkili uygulamaya özgü 32 bitlik bir değer alır.

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Düzenlenebilir liste denetim öğesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğeyle ilişkili 32 bitlik değer.

### <a name="remarks"></a>Açıklamalar

32 bitlik değeri liste denetim öğesiyle ilişkilendirmek için [CVSListBox:: SetItemData](#setitemdata) veya [CVSListBox:: addidıtem](#additem) metodunu kullanın. Bu değer, uygulamaya özgü bir tamsayı veya diğer verilere yönelik bir işaretçi olabilir.

## <a name="cvslistboxgetitemtext"></a><a name="getitemtext"></a> CVSListBox:: GetItemText

Düzenlenebilir liste denetim öğesinin metnini alır.

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Düzenlenebilir liste denetim öğesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğenin metnini içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="cvslistboxgetlisthwnd"></a><a name="getlisthwnd"></a> CVSListBox:: GetListHwnd

Geçerli katıştırılmış liste görünümü denetimine yönelik tanıtıcıyı döndürür.

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Katıştırılmış liste görünümü denetimine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Sınıfı destekleyen katıştırılmış liste görünümü denetimine bir tanıtıcı almak için bu yöntemi kullanın `CVSListBox` .

## <a name="cvslistboxgetselitem"></a><a name="getselitem"></a> CVSListBox:: Getselıdıtem

Seçili olan öğenin sıfır tabanlı dizinini düzenlenebilir liste denetiminde alır.

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa, şu anda seçili öğenin sıfır tabanlı dizini; Aksi takdirde,-1.

### <a name="remarks"></a>Açıklamalar

## <a name="cvslistboxremoveitem"></a><a name="removeitem"></a> CVSListBox:: RemoveItem

Düzenlenebilir liste denetiminden bir öğeyi kaldırır.

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Düzenlenebilir liste denetim öğesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe kaldırılırsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cvslistboxselectitem"></a><a name="selectitem"></a> CVSListBox:: SelectItem

Düzenlenebilir bir liste denetim dizesi seçer.

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>Parametreler

*IItem*<br/>
'ndaki Düzenlenebilir liste denetim öğesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem belirtilen öğeyi seçer ve gerekliyse, öğeyi görünüme kaydırır.

## <a name="cvslistboxsetitemdata"></a><a name="setitemdata"></a> CVSListBox:: SetItemData

Uygulamaya özgü 32 bitlik bir değeri düzenlenebilir liste denetim öğesiyle ilişkilendirir.

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Düzenlenebilir liste denetim öğesinin sıfır tabanlı dizini.

*dwData*<br/>
'ndaki 32 bitlik bir değer. Bu değer, uygulamaya özgü bir tamsayı veya diğer verilere yönelik bir işaretçi olabilir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
