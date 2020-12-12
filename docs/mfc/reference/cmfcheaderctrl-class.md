---
description: 'Daha fazla bilgi edinin: CMFCHeaderCtrl sınıfı'
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
ms.openlocfilehash: a6be476e095dc4a013705657e259a90d7cafe0d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265382"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl sınıfı

`CMFCHeaderCtrl`Sınıf, üst bilgi denetiminde birden çok sütunu sıralamayı destekler.

## <a name="syntax"></a>Syntax

```
class CMFCHeaderCtrl : public CHeaderCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCHeaderCtrl:: CMFCHeaderCtrl](#cmfcheaderctrl)|Bir `CMFCHeaderCtrl` nesnesi oluşturur.|
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCHeaderCtrl:: EnableMultipleSort](#enablemultiplesort)|Geçerli üst bilgi denetimi için *birden çok sütunlu sıralama* modunu etkin veya devre dışı bırakır.|
|[CMFCHeaderCtrl:: GetColumnState](#getcolumnstate)|Bir sütunun sıralanıp sıralanmadığını veya artan veya azalan düzende sıralanıp sıralanmadığını gösterir.|
|[CMFCHeaderCtrl:: GetSortColumn](#getsortcolumn)|Üst bilgi denetimindeki ilk sıralanmış sütunun sıfır tabanlı dizinini alır.|
|`CMFCHeaderCtrl::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCHeaderCtrl:: ısyükselen](#isascending)|Üst bilgi denetimindeki herhangi bir sütunun artan düzende sıralanıp sıralanmadığını gösterir.|
|[CMFCHeaderCtrl:: IsDialogControl](#isdialogcontrol)|Geçerli üst bilgi denetiminin ana penceresinin bir iletişim kutusu olup olmadığını gösterir.|
|[CMFCHeaderCtrl:: Ismultiplesıralaması](#ismultiplesort)|Geçerli üst bilgi denetiminin *birden çok sütun sıralama* modunda olup olmadığını gösterir.|
|[CMFCHeaderCtrl:: RemoveSortColumn](#removesortcolumn)|Belirtilen sütunu sıralama sütunları listesinden kaldırır.|
|[CMFCHeaderCtrl:: SetSortColumn](#setsortcolumn)|Üstbilgi denetimindeki belirtilen sütunun sıralama düzenini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCHeaderCtrl:: OnDrawItem](#ondrawitem)|Bir üst bilgi denetim sütunu çizmek için Framework tarafından çağırılır.|
|[CMFCHeaderCtrl:: OnDrawSortArrow](#ondrawsortarrow)|Sıralama okunu çizmek için Framework tarafından çağırılır.|
|[CMFCHeaderCtrl:: OnFillBackground](#onfillbackground)|Üst bilgi denetim sütununun arka planını dolduracak şekilde Framework tarafından çağırılır.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu `CMFCHeaderCtrl` ve geçerli üst bilgi denetimi için *birden çok sütunlu sıralama* modunun nasıl etkinleştirileceğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]

## <a name="remarks"></a>Açıklamalar

`CMFCHeaderCtrl`Sınıfı, sütunun sıralanacağını göstermek için üst bilgi denetim sütununa bir sıralama oku çizer. Üst liste denetimindeki bir sütun kümesi ( [CMFCListCtrl sınıfı](../../mfc/reference/cmfclistctrl-class.md)) aynı anda sıralanmışsa, *birden çok sütunlu sıralama* modu kullanın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)

[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxheaderctrl. h

## <a name="cmfcheaderctrlcmfcheaderctrl"></a><a name="cmfcheaderctrl"></a> CMFCHeaderCtrl:: CMFCHeaderCtrl

Bir `CMFCHeaderCtrl` nesnesi oluşturur.

```
CMFCHeaderCtrl::CMFCHeaderCtrl()
```

### <a name="remarks"></a>Açıklamalar

Bu Oluşturucu belirtilen değerlere aşağıdaki üye değişkenlerini başlatır:

|Üye değişkeni|Değer|
|---------------------|-----------|
|`m_bIsMousePressed`|FALSE|
|`m_bMultipleSort`|FALSE|
|`m_bAscending`|TRUE|
|`m_nHighlightedItem`|-1|
|`m_bTracked`|FALSE|
|`m_bIsDlgControl`|FALSE|
|`m_hFont`|NULL|

## <a name="cmfcheaderctrlenablemultiplesort"></a><a name="enablemultiplesort"></a> CMFCHeaderCtrl:: EnableMultipleSort

Geçerli üst bilgi denetimi için *birden çok sütunlu sıralama* modunu etkin veya devre dışı bırakır.

```cpp
void EnableMultipleSort(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Birden çok sütunlu sıralama modunu etkinleştirmek için TRUE; Birden çok sütun sıralama modunu devre dışı bırakmak ve sıralanmış sütunlar listesinden sütunları kaldırmak için FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

Birden çok sütunlu sıralama modunu etkinleştirmek veya devre dışı bırakmak için bu yöntemi kullanın. Üst bilgi denetimi birden çok sütunlu sıralama modunda ise, iki veya daha fazla sütun bir sıralamaya katılabilir.

## <a name="cmfcheaderctrlgetcolumnstate"></a><a name="getcolumnstate"></a> CMFCHeaderCtrl:: GetColumnState

Bir sütunun sıralanmamış olup olmadığını veya artan veya azalan düzende sıralanıp sıralanmadığını gösterir.

```
int GetColumnState(int iColumn) const;
```

### <a name="parameters"></a>Parametreler

*ıolumn*<br/>
'ndaki Bir sütunun sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütunun sıralama durumunu belirten bir değer. Aşağıdaki tabloda olası değerler listelenmiştir:

|Değer|Açıklama|
|-----------|-----------------|
|-1|Azalan düzende sıralanır.|
|0|Sıralanmaz.|
|1|Artan sırada sıralanır.|

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcheaderctrlgetsortcolumn"></a><a name="getsortcolumn"></a> CMFCHeaderCtrl:: GetSortColumn

Üst bilgi denetimindeki ilk sıralanmış sütunun sıfır tabanlı dizinini alır.

```
int GetSortColumn() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıralanmış bir sütunun dizini veya sıralanmış bir sütun bulunmazsa-1.

### <a name="remarks"></a>Açıklamalar

Üst bilgi denetimi *birden çok sütunlu sıralama* modunda ise ve uygulamayı hata ayıklama modunda derlediğiniz zaman, bu yöntem bunun yerine [CMFCHeaderCtrl:: GetColumnState](#getcolumnstate) metodunu kullanmayı onaylar ve size yardımcı olur. Üst bilgi denetimi birden çok sütunlu sıralama modundaysa ve uygulamayı perakende modunda derlediğiniz takdirde, bu yöntem-1 döndürür.

## <a name="cmfcheaderctrlisascending"></a><a name="isascending"></a> CMFCHeaderCtrl:: ısyükselen

Üst bilgi denetimindeki herhangi bir sütunun artan düzende sıralanıp sıralanmadığını gösterir.

```
BOOL IsAscending() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üst bilgi denetimindeki herhangi bir sütun artan düzende sıralanmışsa TRUE. Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin döndürdüğü değer, üst bilgi denetim öğesinde uygun sıralama okunu göstermek için kullanılır. Sıralama düzenini ayarlamak için [CMFCHeaderCtrl:: SetSortColumn](#setsortcolumn) metodunu kullanın.

## <a name="cmfcheaderctrlisdialogcontrol"></a><a name="isdialogcontrol"></a> CMFCHeaderCtrl:: IsDialogControl

Geçerli üst bilgi denetiminin ana penceresinin bir iletişim kutusu olup olmadığını gösterir.

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli üst bilgi denetiminin üst penceresi bir iletişim kutusu ise TRUE. Aksi takdirde, FALSE.

## <a name="cmfcheaderctrlismultiplesort"></a><a name="ismultiplesort"></a> CMFCHeaderCtrl:: Ismultiplesıralaması

Geçerli üst bilgi denetiminin *birden çok sütun sıralama* modunda olup olmadığını gösterir.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birden çok sütunlu sıralama modu etkinse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Birden çok sütunlu sıralama modunu etkinleştirmek veya devre dışı bırakmak için [CMFCHeaderCtrl:: EnableMultipleSort](#enablemultiplesort) metodunu kullanın. Üst bilgi denetimi birden çok sütunlu sıralama modunda ise, iki veya daha fazla sütun bir sıralamaya katılabilir.

## <a name="cmfcheaderctrlondrawitem"></a><a name="ondrawitem"></a> CMFCHeaderCtrl:: OnDrawItem

Bir üst bilgi denetim sütunu çizmek için Framework tarafından çağırılır.

```
virtual void OnDrawItem(
    CDC* pDC,
    int iItem,
    CRect rect,
    BOOL bIsPressed,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*IItem*<br/>
'ndaki Çizilecek öğenin sıfır tabanlı dizini.

*Rect*<br/>
'ndaki Çizilecek öğenin sınırlayıcı dikdörtgeni.

*Bisbasılmış*<br/>
'ndaki Basılı durumda öğeyi çizmek için TRUE; Aksi takdirde, FALSE.

*Bisvurgulu*<br/>
'ndaki Vurgulanan durumda öğeyi çizmek için TRUE; Aksi takdirde, FALSE.

## <a name="cmfcheaderctrlondrawsortarrow"></a><a name="ondrawsortarrow"></a> CMFCHeaderCtrl:: OnDrawSortArrow

Sıralama okunu çizmek için Framework tarafından çağırılır.

```
virtual void OnDrawSortArrow(
    CDC* pDC,
    CRect rectArrow);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*rectArrow*<br/>
'ndaki Sıralama okuna ait sınırlayıcı dikdörtgen.

## <a name="cmfcheaderctrlonfillbackground"></a><a name="onfillbackground"></a> CMFCHeaderCtrl:: OnFillBackground

Üst bilgi denetim sütununun arka planını dolduracak şekilde Framework tarafından çağırılır.

```
virtual void OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcheaderctrlremovesortcolumn"></a><a name="removesortcolumn"></a> CMFCHeaderCtrl:: RemoveSortColumn

Belirtilen sütunu sıralama sütunları listesinden kaldırır.

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>Parametreler

*ıolumn*<br/>
'ndaki Kaldırılacak sütunun sıfır tabanlı dizini.

## <a name="cmfcheaderctrlsetsortcolumn"></a><a name="setsortcolumn"></a> CMFCHeaderCtrl:: SetSortColumn

Üstbilgi denetimindeki belirtilen sütunun sıralama düzenini ayarlar.

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending=TRUE,
    BOOL bAdd=FALSE);
```

### <a name="parameters"></a>Parametreler

*ıolumn*<br/>
'ndaki Üst bilgi denetim sütununun sıfır tabanlı dizini. Bu parametre sıfırdan küçükse, bu yöntem sıralama sütunları listesinden tüm sütunları kaldırır.

*Bascbitiriliyor*<br/>
'ndaki *Iolumn* parametresinin belirttiği sütunun sıralama düzenini belirtir. Artan sıralamayı ayarlamak için TRUE; Azalan sıra ayarlamak için FALSE. Varsayılan değer TRUE 'dur.

*bAdd*<br/>
'ndaki *Iolumn* parametresinin belirttiği sütunun sıralama düzenini ayarlamak için true.

Geçerli üst bilgi denetimi *birden çok sütunlu sıralama* modundaysa, bu yöntem sıralama sütunları listesine belirtilen sütunu ekler. Birden çok sütunlu sıralama modunu ayarlamak için [CMFCHeaderCtrl:: EnableMultipleSort](#enablemultiplesort) komutunu kullanın.

Birden çok sütunlu sıralama modu ayarlanmamışsa ve bu yöntem hata ayıklama modunda derlenirse, bu yöntem onaylar. Birden çok sütunlu sıralama modu ayarlanmamışsa ve bu yöntem perakende modunda derlenirse, bu yöntem öncelikle sıralama sütunları listesinden tüm sütunları kaldırır ve ardından belirtilen sütunu listeye ekler.

Önce sıralama sütunları listesinden tüm sütunları kaldırmak için FALSE, ardından belirtilen sütunu listeye ekleyin. Varsayılan değer FALSE 'dur.

### <a name="remarks"></a>Açıklamalar

Bir sütunun sıralama düzenini ayarlamak için bu yöntemi kullanın. Gerekirse, bu yöntem sütunu sıralama sütunları listesine ekler. Üstbilgi denetimi, yukarı veya aşağı işaret eden bir sıralama oku çizmek için sıralama düzenini kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl sınıfı](../../mfc/reference/cmfclistctrl-class.md)
