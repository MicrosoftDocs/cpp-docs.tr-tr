---
title: CVSListBox Sınıfı
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
ms.openlocfilehash: 4ea48a263a01133419067979ee5fa3e62105c7f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373185"
---
# <a name="cvslistbox-class"></a>CVSListBox Sınıfı

Sınıf, `CVSListBox` değiştirilebilir bir liste denetimini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CVSListBox : public CVSListBoxBase
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CVSListBox::CVSListBox](#cvslistbox)|Bir `CVSListBox` nesne inşa eder.|
|`CVSListBox::~CVSListBox`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CVSListBox::AddItem](#additem)|Liste denetimine bir dize ekler. (Geçersiz `CVSListBoxBase::AddItem`kılar .)|
|[CVSListBox::EditItem](#edititem)|Liste denetim öğesinin metninde bir denetim işlemi başlatır. (Geçersiz `CVSListBoxBase::EditItem`kılar .)|
|[CVSListBox::GetCount](#getcount)|Editable liste denetiminde dizelerin sayısını alır. (Geçersiz `CVSListBoxBase::GetCount`kılar .)|
|[CVSListBox::GetItemData](#getitemdata)|Kullanılabilir liste denetim öğesiyle ilişkili uygulamaya özgü 32 bit lik bir değer alır. (Geçersiz `CVSListBoxBase::GetItemData`kılar .)|
|[CVSListBox::GetItemText](#getitemtext)|Editable list denetim öğesinin metnini alır. (Geçersiz `CVSListBoxBase::GetItemText`kılar .)|
|[CVSListBox::GetSelItem](#getselitem)|Şu anda seçili maddenin sıfır tabanlı dizinini kullanılabilir liste denetiminde alır. (Geçersiz `CVSListBoxBase::GetSelItem`kılar .)|
|`CVSListBox::PreTranslateMessage`|Pencere iletilerini [Çeviri İletisi](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine gönderilmeden önce çevirir. Daha fazla bilgi ve yöntem sözdizimi için [Bkz. CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz `CVSListBoxBase::PreTranslateMessage`kılar .)|
|[CVSListBox::RemoveItem](#removeitem)|Bir öğeyi kullanılabilir liste denetiminden kaldırır. (Geçersiz `CVSListBoxBase::RemoveItem`kılar .)|
|[CVSListBox::SelectItem](#selectitem)|Editable liste denetim dizesi seçer. (Geçersiz `CVSListBoxBase::SelectItem`kılar .)|
|[CVSListBox::SetItemData](#setitemdata)|Uygulamaya özgü 32 bit değeri, kullanılabilir liste denetim öğesiyle ilişkilendirin. (Geçersiz `CVSListBoxBase::SetItemData`kılar .)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CVSListBox::GetListHwnd](#getlisthwnd)|Tanıtıcıyı geçerli katışılmış liste görünümü denetimine döndürür.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CVSListBox` kullanıcının liste denetimindeki öğeleri oluşturmasına, değiştirmesine, silmesini veya yeniden düzenlemesine olanak tanıyan bir düzenleme düğmesi kümesi sağlar.

Aşağıda, değiştirilebilir liste denetiminin bir resmi verem. "Item2" başlıklı ikinci liste girişi, düzenleme için seçilir.

![CVSListBox kontrolü](../../mfc/reference/media/cvslistbox.png "CVSListBox kontrolü")

Kullanılabilir bir liste denetimi eklemek için kaynak düzenleyicisini kullanıyorsanız, düzenleyicinin **Araç Kutusu** bölmesinin önceden tanımlanmış bir editable list denetimi sağlamadığını unutmayın. Bunun yerine, **Grup Kutusu** denetimi gibi statik bir denetim ekleyin. Çerçeve, değiştirilebilir liste denetiminin boyutunu ve konumunu belirtmek için yer tutucu olarak statik denetimi kullanır.

İletişim kutusu şablonunda değiştirilebilir liste denetimi kullanmak için `CVSListBox` iletişim kutusu sınıfınızda bir değişken bildirin. Değişken ve denetim arasındaki veri alışverişini `DDX_Control` desteklemek için `DoDataExchange` iletişim kutusu yönteminde bir makro girişi tanımlayın. Varsayılan olarak, düzenleme listesi denetimi düzenleme düğmeleri olmadan oluşturulur. Devralma düğmelerini etkinleştirmek için devralınan CVSListBoxBase::SetStandardButtons yöntemini kullanın.

Daha fazla bilgi için Örnekler dizini, `New Controls` örnek, Page3.cpp ve Page3.h dosyalarına bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cstatic](../../mfc/reference/cstatic-class.md)

`CVSListBoxBase`

[CVSListBox](../../mfc/reference/cvslistbox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxvslistbox.h

## <a name="cvslistboxadditem"></a><a name="additem"></a>CVSListBox::AddItem

Liste denetimine bir dize ekler.

```
virtual int AddItem(
    const CString& strIext,
    DWORD_PTR dwData=0,
    int iIndex=-1);
```

### <a name="parameters"></a>Parametreler

*strIext*<br/>
[içinde] Bir dize için bir başvuru.

*Dwdata*<br/>
[içinde] Dize ile ilişkili uygulamaya özgü 32 bit değeri. Varsayılan değer 0’dır.

*ıındex*<br/>
[içinde] Dizeyi tutacak konumun sıfır tabanlı dizin. *iIndex* parametresi -1 ise, dize listenin sonuna eklenir. Varsayılan değer -1'dir.

### <a name="return-value"></a>Dönüş Değeri

Liste denetimindeki dizenin konumunun sıfır tabanlı dizin.

### <a name="remarks"></a>Açıklamalar

*dwData* parametresi tarafından belirtilen değeri almak için [CVSListBox::GetItemData](#getitemdata) yöntemini kullanın. Bu değer uygulamaya özgü bir tamsayı veya diğer verilere işaretçi olabilir.

## <a name="cvslistboxcvslistbox"></a><a name="cvslistbox"></a>CVSListBox::CVSListBox

Bir `CVSListBox` nesne inşa eder.

```
CVSListBox();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cvslistboxedititem"></a><a name="edititem"></a>CVSListBox::EditItem

Liste denetim öğesinin metninde bir denetim işlemi başlatır.

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Liste denetim öğesinin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Edit işlemi başarıyla başlarsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Kullanıcı, bir öğenin etiketini çift tıklatarak veya bir öğe nin odak noktası olduğunda **F2** veya **SPACEBAR** tuşuna basarak bir düzenleme işlemi başlatır.

## <a name="cvslistboxgetcount"></a><a name="getcount"></a>CVSListBox::GetCount

Editable liste denetiminde dizelerin sayısını alır.

```
virtual int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste denetimindeki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Dizin sıfır tabanlı olduğundan, sayım son maddenin dizin değerinden bir büyük olduğunu unutmayın.

## <a name="cvslistboxgetitemdata"></a><a name="getitemdata"></a>CVSListBox::GetItemData

Kullanılabilir liste denetim öğesiyle ilişkili uygulamaya özgü 32 bit lik bir değer alır.

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Bir editable liste denetim öğesinin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen maddeyle ilişkili 32 bit lik değer.

### <a name="remarks"></a>Açıklamalar

32 bit değerini liste kontrol öğesiyle ilişkilendirmek için [CVSListBox::SetItemData](#setitemdata) veya [CVSListBox::AddItem](#additem) yöntemini kullanın. Bu değer uygulamaya özgü bir tamsayı veya diğer verilere işaretçi olabilir.

## <a name="cvslistboxgetitemtext"></a><a name="getitemtext"></a>CVSListBox::GetItemText

Editable list denetim öğesinin metnini alır.

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Bir editable liste denetim öğesinin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğenin metnini içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="cvslistboxgetlisthwnd"></a><a name="getlisthwnd"></a>CVSListBox::GetListHwnd

Tanıtıcıyı geçerli katışılmış liste görünümü denetimine döndürür.

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Katıştılmış liste görünümü denetimine bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

`CVSListBox` Sınıfı destekleyen katışılmış liste görünümü denetimine bir tanıtıcı almak için bu yöntemi kullanın.

## <a name="cvslistboxgetselitem"></a><a name="getselitem"></a>CVSListBox::GetSelItem

Şu anda seçili maddenin sıfır tabanlı dizinini kullanılabilir liste denetiminde alır.

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa, şu anda seçili öğenin sıfır tabanlı dizin; aksi takdirde, -1.

### <a name="remarks"></a>Açıklamalar

## <a name="cvslistboxremoveitem"></a><a name="removeitem"></a>CVSListBox::RemoveItem

Bir öğeyi kullanılabilir liste denetiminden kaldırır.

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Bir editable liste denetim öğesinin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe kaldırılırsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cvslistboxselectitem"></a><a name="selectitem"></a>CVSListBox::SelectItem

Editable liste denetim dizesi seçer.

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>Parametreler

*iÖğe*<br/>
[içinde] Bir editable liste denetim öğesinin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem belirtilen öğeyi seçer ve gerekirse öğeyi görünüme kaydırır.

## <a name="cvslistboxsetitemdata"></a><a name="setitemdata"></a>CVSListBox::SetItemData

Uygulamaya özgü 32 bit değeri, kullanılabilir liste denetim öğesiyle ilişkilendirin.

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Bir editable liste denetim öğesinin sıfır tabanlı dizin.

*Dwdata*<br/>
[içinde] 32 bit lik bir değer. Bu değer uygulamaya özgü bir tamsayı veya diğer verilere işaretçi olabilir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
