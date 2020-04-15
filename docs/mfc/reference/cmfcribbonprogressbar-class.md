---
title: CMFCRibbonProgressBar Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
ms.openlocfilehash: 063f8ce560af84d350abc0114644f6a63f969f95
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368857"
---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar Sınıfı

Uzun bir işlemin ilerlemesini görsel olarak gösteren bir denetim uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Bir `CMFCRibbonProgressBar` nesne yi inşa eder ve başharfe ait hale raz.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonProgressBar::GetPos](#getpos)|Geçerli ilerlemeyi döndürür.|
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|Geçerli aralığın maksimum değerini verir.|
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|Geçerli aralığın minimum değerini verir.|
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|Şerit öğesinin normal boyutunu döndürür. [(CMFCRibbonBaseElement geçersiz kılar::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|İlerleme çubuğunun sonsuz modda çalışıp çalışmadığını belirtir.|
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|Şerit öğesini çizmek için çerçeve tarafından çağrılır. [(CMFCRibbonBaseElement geçersiz kılar::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|İlerleme çubuğunu sonsuz modda çalışacak şekilde ayarlar.|
|[CMFCRibbonProgressBar::SetPos](#setpos)|Geçerli ilerlemeyi ayarlar.|
|[CMFCRibbonProgressBar::SetRange](#setrange)|Minimum ve maksimum değerleri ayarlar.|

## <a name="remarks"></a>Açıklamalar

A `CMFCRibbonProgressBar` iki modda çalışabilir: normal ve sonsuz. Normal modda, ilerleme çubuğu soldan sağa doldurulur ve maksimum değere ulaştığında durur. Sonsuz modda, ilerleme çubuğu sürekli olarak minimum değerden maksimum değere doldurulur. Bir işlemin devam ettiğini, ancak tamamlanma süresinin bilinmediğini belirtmek için sonsuz modu kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCRibbonProgressBar` nasıl kullanılacağını göstermektedir. Örnek, ilerleme çubuğunun sonsuz modda nasıl çalışacağını (bir işlemin tamamlanma süresinin bilinmemesi durumunda), ilerleme çubuğu için minimum ve en büyük değerleri ayarlamayı ve ilerleme çubuğunun geçerli konumunu nasıl ayarlayabileceğinizi gösterir. Bu kod parçacığı MS Office [2007 Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbonprogressbar](../../mfc/reference/cmfcribbonprogressbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonProgressBar.h

## <a name="cmfcribbonprogressbarcmfcribbonprogressbar"></a><a name="cmfcribbonprogressbar"></a>CMFCRibbonProgressBar::CMFCRibbonProgressBar

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) nesnesi oluşturuyor ve başharflerini.

```
CMFCRibbonProgressBar();

CMFCRibbonProgressBar(
    UINT nID,
    int nWidth = 90,
    int nHeight = 22);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
[içinde] Şerit ilerleme çubuğunun komut kimliğini belirtir.

*Nwidth*<br/>
[içinde] Şerit ilerleme çubuğunun piksel olarak genişliğini belirtir.

*Nheight*<br/>
[içinde] Şerit ilerleme çubuğunun yüksekliğini, piksel olarak belirtir.

## <a name="cmfcribbonprogressbargetpos"></a><a name="getpos"></a>CMFCRibbonProgressBar::GetPos

İlerleme çubuğunun geçerli konumunu döndürür.

```
int GetPos () const;
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğunun geçerli konumunu temsil eden bir değer.

### <a name="remarks"></a>Açıklamalar

Ayarlanan aralık [CMFCRibbonProgressBar::SetRange](#setrange) yöntemi tarafından belirtilen aralıkiçinde olmalıdır.

## <a name="cmfcribbonprogressbargetrangemax"></a><a name="getrangemax"></a>CMFCRibbonProgressBar::GetRangeMax

İlerleme çubuğunun geçerli maksimum değerini verir.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli aralığın maksimum değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonprogressbargetrangemin"></a><a name="getrangemin"></a>CMFCRibbonProgressBar::GetRangeMin

İlerleme çubuğunun geçerli minimum aralık değerini verir.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli aralığın minimum değeri.

## <a name="cmfcribbonprogressbargetregularsize"></a><a name="getregularsize"></a>CMFCRibbonProgressBar::GetRegularSize

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonprogressbarisinfinitemode"></a><a name="isinfinitemode"></a>CMFCRibbonProgressBar::IsInfiniteMode

İlerleme çubuğunun sonsuz modda çalışıp çalışmadığını belirtir.

```
BOOL IsInfiniteMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu sonsuz moddaysa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Sonsuz modda, ilerleme çubuğu en küçük değerden maksimum değere tekrar tekrar doldurur. Bir işlemin devam ettiğini, ancak tamamlanma süresinin bilinmediğini belirtmek için sonsuz modu kullanabilirsiniz.

## <a name="cmfcribbonprogressbarondraw"></a><a name="ondraw"></a>CMFCRibbonProgressBar::OnDraw

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDC*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonprogressbarsetinfinitemode"></a><a name="setinfinitemode"></a>CMFCRibbonProgressBar::SetInfiniteMode

İlerleme çubuğunu sonsuz modda çalışacak şekilde ayarlar.

```
void SetInfiniteMode(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSet*<br/>
[içinde] İlerleme çubuğunun sonsuz modda olduğunu belirtmek için TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Genellikle, ilerleme çubuğu sonsuz moddaysa, kullanıcıya bir işlemin devam ettiğini, ancak tamamlanma süresinin bilinmediğini söyler. Böylece, ilerleme çubuğu en küçük değerden maksimum değere tekrar tekrar doldurur.

## <a name="cmfcribbonprogressbarsetpos"></a><a name="setpos"></a>CMFCRibbonProgressBar::SetPos

İlerleme çubuğunun geçerli konumunu ayarlar.

```
void SetPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
[içinde] İlerleme çubuğunun ayarlandığı konumu belirtir.

*bRedraw*<br/>
[içinde] İlerleme çubuğunun yeniden çizilip çizilmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

Ayarlanan aralık [CMFCRibbonProgressBar::SetRange](#setrange) yöntemi tarafından belirtilen aralıkiçinde olmalıdır.

## <a name="cmfcribbonprogressbarsetrange"></a><a name="setrange"></a>CMFCRibbonProgressBar::SetRange

İlerleme çubuğu için minimum ve maksimum değerleri ayarlar.

```
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
[içinde] Aralığın minimum değerini belirtir.

*nMax*<br/>
[içinde] Aralığın maksimum değerini belirtir.

### <a name="remarks"></a>Açıklamalar

En küçük ve en büyük değerleri ayarlayarak ilerleme çubuğunun aralığını tanımlamak için bu yöntemi kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBaseElement Sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
