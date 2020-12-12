---
description: 'Daha fazla bilgi edinin: CMFCRibbonSlider sınıfı'
title: CMFCRibbonSlider sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
helpviewer_keywords:
- CMFCRibbonSlider [MFC], CMFCRibbonSlider
- CMFCRibbonSlider [MFC], GetPos
- CMFCRibbonSlider [MFC], GetRangeMax
- CMFCRibbonSlider [MFC], GetRangeMin
- CMFCRibbonSlider [MFC], GetRegularSize
- CMFCRibbonSlider [MFC], GetZoomIncrement
- CMFCRibbonSlider [MFC], HasZoomButtons
- CMFCRibbonSlider [MFC], OnDraw
- CMFCRibbonSlider [MFC], SetPos
- CMFCRibbonSlider [MFC], SetRange
- CMFCRibbonSlider [MFC], SetZoomButtons
- CMFCRibbonSlider [MFC], SetZoomIncrement
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
ms.openlocfilehash: d125afdf961d97c0501742acdc75d7802c7e104d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321740"
---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider sınıfı

`CMFCRibbonSlider`Sınıfı, şerit çubuğuna veya şerit durum çubuğuna ekleyebileceğiniz bir kaydırıcı denetimi uygular. Şerit kaydırıcı denetimi, Office 2007 uygulamalarında görünen yakınlaştırma sürgüleriyle benzerdir.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonSlider : public CMFCRibbonBaseElement
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonSlider:: Cmfcribbonkaydırıcısı](#cmfcribbonslider)|Bir şerit kaydırıcı denetimi oluşturur ve başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonSlider:: GetPos](#getpos)|Kaydırıcı denetiminin geçerli konumunu döndürür.|
|[CMFCRibbonSlider:: GetRangeMax](#getrangemax)|Kaydırıcının en büyük değerini döndürür.|
|[CMFCRibbonSlider:: GetRangeMin](#getrangemin)|Kaydırıcının en küçük değerini döndürür.|
|[CMFCRibbonSlider:: GetRegularSize](#getregularsize)|Şerit öğesinin normal boyutunu döndürür. ( [CMFCRibbonBaseElement:: GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonSlider:: GetZoomIncrement](#getzoomincrement)|Kaydırıcı denetimi için yakınlaştırma artışının boyutunu döndürür.|
|[CMFCRibbonSlider:: HasZoomButtons](#haszoombuttons)|Kaydırıcının yakınlaştırma düğmelerine sahip olup olmadığını belirtir.|
|[CMFCRibbonSlider:: OnDraw](#ondraw)|Şerit öğesi çizmek için Framework tarafından çağırılır. ( [CMFCRibbonBaseElement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw)geçersiz kılar.)|
|[CMFCRibbonSlider:: SetPos](#setpos)|Kaydırıcı denetiminin geçerli konumunu ayarlar.|
|[CMFCRibbonSlider:: SetRange](#setrange)|Minimum ve maksimum değerleri ayarlayarak kaydırıcı denetiminin aralığını belirtir.|
|[CMFCRibbonSlider:: SetZoomButtons](#setzoombuttons)|Yakınlaştırma düğmelerini gösterir veya gizler.|
|[CMFCRibbonSlider:: SetZoomIncrement](#setzoomincrement)|Kaydırıcı denetimi için yakınlaştırma artışının boyutunu ayarlar.|

## <a name="remarks"></a>Açıklamalar

`SetRange`Kaydırıcı için yakınlaştırma artışlarının aralığını yapılandırmak için yöntemini kullanabilirsiniz. Yöntemini kullanarak kaydırıcının geçerli konumunu ayarlayabilirsiniz `SetPos` .

Yöntemini kullanarak kaydırıcı denetiminin sol ve sağ tarafında dairesel yakınlaştırma düğmelerini görüntüleyebilirsiniz `SetZoomButtons` . Varsayılan olarak kaydırıcı yataydır, sol yakınlaştırma düğmesi eksi işareti görüntüler ve sağ yakınlaştırma düğmesi bir artı işareti görüntüler.

`SetZoomIncrement`Yöntemi, Kullanıcı yakınlaştırma düğmelerine tıkladığında geçerli konuma eklenecek veya çıkarılacak artışı tanımlar.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCRibbonSlider` kaydırıcının özelliklerini ayarlamak için sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir. Örnek, bir `CMFCRibbonSlider` nesne oluşturmayı, yakınlaştırma düğmelerini görüntülemeyi, kaydırıcı denetiminin geçerli konumunu ayarlamayı ve kaydırıcı denetimi için değer aralığını ayarlamayı gösterir.

[!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbonkaydırıcısı](../../mfc/reference/cmfcribbonslider-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonslider. h

## <a name="cmfcribbonslidercmfcribbonslider"></a><a name="cmfcribbonslider"></a> CMFCRibbonSlider:: Cmfcribbonkaydırıcısı

Şerit kaydırıcı oluşturun.

```
CMFCRibbonSlider(
    UINT nID,
    int nWidth=100);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
'ndaki Kaydırıcı KIMLIĞI.

[in]. *nWidth* Piksel cinsinden kaydırıcı genişliği.

### <a name="remarks"></a>Açıklamalar

Kaydırıcısının eklendiği panel kategorisinde, *nWidth* piksel genişliğinde olan bir şerit kaydırıcı oluşturur. Varsayılan olarak kaydırıcı yataydır.

## <a name="cmfcribbonslidergetpos"></a><a name="getpos"></a> CMFCRibbonSlider:: GetPos

Kaydırıcı denetiminin geçerli konumunu döndürür.

```
int GetPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcısının başlangıcına göre bir konum olan kaydırıcı denetiminin geçerli konumu.

## <a name="cmfcribbonslidergetrangemax"></a><a name="getrangemax"></a> CMFCRibbonSlider:: GetRangeMax

Kaydırıcının kaydırıcı denetimine geçebileceği kaydırıcının maksimum artışını edinir.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcının kaydırıcı denetimine geçebileceği, kaydırıcının maksimum artışı.

## <a name="cmfcribbonslidergetrangemin"></a><a name="getrangemin"></a> CMFCRibbonSlider:: GetRangeMin

Kaydırıcının kaydırıcı denetimine geçebileceği minimum artışı döndürür.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcının kaydırıcı denetimine geçebileceği en az artış.

## <a name="cmfcribbonslidergetregularsize"></a><a name="getregularsize"></a> CMFCRibbonSlider:: GetRegularSize

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonslidergetzoomincrement"></a><a name="getzoomincrement"></a> CMFCRibbonSlider:: GetZoomIncrement

Kaydırıcı denetimi için yakınlaştırma artışı elde edin.

```
int GetZoomIncrement() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimi için yakınlaştırma artışı.

## <a name="cmfcribbonsliderhaszoombuttons"></a><a name="haszoombuttons"></a> CMFCRibbonSlider:: HasZoomButtons

Kaydırıcının yakınlaştırma düğmelerine sahip olup olmadığını belirtir.

```
BOOL HasZoomButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı yakınlaştırma düğmelerine sahipse TRUE; Aksi takdirde FALSE.

## <a name="cmfcribbonsliderondraw"></a><a name="ondraw"></a> CMFCRibbonSlider:: OnDraw

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonslidersetpos"></a><a name="setpos"></a> CMFCRibbonSlider:: SetPos

Kaydırıcı denetiminin geçerli konumunu ayarlayın.

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
'ndaki Kaydırıcı için ayarlanacak konumu belirtir. Konum, kaydırıcının başlangıcına göre değişir.

*bRedraw*<br/>
'ndaki TRUE ise kaydırıcı yeniden çizilir.

## <a name="cmfcribbonslidersetrange"></a><a name="setrange"></a> CMFCRibbonSlider:: SetRange

Kaydırıcı denetimi için değer aralığını ayarlayın.

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametreler

*Ngünde en az*<br/>
'ndaki Kaydırıcı denetiminin en küçük değerini belirtir.

*Ngünde en çok*<br/>
'ndaki Kaydırıcı denetiminin en büyük değerini belirtir.

### <a name="remarks"></a>Açıklamalar

Minimum ve maksimum değerleri ayarlayarak kaydırıcı denetimi için değer aralığını belirtir.

## <a name="cmfcribbonslidersetzoombuttons"></a><a name="setzoombuttons"></a> CMFCRibbonSlider:: SetZoomButtons

Yakınlaştırma düğmelerini görüntüleyin veya gizleyin.

```cpp
void SetZoomButtons(BOOL bSet=TRUE);
```

### <a name="parameters"></a>Parametreler

[in]. *bSet* Yakınlaştırma düğmelerini göstermek için TRUE; Bunları gizlemek için FALSE.

## <a name="cmfcribbonslidersetzoomincrement"></a><a name="setzoomincrement"></a> CMFCRibbonSlider:: SetZoomIncrement

Kaydırıcı denetimi için yakınlaştırma artışı ayarlayın.

```cpp
void SetZoomIncrement(int nZoomIncrement);
```

### <a name="parameters"></a>Parametreler

*nZoomIncrement*<br/>
'ndaki Kaydırıcı denetiminin yakınlaştırma artışını belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBaseElement sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)
