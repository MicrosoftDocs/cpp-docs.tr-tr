---
description: 'Daha fazla bilgi edinin: CMFCRibbonProgressBar sınıfı'
title: CMFCRibbonProgressBar sınıfı
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
ms.openlocfilehash: b4e91a604386a57aa7cac59294c569635583304c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321767"
---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar sınıfı

Uzun bir işlemin ilerlemesini görsel olarak gösteren bir denetim uygular.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonProgressBar:: CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Bir nesnesi oluşturur ve başlatır `CMFCRibbonProgressBar` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonProgressBar:: GetPos](#getpos)|Geçerli ilerlemeyi döndürür.|
|[CMFCRibbonProgressBar:: GetRangeMax](#getrangemax)|Geçerli aralığın en büyük değerini döndürür.|
|[CMFCRibbonProgressBar:: GetRangeMin](#getrangemin)|Geçerli aralığın en küçük değerini döndürür.|
|[CMFCRibbonProgressBar:: GetRegularSize](#getregularsize)|Şerit öğesinin normal boyutunu döndürür. ( [CMFCRibbonBaseElement:: GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonProgressBar:: ısınfinitemode](#isinfinitemode)|İlerleme çubuğunun sonsuz modda çalışıp çalışmadığını belirtir.|
|[CMFCRibbonProgressBar:: OnDraw](#ondraw)|Şerit öğesi çizmek için Framework tarafından çağırılır. ( [CMFCRibbonBaseElement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw)geçersiz kılar.)|
|[CMFCRibbonProgressBar:: Setınfinitemode](#setinfinitemode)|İlerleme çubuğunu sonsuz modda çalışacak şekilde ayarlar.|
|[CMFCRibbonProgressBar:: SetPos](#setpos)|Geçerli ilerlemeyi ayarlar.|
|[CMFCRibbonProgressBar:: SetRange](#setrange)|Minimum ve maksimum değerleri ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CMFCRibbonProgressBar`, İki modda çalışabilir: normal ve sonsuz. Normal modda, ilerleme çubuğu soldan sağa doldurulur ve en büyük değere ulaştığında duraklar. Sonsuz modda, ilerleme çubuğu en küçük değerden tekrar en büyük değere kadar doldurulur. Bir işlemin devam etmekte olduğunu, ancak tamamlanma süresinin bilinmediğini göstermek için sonsuz modu kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCRibbonProgressBar` . Örnekte, ilerleme çubuğunun sonsuz modda çalışacak şekilde nasıl ayarlanacağı gösterilmektedir (bir işlemin tamamlanma zamanı bilinmiyor), ilerleme çubuğunun minimum ve maksimum değerlerini ayarlayın ve ilerleme çubuğunun geçerli konumunu ayarlayın. Bu kod parçacığı, [MS Office 2007 demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonProgressBar. h

## <a name="cmfcribbonprogressbarcmfcribbonprogressbar"></a><a name="cmfcribbonprogressbar"></a> CMFCRibbonProgressBar:: CMFCRibbonProgressBar

Bir [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) nesnesi oluşturur ve başlatır.

```
CMFCRibbonProgressBar();

CMFCRibbonProgressBar(
    UINT nID,
    int nWidth = 90,
    int nHeight = 22);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
'ndaki Şerit ilerleme çubuğu için komut KIMLIĞINI belirtir.

*nWidth*<br/>
'ndaki Şerit ilerleme çubuğunun genişliğini piksel cinsinden belirtir.

*nHeight*<br/>
'ndaki Şerit ilerleme çubuğunun yüksekliğini piksel cinsinden belirtir.

## <a name="cmfcribbonprogressbargetpos"></a><a name="getpos"></a> CMFCRibbonProgressBar:: GetPos

İlerleme çubuğunun geçerli konumunu döndürür.

```
int GetPos () const;
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğunun geçerli konumunu temsil eden bir değer.

### <a name="remarks"></a>Açıklamalar

Ayarlanan Aralık [CMFCRibbonProgressBar:: SetRange](#setrange) yöntemi tarafından belirtilen aralık dahilinde olmalıdır.

## <a name="cmfcribbonprogressbargetrangemax"></a><a name="getrangemax"></a> CMFCRibbonProgressBar:: GetRangeMax

İlerleme çubuğunun geçerli en büyük değerini döndürür.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli aralığın en büyük değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonprogressbargetrangemin"></a><a name="getrangemin"></a> CMFCRibbonProgressBar:: GetRangeMin

İlerleme çubuğunun geçerli en düşük Aralık değerini döndürür.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli aralığın en küçük değeri.

## <a name="cmfcribbonprogressbargetregularsize"></a><a name="getregularsize"></a> CMFCRibbonProgressBar:: GetRegularSize

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonprogressbarisinfinitemode"></a><a name="isinfinitemode"></a> CMFCRibbonProgressBar:: ısınfinitemode

İlerleme çubuğunun sonsuz modda çalışıp çalışmadığını belirtir.

```
BOOL IsInfiniteMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlerleme çubuğu sonsuz modundaysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Sonsuz modda, ilerleme çubuğu en küçük değerden en yüksek değere kadar bir kez doldurulur. Bir işlemin devam etmekte olduğunu, ancak tamamlanma süresinin bilinmediğini göstermek için sonsuz modu kullanabilirsiniz.

## <a name="cmfcribbonprogressbarondraw"></a><a name="ondraw"></a> CMFCRibbonProgressBar:: OnDraw

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonprogressbarsetinfinitemode"></a><a name="setinfinitemode"></a> CMFCRibbonProgressBar:: Setınfinitemode

İlerleme çubuğunu sonsuz modda çalışacak şekilde ayarlar.

```cpp
void SetInfiniteMode(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSet*<br/>
'ndaki İlerleme çubuğunun sonsuz modda olduğunu belirtmek için TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Genellikle, ilerleme çubuğu sonsuz modundaysa, kullanıcıya bir işlemin devam ettiğini, ancak tamamlanma süresinin bilinmediğini belirten bir yol vardır. Bu nedenle, ilerleme çubuğu en küçük değerden en yüksek değere kadar bir kez doldurulur.

## <a name="cmfcribbonprogressbarsetpos"></a><a name="setpos"></a> CMFCRibbonProgressBar:: SetPos

İlerleme çubuğunun geçerli konumunu ayarlar.

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
'ndaki İlerleme çubuğunun ayarlandığı konumu belirtir.

*bRedraw*<br/>
'ndaki İlerleme çubuğunun yeniden çizilip çizmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

Ayarlanan Aralık [CMFCRibbonProgressBar:: SetRange](#setrange) yöntemi tarafından belirtilen aralık dahilinde olmalıdır.

## <a name="cmfcribbonprogressbarsetrange"></a><a name="setrange"></a> CMFCRibbonProgressBar:: SetRange

İlerleme çubuğu için en düşük ve en yüksek değerleri ayarlar.

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametreler

*Ngünde en az*<br/>
'ndaki Aralığın en küçük değerini belirtir.

*Ngünde en çok*<br/>
'ndaki Aralığın en büyük değerini belirtir.

### <a name="remarks"></a>Açıklamalar

En düşük ve en yüksek değerleri ayarlayarak ilerleme çubuğunun aralığını tanımlamak için bu yöntemi kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBaseElement sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
