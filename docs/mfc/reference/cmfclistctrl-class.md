---
title: CMFCListCtrl sınıfı
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
ms.openlocfilehash: 599a00af28ee5b8effbabbe5b334022ceb49f91a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79420318"
---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl sınıfı

`CMFCListCtrl` sınıfı, [CMFCHeaderCtrl sınıfının](../../mfc/reference/cmfcheaderctrl-class.md)gelişmiş üstbilgi denetimi Işlevini destekleyerek [clienstctrl Class](../../mfc/reference/clistctrl-class.md) sınıfının işlevselliğini genişletir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCListCtrl : public CListCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CMFCListCtrl:: EnableMarkSortedColumn](#enablemarksortedcolumn)|Sıralanmış bir sütunu farklı bir arka plan rengiyle işaretleyebilme olanağı tanır.|
|[CMFCListCtrl:: EnableMultipleSort](#enablemultiplesort)|Birden çok sıralama moduna izin vermez.|
|[CMFCListCtrl:: GetHeaderCtrl](#getheaderctrl)|Altı çizili üstbilgi denetimine bir başvuru döndürür.|
|[CMFCListCtrl:: Ismultiplesıralaması](#ismultiplesort)|Liste denetiminin birden çok sıralama modunda olup olmadığını denetler.|
|[CMFCListCtrl:: OnCompareItems](#oncompareitems)|İki liste denetim öğesini karşılaştırmanız gerektiğinde Framework tarafından çağırılır.|
|[CMFCListCtrl:: OnGetCellBkColor](#ongetcellbkcolor)|Tek bir hücrenin arka plan rengini belirlemesi gerektiğinde Framework tarafından çağırılır.|
|[CMFCListCtrl:: OnGetCellFont](#ongetcellfont)|Çizilemekte olan hücrenin yazı tipini alması gereken Framework tarafından çağırılır.|
|[CMFCListCtrl:: OnGetCellTextColor](#ongetcelltextcolor)|Tek bir hücrenin metin rengini belirlemesi gerektiğinde Framework tarafından çağırılır.|
|[CMFCListCtrl:: RemoveSortColumn](#removesortcolumn)|Sıralanmış sütunlar listesinden bir sıralama sütununu kaldırır.|
|[CMFCListCtrl:: SetSortColumn](#setsortcolumn)|Geçerli sıralanmış sütunu ve sıralama düzenini ayarlar.|
|[CMFCListCtrl:: Sort](#sort)|Liste denetimini sıralar.|

## <a name="remarks"></a>Açıklamalar

`CMFCListCtrl` [Clienstctrl sınıf](../../mfc/reference/clistctrl-class.md) sınıfında iki geliştirme sunar. İlk olarak, üst bilgide bir sıralama okunu otomatik olarak çizerek sütun sıralamanın kullanılabilir bir seçenek olduğunu gösterir. İkincisi, aynı anda birden çok sütunda veri sıralamayı destekler.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCListCtrl` sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir. Örnek, bir liste denetimi oluşturma, sütun ekleme, öğe ekleme, öğe metin ayarlama ve liste denetiminin yazı tipini ayarlama işlemlerinin nasıl yapılacağını gösterir. Bu kod parçacığı, [Visual Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListCtrl](../../mfc/reference/clistctrl-class.md)

[CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxlistctrl. h

##  <a name="enablemarksortedcolumn"></a>CMFCListCtrl:: EnableMarkSortedColumn

Sıralanan sütunları farklı bir arka plan rengiyle işaretler.

```
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*bMark*<br/>
'ndaki Farklı bir arka plan renginin etkinleştirilip etkinleştirilmeyeceğini belirleyen bir Boolean parametresi.

*bRedraw*<br/>
'ndaki Denetimin hemen yeniden çizilip çizmeyeceğini belirleyen bir Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

`EnableMarkSortedColumn`, sıralanan sütunlarda kullanılacak rengi hesaplamak için `CDrawingManager::PixelAlpha` yöntemini kullanır. Çekilen renk, normal arka plan rengine göre belirlenir.

##  <a name="enablemultiplesort"></a>CMFCListCtrl:: EnableMultipleSort

Liste denetimindeki veri satırlarını birden çok sütuna göre sıralamaya izin vermez.

```
void EnableMultipleSort(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Birden çok sütunlu sıralama modunun etkinleştirilip etkinleştirilmeyeceğini belirten bir Boole değeri.

### <a name="remarks"></a>Açıklamalar

Sıralamayı birden çok sütuna göre etkinleştirdiğinizde, sütunların bir hiyerarşisi vardır. Verilerin satırları ilk olarak birincil sütuna göre sıralanır. Bundan sonra eşdeğer değerler, öncelik temelinde izleyen her sütuna göre sıralanır.

##  <a name="getheaderctrl"></a>CMFCListCtrl:: GetHeaderCtrl

Üstbilgi denetimine bir başvuru döndürür.

```
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Liste denetimi için üst bilgi denetimi, sütunların başlıklarını içeren penceresidir. Genellikle sütunların üzerinde doğrudan konumlandırılır.

##  <a name="ismultiplesort"></a>CMFCListCtrl:: Ismultiplesıralaması

Liste denetiminin Şu anda birden çok sütunda sıralamayı destekleyip desteklemediğini denetler.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Dönüş Değeri

Liste denetimi birden çok sıralamayı destekliyorsa doğru. Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir [CMFCListCtrl sınıfı](../../mfc/reference/cmfclistctrl-class.md) birden çok sıralamayı desteklediğinde, Kullanıcı liste denetimindeki verileri birden çok sütuna göre sıralayabilir. Birden çok sıralamayı etkinleştirmek için [CMFCListCtrl:: EnableMultipleSort](#enablemultiplesort)komutunu çağırın.

##  <a name="oncompareitems"></a>CMFCListCtrl:: OnCompareItems

Framework iki öğeyi karşılaştırırken bu yöntemi çağırır.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>Parametreler

*lParam1*<br/>
'ndaki Karşılaştırılacak ilk öğe.

*lParam2*<br/>
'ndaki Karşılaştırılacak ikinci öğe.

*ıolumn*<br/>
'ndaki Bu yöntemin sıralama yaptığınız sütunun dizini.

### <a name="return-value"></a>Dönüş Değeri

İki öğenin göreli konumunu gösteren bir tamsayı. Negatif bir değer, ilk öğenin ikinciden önce gelmesi gerektiğini gösterir, pozitif bir değer ilk öğenin ikincisini izlemesi gerektiğini, sıfır ise iki öğenin eşdeğer olduğu anlamına gelir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama her zaman 0 döndürür. Kendi sıralama algoritmanızı sağlamak için bu işlevi geçersiz kılın.

##  <a name="ongetcellbkcolor"></a>CMFCListCtrl:: OnGetCellBkColor

Çerçeve, tek bir hücrenin arka plan rengini belirlemesi gerektiğinde bu yöntemi çağırır.

```
virtual COLORREF OnGetCellBkColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>Parametreler

*Nsatır*<br/>
'ndaki Söz konusu hücrenin satırı.

*Nsütun*<br/>
'ndaki Söz konusu hücrenin sütunu.

### <a name="return-value"></a>Dönüş Değeri

Hücrenin arka plan rengini belirten bir birlikte bulunan başvuru değeri.

### <a name="remarks"></a>Açıklamalar

`OnGetCellBkColor` varsayılan uygulanması, sağlanan giriş parametrelerini kullanmaz ve bunun yerine `GetBkColor`çağırır. Bu nedenle, varsayılan olarak tüm liste denetimi aynı arka plan rengine sahip olur. Tek tek hücreleri ayrı bir arka plan rengiyle işaretlemek için türetilmiş bir sınıftaki `OnGetCellBkColor` geçersiz kılabilirsiniz.

##  <a name="ongetcellfont"></a>CMFCListCtrl:: OnGetCellFont

Çerçeve, tek bir hücrenin yazı tipini aldığında bu yöntemi çağırır.

```
virtual HFONT OnGetCellFont(
    int nRow,
    int nColumn,
    DWORD dwData = 0);
```

### <a name="parameters"></a>Parametreler

*Nsatır*<br/>
'ndaki Söz konusu hücrenin satırı.

*Nsütun*<br/>
'ndaki Söz konusu hücrenin sütunu.

*dwData*<br/>
'ndaki Kullanıcı tanımlı veriler. Varsayılan uygulama bu parametreyi kullanmaz.

### <a name="return-value"></a>Dönüş Değeri

Geçerli hücre için kullanılan yazı tipine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem NULL değerini döndürür. Liste denetimindeki tüm hücreler aynı yazı tipine sahip. Farklı hücrelere farklı yazı tipleri sağlamak için bu yöntemi geçersiz kılın.

##  <a name="ongetcelltextcolor"></a>CMFCListCtrl:: OnGetCellTextColor

Çerçeve, tek bir hücrenin metin rengini belirlemesi gerektiğinde bu yöntemi çağırır.

```
virtual COLORREF OnGetCellTextColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>Parametreler

*Nsatır*<br/>
'ndaki Söz konusu hücrenin satırı.

*Nsütun*<br/>
'ndaki Söz konusu hücrenin sütunu.

### <a name="return-value"></a>Dönüş Değeri

Hücrenin metin rengini belirten bir birlikte bulunan başvuru değeri.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem giriş parametrelerinden bağımsız olarak `GetTextColor` çağırır. Tüm liste denetimi aynı metin rengine sahip olur. Tek tek hücreleri ayrı bir metin rengiyle işaretlemek için türetilmiş bir sınıftaki `OnGetCellTextColor` geçersiz kılabilirsiniz.

##  <a name="removesortcolumn"></a>CMFCListCtrl:: RemoveSortColumn

Sıralanmış sütunlar listesinden bir sıralama sütununu kaldırır.

```
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>Parametreler

*ıolumn*<br/>
'ndaki Kaldırılacak sütun.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, üst bilgi denetiminden bir sıralama sütununu kaldırır. [CMFCHeaderCtrl:: RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn)öğesini çağırır.

##  <a name="setsortcolumn"></a>CMFCListCtrl:: SetSortColumn

Geçerli sıralanmış sütunu ve sıralama düzenini ayarlar.

```
void SetSortColumn(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>Parametreler

*ıolumn*<br/>
'ndaki Sıralanacak sütun.

*Bascbitiriliyor*<br/>
'ndaki Sıralama düzenini belirten bir Boole değeri.

*bAdd*<br/>
'ndaki Yöntemin, *ıolumn* tarafından belirtilen sütunu sıralama sütunları listesine ekleyip eklememeyeceğini belirten bir Boole değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CMFCHeaderCtrl:: SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn)metodunu kullanarak giriş parametrelerini üstbilgi denetimine geçirir.

##  <a name="sort"></a>CMFCListCtrl:: Sort

Liste denetimini sıralar.

```
virtual void Sort(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>Parametreler

*ıolumn*<br/>
'ndaki Sıralanacak sütun.

*Bascbitiriliyor*<br/>
'ndaki Sıralama düzenini belirten bir Boole değeri.

*bAdd*<br/>
'ndaki Bu yöntemin, *ıolumn* tarafından belirtilen sütunu sıralama sütunları listesine ekleyip eklememeyeceğini belirten bir Boole değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CListCtrl Sınıfı](../../mfc/reference/clistctrl-class.md)
