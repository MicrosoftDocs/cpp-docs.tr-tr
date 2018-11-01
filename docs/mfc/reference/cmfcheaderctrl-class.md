---
title: CMFCHeaderCtrl sınıfı
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
ms.openlocfilehash: 10d7dda39223e1d6206d2ede96874d9d546c8776
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538508"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl sınıfı

`CMFCHeaderCtrl` Sınıfı, bir başlığı denetiminde birden çok sütunu sıralamayı destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCHeaderCtrl : public CHeaderCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCHeaderCtrl::CMFCHeaderCtrl](#cmfcheaderctrl)|Oluşturur bir `CMFCHeaderCtrl` nesne.|
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|Etkinleştirir veya devre dışı bırakır *birden çok sütunu sıralama* modu için geçerli üst bilgi denetimi.|
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|Bir sütun sıralı veya artan veya azalan düzende sıralandı olmadığını gösterir.|
|[CMFCHeaderCtrl::GetSortColumn](#getsortcolumn)|Üstbilgi denetimi sıralanmış ilk sütunda sıfır tabanlı dizinini alır.|
|`CMFCHeaderCtrl::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|[CMFCHeaderCtrl::IsAscending](#isascending)|Herhangi bir sütun başlığı denetiminde artan düzende sıralandı olmadığını gösterir.|
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|Geçerli üst bilgi denetiminin üst penceresine bir iletişim kutusu olup olmadığını belirtir.|
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|Geçerli üst bilgi denetiminin içinde olup olmadığını belirten *birden çok sütunu sıralama* modu.|
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|Belirtilen sütunun sıralama sütunları listesinden kaldırır.|
|[CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)|Üstbilgi denetimindeki belirtilen bir sütunun sıralama düzenini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|Üstbilgi denetimi sütun çizmek için framework tarafından çağırılır.|
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|Sıralama oku çizmek için framework tarafından çağırılır.|
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|Üstbilgi denetimi sütunun arkaplanını doldurmak için framework tarafından çağırılır.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCHeaderCtrl` sınıfı ve nasıl etkinleştirileceği *birden çok sütunu sıralama* modu için geçerli üst bilgi denetimi.

[!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]

## <a name="remarks"></a>Açıklamalar

`CMFCHeaderCtrl` Sınıfı bir üstbilgi denetim sütununda sütun sıralı olduğunu belirtmek için bir sıralama ok çizer. Kullanım *birden çok sütunu sıralama* modu bir dizi sütun üst liste denetimi ( [CMFCListCtrl sınıfı](../../mfc/reference/cmfclistctrl-class.md)) aynı anda sıralanabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)

[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxheaderctrl.h

##  <a name="cmfcheaderctrl"></a>  CMFCHeaderCtrl::CMFCHeaderCtrl

Oluşturur bir `CMFCHeaderCtrl` nesne.

```
CMFCHeaderCtrl::CMFCHeaderCtrl()
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu, aşağıdaki üye değişkenlerini belirtilen değerlerle başlatır:

|Üye değişkeni|Değer|
|---------------------|-----------|
|`m_bIsMousePressed`|FALSE|
|`m_bMultipleSort`|FALSE|
|`m_bAscending`|TRUE|
|`m_nHighlightedItem`|-1|
|`m_bTracked`|FALSE|
|`m_bIsDlgControl`|FALSE|
|`m_hFont`|NULL|

##  <a name="enablemultiplesort"></a>  CMFCHeaderCtrl::EnableMultipleSort

Etkinleştirir veya devre dışı bırakır *birden çok sütunu sıralama* modu için geçerli üst bilgi denetimi.

```
void EnableMultipleSort(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Birden çok sütunu sıralama modunu etkinleştirmek için TRUE; Birden çok sütunu sıralama modunu devre dışı bırakmak ve herhangi bir sütunu sıralanmış sütunlar listesinden kaldırmak için FALSE. Varsayılan değer True'dur.

### <a name="remarks"></a>Açıklamalar

Etkinleştirmek veya birden çok sütunu sıralama modunu devre dışı bırakmak için bu yöntemi kullanın. Üstbilgi denetimi birden çok sütunu sıralama modunda değilse, iki veya daha fazla sütun bir sıralamada katılabilir.

##  <a name="getcolumnstate"></a>  CMFCHeaderCtrl::GetColumnState

Bir sütun sıralı değil veya artan veya azalan düzende sıralandı olmadığını gösterir.

```
int GetColumnState(int iColumn) const;
```

### <a name="parameters"></a>Parametreler

*iColumn*<br/>
[in] Bir sütunun sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütunun sıralama durumunu gösteren bir değer. Olası değerler aşağıdaki tabloda listelenmektedir:

|Değer|Açıklama|
|-----------|-----------------|
|-1|Azalan düzende sıralanır.|
|0|Sıralı değil.|
|1.|Artan düzende sıralanır.|

### <a name="remarks"></a>Açıklamalar

##  <a name="getsortcolumn"></a>  CMFCHeaderCtrl::GetSortColumn

Üstbilgi denetimi sıralanmış ilk sütunda sıfır tabanlı dizinini alır.

```
int GetSortColumn() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıralanmış sütun veya sıralanmış sütun bulunursa, -1 dizini.

### <a name="remarks"></a>Açıklamalar

Üstbilgi denetimine ise *birden çok sütunu sıralama* modu ve bu yöntem, onaylar ve kullanmanızı önerir uygulamayı hata ayıklama modunda derlenmiş [CMFCHeaderCtrl::GetColumnState](#getcolumnstate) yöntemi yerine. Üstbilgi denetimi birden çok sütunu sıralama modunda ve uygulamayı perakende modunda derlenmiş, bu yöntem -1 döndürür.

##  <a name="isascending"></a>  CMFCHeaderCtrl::IsAscending

Herhangi bir sütun başlığı denetiminde artan düzende sıralandı olmadığını gösterir.

```
BOOL IsAscending() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir sütun başlığı denetiminde artan düzende sıralanır TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin döndürdüğü değer uygun sıralama okunu üstbilgi denetim öğesi üzerinde görüntülemek için kullanılır. Kullanım [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn) sıralama düzenini ayarlamak için yöntemi.

##  <a name="isdialogcontrol"></a>  CMFCHeaderCtrl::IsDialogControl

Geçerli üst bilgi denetiminin üst penceresine bir iletişim kutusu olup olmadığını belirtir.

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli üst bilgi denetiminin üst penceresine bir iletişim kutusu ise TRUE; Aksi takdirde FALSE.

##  <a name="ismultiplesort"></a>  CMFCHeaderCtrl::IsMultipleSort

Geçerli üst bilgi denetiminin içinde olup olmadığını belirten *birden çok sütunu sıralama* modu.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birden çok sütunu sıralama modu etkinse TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanım [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) etkinleştirmek veya birden çok sütunu sıralama modunu devre dışı bırakmak için yöntemi. Üstbilgi denetimi birden çok sütunu sıralama modunda değilse, iki veya daha fazla sütun bir sıralamada katılabilir.

##  <a name="ondrawitem"></a>  CMFCHeaderCtrl::OnDrawItem

Üstbilgi denetimi sütun çizmek için framework tarafından çağırılır.

```
virtual void OnDrawItem(
    CDC* pDC,
    int iItem,
    CRect rect,
    BOOL bIsPressed,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*iItem*<br/>
[in] Çizmek için öğenin sıfır tabanlı dizini.

*Rect*<br/>
[in] Dikdörtgen çizmek için öğesi.

*bIsPressed*<br/>
[in] Öğe basılı durumda çizmek için TRUE; Aksi takdirde FALSE.

*bIsHighlighted*<br/>
[in] Vurgulanan durumda öğeyi çizmek için TRUE; Aksi takdirde FALSE.

##  <a name="ondrawsortarrow"></a>  CMFCHeaderCtrl::OnDrawSortArrow

Sıralama oku çizmek için framework tarafından çağırılır.

```
virtual void OnDrawSortArrow(
    CDC* pDC,
    CRect rectArrow);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*rectArrow*<br/>
[in] Sıralama oku sınırlayıcı dikdörtgenini.

##  <a name="onfillbackground"></a>  CMFCHeaderCtrl::OnFillBackground

Üstbilgi denetimi sütunun arkaplanını doldurmak için framework tarafından çağırılır.

```
virtual void OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="removesortcolumn"></a>  CMFCHeaderCtrl::RemoveSortColumn

Belirtilen sütunun sıralama sütunları listesinden kaldırır.

```
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>Parametreler

*iColumn*<br/>
[in] Kaldırılacak sütunun sıfır tabanlı dizini.

##  <a name="setsortcolumn"></a>  CMFCHeaderCtrl::SetSortColumn

Üstbilgi denetimindeki belirtilen bir sütunun sıralama düzenini ayarlar.

```
void SetSortColumn(
    int iColumn,
    BOOL bAscending=TRUE,
    BOOL bAdd=FALSE);
```

### <a name="parameters"></a>Parametreler

*iColumn*<br/>
[in] Üstbilgi denetimi sütunun sıfır tabanlı dizini. Bu parametre küçükse sıfırdan, bu yöntem tüm sütunları sıralama sütunları listesinden kaldırır.

*bAscending*<br/>
[in] Sütunun sıralama düzenini belirtir, *iColumn* parametre belirtir. Artan düzende ayarlamak için TRUE; Azalan ayarlamak için FALSE. Varsayılan değer True'dur.

*Bekle*<br/>
[in] TRUE sütunun sıralama düzenini kümesi *iColumn* parametre belirtir.

Üstbilgi denetimine geçerli ise *birden çok sütunu sıralama* modu, bu yöntem, belirtilen sütun sıralama sütunlar listesine ekler. Kullanım [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) birden çok sütunu sıralama modu ayarlamak için.

Bu yöntem, birden çok sütunu sıralama modu ayarlı değil ve bu yöntem, hata ayıklama modunda derlendiğinde, onaylar. Birden çok sütunu sıralama modu ayarlı değil ve bu yöntem, perakende modunda derlendiğinde, bu yöntem ilk tüm sütunları sıralama sütunları listeden kaldırır ve ardından belirtilen sütun listesine ekler.

FALSE ilk olarak, tüm sütunları sıralama sütunları listeden kaldırın ve sonra belirtilen sütun listesine ekleyin. Varsayılan değer FALSE olur.

### <a name="remarks"></a>Açıklamalar

Bir sütunun sıralama düzenini ayarlamak için bu yöntemi kullanın. Gerekirse, bu yöntem Sütun sıralama sütunlar listesine ekler. Üstbilgi denetimi yukarı veya aşağı işaret eden bir sıralama ok çizmek için sıralama düzeni kullanır.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl Sınıfı](../../mfc/reference/cmfclistctrl-class.md)
