---
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
ms.openlocfilehash: 618f4f386db477dd301ada862ebd2094a6c6651f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324442"
---
# <a name="cvslistbox-class"></a>CVSListBox sınıfı

`CVSListBox` Sınıfı, düzenlenebilir bir liste denetimini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CVSListBox : public CVSListBoxBase
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CVSListBox::CVSListBox](#cvslistbox)|Oluşturur bir `CVSListBox` nesne.|
|`CVSListBox::~CVSListBox`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CVSListBox::AddItem](#additem)|Liste denetimi için bir dize ekler. (Geçersiz kılmaları `CVSListBoxBase::AddItem`.)|
|[CVSListBox::EditItem](#edititem)|Liste Denetim öğesi metni düzenleme işlemi başlatır. (Geçersiz kılmaları `CVSListBoxBase::EditItem`.)|
|[CVSListBox::GetCount](#getcount)|Düzenlenebilir bir liste denetimini dizelerde sayısını alır. (Geçersiz kılmaları `CVSListBoxBase::GetCount`.)|
|[CVSListBox::GetItemData](#getitemdata)|Bir düzenlenebilir bir liste denetim öğesi ile ilişkilendirilen bir uygulamaya özgü 32-bit değeri alır. (Geçersiz kılmaları `CVSListBoxBase::GetItemData`.)|
|[CVSListBox::GetItemText](#getitemtext)|Düzenlenebilir bir liste denetimini öğenin metnini alır. (Geçersiz kılmaları `CVSListBoxBase::GetItemText`.)|
|[CVSListBox::GetSelItem](#getselitem)|Düzenlenebilir bir liste denetimini şu anda seçili öğenin sıfır tabanlı dizinini alır. (Geçersiz kılmaları `CVSListBoxBase::GetSelItem`.)|
|`CVSListBox::PreTranslateMessage`|Pencere iletileri için dağıtılmadan önce çevirir [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows işlevleri. Daha fazla bilgi ve yöntem sözdizimi için bkz. [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz kılmaları `CVSListBoxBase::PreTranslateMessage`.)|
|[CVSListBox::RemoveItem](#removeitem)|Bir düzenlenebilir bir liste denetiminden bir öğeyi kaldırır. (Geçersiz kılmaları `CVSListBoxBase::RemoveItem`.)|
|[CVSListBox::SelectItem](#selectitem)|Düzenlenebilir bir liste denetimini dizisi seçer. (Geçersiz kılmaları `CVSListBoxBase::SelectItem`.)|
|[CVSListBox::SetItemData](#setitemdata)|Uygulamaya özgü 32-bit bir değer bir düzenlenebilir listesi denetim öğesini ile ilişkilendirir. (Geçersiz kılmaları `CVSListBoxBase::SetItemData`.)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CVSListBox::GetListHwnd](#getlisthwnd)|Tanıtıcı geçerli katıştırılmış bir liste görünümü denetimi için döndürür.|

## <a name="remarks"></a>Açıklamalar

`CVSListBox` Sınıfı oluşturmak, değiştirmek, silmek veya liste denetimindeki öğeleri yeniden düzenlemek kullanıcıyı etkinleştirme Düzenle düğmeler kümesi sağlar.

Düzenlenebilir bir liste denetimini resmini verilmiştir. "Item2" başlıklı ikinci liste girdisini düzenlemek için seçilir.

![CVSListBox denetimi](../../mfc/reference/media/cvslistbox.png "CVSListBox denetimi")

Düzenlenebilir bir liste denetimini eklemek için kaynak düzenleyicisini kullanmak, dikkat **araç kutusu** Düzenleyicisi bölmesinde önceden tanımlanmış düzenlenebilir bir liste denetimini sağlamaz. Bunun yerine, statik denetim gibi ekleme **grup kutusu** denetimi. Çerçeve statik denetimin boyutunu ve konumunu düzenlenebilir bir liste denetimi belirtmek için bir yer tutucu olarak kullanır.

Düzenlenebilir bir liste denetimini bir iletişim kutusu şablonunda kullanmak için bildirin bir `CVSListBox` iletişim kutusu sınıfında değişken. Değişkeni ve denetimi arasındaki veri değişimini desteklemek için tanımladığınız bir `DDX_Control` makrosu girişi `DoDataExchange` iletişim kutusunun yöntemi. Varsayılan olarak, düzenlenebilir bir liste denetimi Düzenle düğmeler oluşturulur. Devralınan CVSListBoxBase::SetStandardButtons yöntemi Düzenle düğmeler etkinleştirmek için kullanın.

Örnekler dizini daha fazla bilgi için bkz. `New Controls` örnek Page3.cpp ve Page3.h dosyaları.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CStatic](../../mfc/reference/cstatic-class.md)

`CVSListBoxBase`

[CVSListBox](../../mfc/reference/cvslistbox-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxvslistbox.h

##  <a name="additem"></a>  CVSListBox::AddItem

Liste denetimi için bir dize ekler.

```
virtual int AddItem(
    const CString& strIext,
    DWORD_PTR dwData=0,
    int iIndex=-1);
```

### <a name="parameters"></a>Parametreler

*strIext*<br/>
[in] Bir dizeyi bir başvuru.

*dwData*<br/>
[in] Dize ile ilişkili bir uygulamaya özgü 32-bit değeri. Varsayılan değer 0’dır.

*İIndex*<br/>
[in] Dize barındıracak konumu sıfır tabanlı dizini. Varsa *İIndex* parametresi, -1, dizenin listenin sonuna eklenir. Varsayılan değer -1'dir.

### <a name="return-value"></a>Dönüş Değeri

Listesi denetimini dize konumunu sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Kullanım [CVSListBox::GetItemData](#getitemdata) yöntemi tarafından belirtilen değeri alınacak *dwData* parametresi. Bu değer, uygulamaya özgü tamsayı veya diğer verileri gösteren bir işaretçi olabilir.

##  <a name="cvslistbox"></a>  CVSListBox::CVSListBox

Oluşturur bir `CVSListBox` nesne.

```
CVSListBox();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="edititem"></a>  CVSListBox::EditItem

Liste Denetim öğesi metni düzenleme işlemi başlatır.

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>Parametreler

*İIndex*<br/>
[in] Liste Denetim öğesi sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Düzenleme işlemi başarıyla başlatılırsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir düzenleme işlemi, bir öğenin etiketini çift tıklayarak veya basarak başlatır. **F2** veya **boşluk** anahtar öğenin odağa sahip olduğunda.

##  <a name="getcount"></a>  CVSListBox::GetCount

Düzenlenebilir bir liste denetimini dizelerde sayısını alır.

```
virtual int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste denetiminde öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Dizin sıfır tabanlı olduğundan sayısı bir son öğenin dizini değerden büyük olduğunu unutmayın.

##  <a name="getitemdata"></a>  CVSListBox::GetItemData

Bir düzenlenebilir bir liste denetim öğesi ile ilişkilendirilen bir uygulamaya özgü 32-bit değeri alır.

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Parametreler

*İIndex*<br/>
[in] Düzenlenebilir bir liste denetimini öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe ile ilişkili 32-bit değeri.

### <a name="remarks"></a>Açıklamalar

Kullanım [CVSListBox::SetItemData](#setitemdata) veya [CVSListBox::AddItem](#additem) 32-bit bir değer listesi denetim öğesini ile ilişkilendirmek için yöntemi. Bu değer, uygulamaya özgü tamsayı veya diğer verileri gösteren bir işaretçi olabilir.

##  <a name="getitemtext"></a>  CVSListBox::GetItemText

Düzenlenebilir bir liste denetimini öğenin metnini alır.

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>Parametreler

*İIndex*<br/>
[in] Düzenlenebilir bir liste denetimini öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) belirtilen öğenin metnini içeren nesne.

### <a name="remarks"></a>Açıklamalar

##  <a name="getlisthwnd"></a>  CVSListBox::GetListHwnd

Tanıtıcı geçerli katıştırılmış bir liste görünümü denetimi için döndürür.

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Katıştırılmış bir liste görünümü denetimi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Destekleyen gömülü liste görünümü denetimi için bir tanıtıcı almak için bu yöntemi kullanın `CVSListBox` sınıfı.

##  <a name="getselitem"></a>  CVSListBox::GetSelItem

Düzenlenebilir bir liste denetimini şu anda seçili öğenin sıfır tabanlı dizinini alır.

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa sıfır tabanlı dizini; geçerli seçilmiş öğe Aksi durumda, -1.

### <a name="remarks"></a>Açıklamalar

##  <a name="removeitem"></a>  CVSListBox::RemoveItem

Bir düzenlenebilir bir liste denetiminden bir öğeyi kaldırır.

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>Parametreler

*İIndex*<br/>
[in] Düzenlenebilir bir liste denetimini öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe kaldırılırsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="selectitem"></a>  CVSListBox::SelectItem

Düzenlenebilir bir liste denetimini dizisi seçer.

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>Parametreler

*iItem*<br/>
[in] Düzenlenebilir bir liste denetimini öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen öğeyi seçer ve gerekliyse, öğe görünüme kaydırır.

##  <a name="setitemdata"></a>  CVSListBox::SetItemData

Uygulamaya özgü 32-bit bir değer bir düzenlenebilir listesi denetim öğesini ile ilişkilendirir.

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>Parametreler

*İIndex*<br/>
[in] Düzenlenebilir bir liste denetimini öğenin sıfır tabanlı dizini.

*dwData*<br/>
[in] 32-bit bir değer. Bu değer, uygulamaya özgü tamsayı veya diğer verileri gösteren bir işaretçi olabilir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
