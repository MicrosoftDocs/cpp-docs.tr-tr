---
title: CMFCRibbonSlider Sınıfı
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
ms.openlocfilehash: 304581371c68817c6031153c3cec227137771c5d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754067"
---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider Sınıfı

Sınıf, `CMFCRibbonSlider` şerit çubuğuna veya şerit durum çubuğuna ekleyebileceğiniz bir kaydırıcı denetimi uygular. Şerit kaydırıcı denetimi, Office 2007 uygulamalarında görünen yakınlaştırma kaydırıcılarını benzer.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonSlider : public CMFCRibbonBaseElement
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|Şerit kaydırıcı denetimini kurar ve başharfe ait hale sağlar.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonSlider::GetPos](#getpos)|Kaydırıcı denetiminin geçerli konumunu döndürür.|
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|Kaydırıcının maksimum değerini verir.|
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|Kaydırıcının minimum değerini verir.|
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|Şerit öğesinin normal boyutunu döndürür. [(CMFCRibbonBaseElement geçersiz kılar::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|Kaydırıcı denetimi için yakınlaştırma artış boyutunu döndürür.|
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|Kaydırıcının yakınlaştırma düğmeleri olup olmadığını belirtir.|
|[CMFCRibbonSlider::OnDraw](#ondraw)|Şerit öğesini çizmek için çerçeve tarafından çağrılır. [(CMFCRibbonBaseElement geçersiz kılar::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[CMFCRibbonSlider::SetPos](#setpos)|Kaydırıcı denetiminin geçerli konumunu ayarlar.|
|[CMFCRibbonSlider::SetRange](#setrange)|Minimum ve maksimum değerleri ayarlayarak kaydırıcı denetiminin aralığını belirtir.|
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|Yakınlaştırma düğmelerini gösterir veya gizler.|
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|Kaydırıcı denetimi için yakınlaştırma nın boyutunu ayarlar.|

## <a name="remarks"></a>Açıklamalar

Kaydırıcı için `SetRange` yakınlaştırma artışlarını yapılandırmak için yöntemi kullanabilirsiniz. `SetPos` Yöntemi kullanarak kaydırıcının geçerli konumunu ayarlayabilirsiniz.

`SetZoomButtons` Yöntemi kullanarak kaydırıcı denetiminin sol ve sağ tarafında dairesel yakınlaştırma düğmelerini görüntüleyebilirsiniz. Varsayılan olarak kaydırıcı yatay, sol yakınlaştırma düğmesi eksi işareti ve sağ yakınlaştırma düğmesi artı bir işaret görüntüler.

Yöntem, `SetZoomIncrement` kullanıcı yakınlaştırma düğmelerini tıklattığında geçerli konuma eklemek veya çıkarmak için yapılan artıştanımlar.

## <a name="example"></a>Örnek

Aşağıdaki örnek, kaydırıcının `CMFCRibbonSlider` özelliklerini ayarlamak için sınıfta çeşitli yöntemlerin nasıl kullanılacağını gösterir. Örnek, bir `CMFCRibbonSlider` nesnenin nasıl oluşturulabildiğini, yakınlaştırma düğmelerini nasıl görüntülenebildiğini, kaydırıcı denetiminin geçerli konumunu nasıl ayarlayıp kaydırıcı denetimi için değerler aralığını ayarlayabilirsiniz.

[!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbonslider](../../mfc/reference/cmfcribbonslider-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonslider.h

## <a name="cmfcribbonslidercmfcribbonslider"></a><a name="cmfcribbonslider"></a>CMFCRibbonSlider::CMFCRibbonSlider

Bir şerit kaydırıcısı oluştur.

```
CMFCRibbonSlider(
    UINT nID,
    int nWidth=100);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
[içinde] Kaydırıcı kimliği.

[içinde]. *nGenişlik* Piksellerde kaydırıcı genişliği.

### <a name="remarks"></a>Açıklamalar

Kaydırıcının eklendiği panel kategorisinde *nGeniş piksel* genişliğinde bir şerit kaydırıcısı oluşur. Varsayılan olarak, kaydırıcı yataydır.

## <a name="cmfcribbonslidergetpos"></a><a name="getpos"></a>CMFCRibbonSlider::GetPos

Kaydırıcı denetiminin geçerli konumunu döndürür.

```
int GetPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetiminin geçerli konumu, kaydırıcının başına göre bir konumdur.

## <a name="cmfcribbonslidergetrangemax"></a><a name="getrangemax"></a>CMFCRibbonSlider::GetRangeMax

Kaydırıcının kaydırıcı nın kaydırıcı kontrolünde hareket edebileceği maksimum artış sağlar.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcının kaydırıcı nın kaydırıcı denetiminde kullanabileceği maksimum artış.

## <a name="cmfcribbonslidergetrangemin"></a><a name="getrangemin"></a>CMFCRibbonSlider::GetRangeMin

Kaydırıcının kaydırıcı denetiminde kullanabileceği minimum artış verir.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcının kaydırıcı denetiminde seyahat edebileceği minimum artış.

## <a name="cmfcribbonslidergetregularsize"></a><a name="getregularsize"></a>CMFCRibbonSlider::GetRegularSize

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonslidergetzoomincrement"></a><a name="getzoomincrement"></a>CMFCRibbonSlider::GetZoomIncrement

Kaydırıcı denetimi için yakınlaştırma artışını elde edin.

```
int GetZoomIncrement() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcı denetimi için yakınlaştırma artımı.

## <a name="cmfcribbonsliderhaszoombuttons"></a><a name="haszoombuttons"></a>CMFCRibbonSlider::HasZoomButtons

Kaydırıcının yakınlaştırma düğmeleri olup olmadığını belirtir.

```
BOOL HasZoomButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaydırıcının yakınlaştırma düğmeleri varsa DOĞRU; YANLIŞ aksi takdirde.

## <a name="cmfcribbonsliderondraw"></a><a name="ondraw"></a>CMFCRibbonSlider::OnDraw

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDC*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonslidersetpos"></a><a name="setpos"></a>CMFCRibbonSlider::SetPos

Kaydırıcı denetiminin geçerli konumunu ayarlayın.

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
[içinde] Kaydırıcı için ayarlanan konumu belirtir. Konum kaydırıcının başına göredir.

*bRedraw*<br/>
[içinde] TRUE ise, kaydırıcı yeniden çizilir.

## <a name="cmfcribbonslidersetrange"></a><a name="setrange"></a>CMFCRibbonSlider::SetRange

Kaydırıcı denetimi için değer aralığını ayarlayın.

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
[içinde] Kaydırıcı denetiminin minimum değerini belirtir.

*nMax*<br/>
[içinde] Kaydırıcı denetiminin maksimum değerini belirtir.

### <a name="remarks"></a>Açıklamalar

Minimum ve maksimum değerleri ayarlayarak kaydırıcı denetimi için değer aralığını belirtir.

## <a name="cmfcribbonslidersetzoombuttons"></a><a name="setzoombuttons"></a>CMFCRibbonSlider::SetZoomButtons

Yakınlaştırma düğmelerini görüntüleyin veya gizleyin.

```cpp
void SetZoomButtons(BOOL bSet=TRUE);
```

### <a name="parameters"></a>Parametreler

[içinde]. *bSet* Zoom düğmelerini görüntülemek için DOĞRU; YANLIŞ onları gizlemek için.

## <a name="cmfcribbonslidersetzoomincrement"></a><a name="setzoomincrement"></a>CMFCRibbonSlider::SetZoomIncrement

Kaydırıcı denetimi için yakınlaştırma artışını ayarlayın.

```cpp
void SetZoomIncrement(int nZoomIncrement);
```

### <a name="parameters"></a>Parametreler

*nZoomIncrement*<br/>
[içinde] Kaydırıcı denetiminin yakınlaştırma artışını belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBaseElement Sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)
