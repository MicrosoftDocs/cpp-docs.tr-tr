---
title: CMFCHeaderCtrl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::EnableMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::GetColumnState
- AFXHEADERCTRL/CMFCHeaderCtrl::GetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::IsAscending
- AFXHEADERCTRL/CMFCHeaderCtrl::IsDialogControl
- AFXHEADERCTRL/CMFCHeaderCtrl::IsMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::RemoveSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::SetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawItem
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawSortArrow
- AFXHEADERCTRL/CMFCHeaderCtrl::OnFillBackground
helpviewer_keywords:
- CMFCHeaderCtrl [MFC], CMFCHeaderCtrl
- CMFCHeaderCtrl [MFC], EnableMultipleSort
- CMFCHeaderCtrl [MFC], GetColumnState
- CMFCHeaderCtrl [MFC], GetSortColumn
- CMFCHeaderCtrl [MFC], IsAscending
- CMFCHeaderCtrl [MFC], IsDialogControl
- CMFCHeaderCtrl [MFC], IsMultipleSort
- CMFCHeaderCtrl [MFC], RemoveSortColumn
- CMFCHeaderCtrl [MFC], SetSortColumn
- CMFCHeaderCtrl [MFC], OnDrawItem
- CMFCHeaderCtrl [MFC], OnDrawSortArrow
- CMFCHeaderCtrl [MFC], OnFillBackground
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
ms.openlocfilehash: 5140d02c5acbbc430c3b4d175da1933c79c702b3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752347"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Sınıfı

Sınıf, `CMFCHeaderCtrl` üstbilgi denetiminde birden çok sütunun sıralatını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCHeaderCtrl : public CHeaderCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCHeaderCtrl::CMFCHeaderCtrl](#cmfcheaderctrl)|Bir `CMFCHeaderCtrl` nesne inşa eder.|
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|Geçerli üstbilgi denetimi için *birden çok sütun sıralama* modunu etkinleştirer veya devre dışı kılabilir.|
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|Bir sütunun sıralanıp sıralanmadığını veya artan veya azalan sırada sıralanıp sıralanmadığını gösterir.|
|[CMFCHeaderCtrl::GetSortSütun](#getsortcolumn)|Üstbilgi denetiminde ilk sıralanmış sütunun sıfır tabanlı dizinini alır.|
|`CMFCHeaderCtrl::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCHeaderCtrl::IsAscending](#isascending)|Üstbilgi denetimindeki herhangi bir sütunun artan sırada sıralanıp sıralanmadığını gösterir.|
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|Geçerli üstbilgi denetiminin üstbilgi penceresinin iletişim kutusu olup olmadığını gösterir.|
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|Geçerli üstbilgi denetiminin *birden çok sütun sıralama* modunda olup olmadığını gösterir.|
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|Belirtilen sütunu sıralama sütunları listesinden kaldırır.|
|[CMFCHeaderCtrl::SetSortSütun](#setsortcolumn)|Üstbilgi denetiminde belirli bir sütunun sıralama sırasını ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|Üstbilgi denetim sütunu çizmek için çerçeve tarafından çağrılır.|
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|Sıralama oku çizmek için çerçeve tarafından çağrılır.|
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|Üstbilgi denetim sütununun arka planını doldurmak için çerçeve tarafından çağrılır.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCHeaderCtrl` nasıl oluşturulabildiğini ve geçerli üstbilgi denetimi için birden çok sütun *sıralama* modunun nasıl etkinleştirilen ini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]

## <a name="remarks"></a>Açıklamalar

Sınıf, `CMFCHeaderCtrl` sütunun sıralı olduğunu belirtmek için üstbilgi denetim sütununa bir sıralama oku çizer. Üst liste denetiminde [(CMFCListCtrl Sınıfı)](../../mfc/reference/cmfclistctrl-class.md)aynı anda sıralanabilen bir sütun kümesi *varsa, birden çok sütun sıralama* modunu kullanın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)

[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxheaderctrl.h

## <a name="cmfcheaderctrlcmfcheaderctrl"></a><a name="cmfcheaderctrl"></a>CMFCHeaderCtrl::CMFCHeaderCtrl

Bir `CMFCHeaderCtrl` nesne inşa eder.

```
CMFCHeaderCtrl::CMFCHeaderCtrl()
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu, aşağıdaki üye değişkenleri belirtilen değerlere aparat eder:

|Üye değişkeni|Değer|
|---------------------|-----------|
|`m_bIsMousePressed`|FALSE|
|`m_bMultipleSort`|FALSE|
|`m_bAscending`|TRUE|
|`m_nHighlightedItem`|-1|
|`m_bTracked`|FALSE|
|`m_bIsDlgControl`|FALSE|
|`m_hFont`|NULL|

## <a name="cmfcheaderctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>CMFCHeaderCtrl::EnableMultipleSort

Geçerli üstbilgi denetimi için *birden çok sütun sıralama* modunu etkinleştirer veya devre dışı kılabilir.

```cpp
void EnableMultipleSort(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Birden çok sütun sıralama modunu etkinleştirmek için TRUE; Birden çok sütun sıralama modunu devre dışı bırakıp sıralanan sütunlar listesinden sütunları kaldırmak için FALSE. Varsayılan değer TRUE'dur.

### <a name="remarks"></a>Açıklamalar

Birden çok sütun sıralama modunu etkinleştirmek veya devre dışı ksaymak için bu yöntemi kullanın. Üstbilgi denetimi birden çok sütun sıralama modundaysa, iki veya daha fazla sütun bir sıralamaya katılabilir.

## <a name="cmfcheaderctrlgetcolumnstate"></a><a name="getcolumnstate"></a>CMFCHeaderCtrl::GetColumnState

Bir sütunun sıralanmamış olup olmadığını veya artan veya azalan sırada sıralanıp sıralanmadığını gösterir.

```
int GetColumnState(int iColumn) const;
```

### <a name="parameters"></a>Parametreler

*ıcolumn*<br/>
[içinde] Bir sütunun sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütunun sıralama durumunu gösteren bir değer. Aşağıdaki tabloda olası değerler listelenebilmektedir:

|Değer|Açıklama|
|-----------|-----------------|
|-1|Azalan sırada sıralanır.|
|0|Sıralanmış değil.|
|1|Artan sırada sıralanır.|

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcheaderctrlgetsortcolumn"></a><a name="getsortcolumn"></a>CMFCHeaderCtrl::GetSortSütun

Üstbilgi denetiminde ilk sıralanmış sütunun sıfır tabanlı dizinini alır.

```
int GetSortColumn() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıralanmış bir sütunun dizini veya sıralanmış sütun bulunamazsa -1.

### <a name="remarks"></a>Açıklamalar

Üstbilgi denetimi birden *çok sütun sıralama* modundaysa ve uygulamayı hata ayıklama modunda derlediyseniz, bu yöntem [cmfcheaderCtrl::GetColumnState](#getcolumnstate) yöntemini kullanmanızı önerir. Üstbilgi denetimi birden çok sütun sıralama modundaysa ve uygulamayı perakende modunda derlediyseniz, bu yöntem -1 döndürür.

## <a name="cmfcheaderctrlisascending"></a><a name="isascending"></a>CMFCHeaderCtrl::IsAscending

Üstbilgi denetimindeki herhangi bir sütunun artan sırada sıralanıp sıralanmadığını gösterir.

```
BOOL IsAscending() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üstbilgi denetimindeki herhangi bir sütun artan sırada sıralanırsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin döndürdettiği değer, üstbilgi denetim öğesinde uygun sıralama oku görüntülemek için kullanılır. Sıralama sırasını ayarlamak için [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn) yöntemini kullanın.

## <a name="cmfcheaderctrlisdialogcontrol"></a><a name="isdialogcontrol"></a>CMFCHeaderCtrl::IsDialogControl

Geçerli üstbilgi denetiminin üstbilgi penceresinin iletişim kutusu olup olmadığını gösterir.

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli üstbilgi denetiminin üstbilgi denetiminin üst penceresi bir iletişim kutusuysa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfcheaderctrlismultiplesort"></a><a name="ismultiplesort"></a>CMFCHeaderCtrl::IsMultipleSort

Geçerli üstbilgi denetiminin *birden çok sütun sıralama* modunda olup olmadığını gösterir.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birden çok sütun sıralama modu etkinse TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Birden çok sütun sıralama modunu etkinleştirmek veya devre dışı kakmak için [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) yöntemini kullanın. Üstbilgi denetimi birden çok sütun sıralama modundaysa, iki veya daha fazla sütun bir sıralamaya katılabilir.

## <a name="cmfcheaderctrlondrawitem"></a><a name="ondrawitem"></a>CMFCHeaderCtrl::OnDrawItem

Üstbilgi denetim sütunu çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDrawItem(
    CDC* pDC,
    int iItem,
    CRect rect,
    BOOL bIsPressed,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*iÖğe*<br/>
[içinde] Çizecek öğenin sıfır tabanlı dizin.

*Rect*<br/>
[içinde] Çizecek öğenin sınırlayıcı dikdörtgeni.

*bIsPressed*<br/>
[içinde] Maddeyi basılı durumda çizmek için TRUE; aksi takdirde, YANLIŞ.

*bIsVurgulu*<br/>
[içinde] Maddeyi vurgulanan durumda çizmek için TRUE; aksi takdirde, YANLIŞ.

## <a name="cmfcheaderctrlondrawsortarrow"></a><a name="ondrawsortarrow"></a>CMFCHeaderCtrl::OnDrawSortArrow

Sıralama oku çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDrawSortArrow(
    CDC* pDC,
    CRect rectArrow);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*rektArrow*<br/>
[içinde] Sıralama okunun sınırlayıcı dikdörtgeni.

## <a name="cmfcheaderctrlonfillbackground"></a><a name="onfillbackground"></a>CMFCHeaderCtrl::OnFillBackground

Üstbilgi denetim sütununun arka planını doldurmak için çerçeve tarafından çağrılır.

```
virtual void OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcheaderctrlremovesortcolumn"></a><a name="removesortcolumn"></a>CMFCHeaderCtrl::RemoveSortColumn

Belirtilen sütunu sıralama sütunları listesinden kaldırır.

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>Parametreler

*ıcolumn*<br/>
[içinde] Kaldırılacak sütunun sıfır tabanlı dizin.

## <a name="cmfcheaderctrlsetsortcolumn"></a><a name="setsortcolumn"></a>CMFCHeaderCtrl::SetSortSütun

Üstbilgi denetiminde belirli bir sütunun sıralama sırasını ayarlar.

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending=TRUE,
    BOOL bAdd=FALSE);
```

### <a name="parameters"></a>Parametreler

*ıcolumn*<br/>
[içinde] Üstbilgi denetim sütununun sıfır tabanlı dizin. Bu parametre sıfırdan küçükse, bu yöntem tüm sütunları sıralama sütunları listesinden kaldırır.

*bArtan*<br/>
[içinde] *iSütun* parametresinin belirttiği sütunun sıralama sırasını belirtir. Yükselen düzeni ayarlamak için DOĞRU; Azalan sırayı ayarlamak için YANLIŞ. Varsayılan değer TRUE'dur.

*Baran*<br/>
[içinde] *TRUE iSütun* parametre sinin belirttiği sütunun sıralama sırasını ayarlamak için.

Geçerli üstbilgi denetimi *birden çok sütun sıralama* modundaysa, bu yöntem belirtilen sütunu sıralama sütunları listesine ekler. Birden çok sütun sıralama modunu ayarlamak için [CMFCHeaderCtrl::EnableMultipleSort'ı](#enablemultiplesort) kullanın.

Birden çok sütun sıralama modu ayarlanmaz ve bu yöntem hata ayıklama modunda derlenirse, bu yöntem ileri sayılsın. Birden çok sütun sıralama modu ayarlanmamışsa ve bu yöntem perakende modunda derlenmişse, bu yöntem önce sıra sütunları listesinden tüm sütunları kaldırır ve ardından belirtilen sütunu listeye ekler.

ÖNCE sıralama sütunları listesinden tüm sütunları kaldırmak ve ardından belirtilen sütunu listeye eklemek için FALSE. Varsayılan değer FALSE'dur.

### <a name="remarks"></a>Açıklamalar

Bir sütunun sıralama sırasını ayarlamak için bu yöntemi kullanın. Gerekirse, bu yöntem sütunu sıralama sütunları listesine ekler. Üstbilgi denetimi yukarı veya aşağı işaret eden bir sıralama oku çizmek için sıralama sırasını kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl Sınıfı](../../mfc/reference/cmfclistctrl-class.md)
