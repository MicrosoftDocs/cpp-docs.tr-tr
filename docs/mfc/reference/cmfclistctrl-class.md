---
title: CMFCListCtrl Sınıfı
ms.date: 07/30/2019
f1_keywords:
- CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl::EnableMarkSortedColumn
- AFXLISTCTRL/CMFCListCtrl::EnableMultipleSort
- AFXLISTCTRL/CMFCListCtrl::GetHeaderCtrl
- AFXLISTCTRL/CMFCListCtrl::IsMultipleSort
- AFXLISTCTRL/CMFCListCtrl::OnCompareItems
- AFXLISTCTRL/CMFCListCtrl::OnGetCellBkColor
- AFXLISTCTRL/CMFCListCtrl::OnGetCellFont
- AFXLISTCTRL/CMFCListCtrl::OnGetCellTextColor
- AFXLISTCTRL/CMFCListCtrl::RemoveSortColumn
- AFXLISTCTRL/CMFCListCtrl::SetSortColumn
- AFXLISTCTRL/CMFCListCtrl::Sort
helpviewer_keywords:
- CMFCListCtrl [MFC], EnableMarkSortedColumn
- CMFCListCtrl [MFC], EnableMultipleSort
- CMFCListCtrl [MFC], GetHeaderCtrl
- CMFCListCtrl [MFC], IsMultipleSort
- CMFCListCtrl [MFC], OnCompareItems
- CMFCListCtrl [MFC], OnGetCellBkColor
- CMFCListCtrl [MFC], OnGetCellFont
- CMFCListCtrl [MFC], OnGetCellTextColor
- CMFCListCtrl [MFC], RemoveSortColumn
- CMFCListCtrl [MFC], SetSortColumn
- CMFCListCtrl [MFC], Sort
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
ms.openlocfilehash: 099ec086bd95a1180af4cf5a8f6a9fa7f1d099ea
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754237"
---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl Sınıfı

Sınıf `CMFCListCtrl` [CMFCHeaderCtrl Sınıfıgelişmiş](../../mfc/reference/cmfcheaderctrl-class.md)üstbilgi denetimi işlevselliğini destekleyerek [CListCtrl Sınıf](../../mfc/reference/clistctrl-class.md) sınıfının işlevselliğini genişletir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCListCtrl : public CListCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|Sıralanmış bir sütunu farklı bir arka plan rengiyle işaretleme olanağı sağlar.|
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|Birden çok sıralama modunu etkinleştirer.|
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|Altı çizili üstbilgi denetimine bir başvuru verir.|
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|Liste denetiminin birden çok sıralama modunda olup olmadığını denetler.|
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|İki liste denetim öğesini karşılaştırması gerektiğinde çerçeve tarafından çağrılır.|
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|Tek bir hücrenin arka plan rengini belirlemesi gerektiğinde çerçeve tarafından çağrılır.|
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|Çizilen hücre için yazı tipini alması gerektiğinde çerçeve tarafından çağrılır.|
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Tek bir hücrenin metin rengini belirlemesi gerektiğinde çerçeve tarafından çağrılır.|
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|Sıralanmış sütunlar listesinden bir sıralama sütunu kaldırır.|
|[CMFCListCtrl::SetSortSütun](#setsortcolumn)|Geçerli sıralanmış sütunu ve sıralama sırasını ayarlar.|
|[CMFCListCtrl::Sırala](#sort)|Liste denetimini sıralar.|

## <a name="remarks"></a>Açıklamalar

`CMFCListCtrl`[CListCtrl Sınıf](../../mfc/reference/clistctrl-class.md) sınıfına iki geliştirme sunar. İlk olarak, sütun sıralama nın üstbilginin üzerine otomatik olarak bir sıralama oku çizerek kullanılabilir bir seçenek olduğunu gösterir. İkinci olarak, aynı anda birden çok sütunda veri sıralamadestekler.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCListCtrl` nasıl kullanılacağını göstermektedir. Örnek, liste denetiminin nasıl oluşturulup sütun lar ekleyip, öğeler eklenin, bir öğenin metnini nasıl ayarlayıp liste denetiminin yazı tipini ayarlayabilirsiniz. Bu kod snippet [Visual Studio Demo örnek](../../overview/visual-cpp-samples.md)parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Clistctrl](../../mfc/reference/clistctrl-class.md)

[CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxlistctrl.h

## <a name="cmfclistctrlenablemarksortedcolumn"></a><a name="enablemarksortedcolumn"></a>CMFCListCtrl::EnableMarkSortedColumn

Sıralanmış sütunları farklı bir arka plan rengiyle işaretler.

```cpp
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*bİşaret*<br/>
[içinde] Farklı bir arka plan rengini etkinleştirip etkinleştirmeyeceğini belirleyen boolean parametresi.

*bRedraw*<br/>
[içinde] Denetimi hemen yeniden çizip yeniden çizmeyeceğini belirleyen bir Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

`EnableMarkSortedColumn`sıralanmış `CDrawingManager::PixelAlpha` sütunlar için hangi rengin kullanılacağını hesaplamak için yöntemi kullanır. Alınan renk normal arka plan rengine bağlıdır.

## <a name="cmfclistctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>CMFCListCtrl::EnableMultipleSort

Liste denetimindeki veri satırlarını birden çok sütuna göre sıralamayı sağlar.

```cpp
void EnableMultipleSort(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Birden çok sütun sıralama modunu etkinleştirip etkinleştirmeyeceğini belirten bir Boolean.

### <a name="remarks"></a>Açıklamalar

Birden çok sütuna göre sıralamayı etkinleştirdiğinizde, sütunların bir hiyerarşisi var. Veri satırları ilk olarak birincil sütuna göre sıralanır. Eşdeğer değerler daha sonra öncelik esas alınarak sonraki her sütuna göre sıralanır.

## <a name="cmfclistctrlgetheaderctrl"></a><a name="getheaderctrl"></a>CMFCListCtrl::GetHeaderCtrl

Üstbilgi denetimine bir başvuru verir.

```
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

Altta yatan [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Liste denetimi için üstbilgi denetimi, sütunların başlıklarını içeren penceredir. Genellikle sütunların hemen üzerinde konumlandırılır.

## <a name="cmfclistctrlismultiplesort"></a><a name="ismultiplesort"></a>CMFCListCtrl::IsMultipleSort

Liste denetiminin şu anda birden çok sütunda sıralamayı destekleyip desteklemediğini denetler.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste denetimi birden çok sıralamayı destekliyorsa DOĞRU; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

[CMFCListCtrl Sınıfı](../../mfc/reference/cmfclistctrl-class.md) birden çok sıralamayı desteklediğinde, kullanıcı liste denetimindeki verileri birden çok sütuna göre sıralayabilir. Birden çok sıralamayı etkinleştirmek için [CMFCListCtrl'i arayın::MultipleSort'u etkinleştirin.](#enablemultiplesort)

## <a name="cmfclistctrloncompareitems"></a><a name="oncompareitems"></a>CMFCListCtrl::OnCompareItems

Çerçeve, iki öğeyi karşıladığında bu yöntemi çağırır.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>Parametreler

*lParam1*<br/>
[içinde] Karşılaştırılacak ilk öğe.

*lParam2*<br/>
[içinde] Karşılaştırılacak ikinci öğe.

*ıcolumn*<br/>
[içinde] Bu yöntemin sıraladığını sütunun dizin.

### <a name="return-value"></a>Dönüş Değeri

İki öğenin göreli konumunu gösteren bir sonsayı. Negatif değer, ilk öğenin ikinci maddeden önce olması gerektiğini gösterir, pozitif değer ilk öğenin ikinci öğeyi izlemesi gerektiğini gösterir ve sıfır iki öğenin eşdeğer olduğu anlamına gelir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama her zaman 0 döndürür. Kendi sıralama algoritmanızı sağlamak için bu işlevi geçersiz kılın.

## <a name="cmfclistctrlongetcellbkcolor"></a><a name="ongetcellbkcolor"></a>CMFCListCtrl::OnGetCellBkColor

Çerçeve, tek bir hücrenin arka plan rengini belirlemesi gerektiğinde bu yöntemi çağırır.

```
virtual COLORREF OnGetCellBkColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>Parametreler

*nSatır*<br/>
[içinde] Söz konusu hücrenin sırası.

*nSütun*<br/>
[içinde] Söz konusu hücrenin sütunu.

### <a name="return-value"></a>Dönüş Değeri

Hücrenin arka plan rengini belirten bir COLOREF değeri.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama `OnGetCellBkColor` sağlanan giriş parametrelerini kullanmaz ve `GetBkColor`bunun yerine sadece çağırır. Bu nedenle, varsayılan olarak, tüm liste denetimi aynı arka plan renge sahip olacaktır. Hücreleri ayrı `OnGetCellBkColor` bir arka plan rengiyle işaretlemek için türetilmiş bir sınıfta geçersiz kılabilirsiniz.

## <a name="cmfclistctrlongetcellfont"></a><a name="ongetcellfont"></a>CMFCListCtrl::OnGetCellFont

Çerçeve, tek bir hücre için yazı tipi elde ettiğinde bu yöntemi çağırır.

```
virtual HFONT OnGetCellFont(
    int nRow,
    int nColumn,
    DWORD dwData = 0);
```

### <a name="parameters"></a>Parametreler

*nSatır*<br/>
[içinde] Söz konusu hücrenin sırası.

*nSütun*<br/>
[içinde] Söz konusu hücrenin sütunu.

*Dwdata*<br/>
[içinde] Kullanıcı tanımlı veriler. Varsayılan uygulama bu parametreyi kullanmaz.

### <a name="return-value"></a>Dönüş Değeri

Geçerli hücre için kullanılan yazı tipiiçin bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem NULL döndürür. Liste denetimindeki tüm hücreler aynı yazı tipine sahiptir. Farklı hücreler için farklı yazı tipleri sağlamak için bu yöntemi geçersiz kılın.

## <a name="cmfclistctrlongetcelltextcolor"></a><a name="ongetcelltextcolor"></a>CMFCListCtrl::OnGetCellTextColor

Çerçeve, tek bir hücrenin metin rengini belirlemesi gerektiğinde bu yöntemi çağırır.

```
virtual COLORREF OnGetCellTextColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>Parametreler

*nSatır*<br/>
[içinde] Söz konusu hücrenin sırası.

*nSütun*<br/>
[içinde] Söz konusu hücrenin sütunu.

### <a name="return-value"></a>Dönüş Değeri

Hücrenin metin rengini belirten bir COLOREF değeri.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu `GetTextColor` yöntem giriş parametreleri ne olursa olsun çağırır. Tüm liste denetimi aynı metin renge sahip olacaktır. Hücreleri ayrı `OnGetCellTextColor` bir metin rengiyle tek tek işaretlemek için türetilmiş bir sınıfta geçersiz kılabilirsiniz.

## <a name="cmfclistctrlremovesortcolumn"></a><a name="removesortcolumn"></a>CMFCListCtrl::RemoveSortColumn

Sıralanmış sütunlar listesinden bir sıralama sütunu kaldırır.

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>Parametreler

*ıcolumn*<br/>
[içinde] Kaldırılacak sütun.

### <a name="remarks"></a>Açıklamalar

Bu yöntem üstbilgi denetiminden bir sıralama sütunu kaldırır. BU [CMFCHeaderCtrl çağırır::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn).

## <a name="cmfclistctrlsetsortcolumn"></a><a name="setsortcolumn"></a>CMFCListCtrl::SetSortSütun

Geçerli sıralanmış sütunu ve sıralama sırasını ayarlar.

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>Parametreler

*ıcolumn*<br/>
[içinde] Sıralamak için sütun.

*bArtan*<br/>
[içinde] Sıralama sırasını belirten bir Boolean.

*Baran*<br/>
[içinde] Yöntemin *iColumn* tarafından gösterilen sütunu sıralama sütunları listesine ekleyip eklemediğini belirten bir Boolean.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [cmfcheaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn)yöntemini kullanarak giriş parametrelerini üstbilgi denetimine geçirir.

## <a name="cmfclistctrlsort"></a><a name="sort"></a>CMFCListCtrl::Sırala

Liste denetimini sıralar.

```
virtual void Sort(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>Parametreler

*ıcolumn*<br/>
[içinde] Sıralamak için sütun.

*bArtan*<br/>
[içinde] Sıralama sırasını belirten bir Boolean.

*Baran*<br/>
[içinde] Bu yöntemin *iColumn* tarafından gösterilen sütunu sıralama sütunları listesine ekleyip eklemediğini belirten bir Boolean.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CListCtrl Sınıfı](../../mfc/reference/clistctrl-class.md)
