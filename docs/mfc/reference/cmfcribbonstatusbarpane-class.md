---
title: CMFCRibbonStatusBarPane sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0b3d012f74706806c1486b38180cd1c69beef2e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053845"
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane sınıfı

`CMFCRibbonStatusBarPane` Sınıfı bir Şerit durum çubuğuna ekleyebileceğiniz bir Şerit öğesi uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonStatusBarPane : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Oluşturur ve başlatır bir `CMFCRibbonStatusBarPane` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Kesmeden bölmesinde görüntülenen en uzun metin dizesi tanımlayan dizeyi döndürür.|
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|Metin hizalama geçerli ayarını döndürür.|
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|Animasyon ediyor olup olmadığını belirler.|
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|Bölmesini Şerit durum çubuğuna genişletilmiş bölümünde bulunup bulunmadığını belirler.|
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(Geçersiz kılmaları [CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(Geçersiz kılmaları [CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Kesmeden bölmesinde görüntülenebilen en uzun metin dizesini tanımlar.|
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Animasyon için kullanılabilecek bir görüntü listesi bölmesine atar.|
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Metin hizalamasını ayarlar.|
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Bölmesine atanan animasyonu başlatır.|
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Bölmesine atanan animasyon durdurur. biçimindeki telefon numarasıdır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Bölmesine atanan animasyon durduğunda framework tarafından çağırılır.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCRibbonStatusBarPane` sınıfı. Bu örnek nasıl oluşturulacağını gösterir. bir `CMFCRibbonStatusBarPane` nesne, durum çubuğu bölmesinin etiketin metin hizalamayı ayarlama, kesmeden durum çubuğu bölmesinde görüntülenen, durum çubuğu bölmesine eklemek için kullanılabilecek bir görüntü listesi en uzun metin tanımlayan bir Meti ve animasyon başlangıç.

[!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxribbonstatusbarpane.h

##  <a name="cmfcribbonstatusbarpane"></a>  CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane

Durum çubuğunda bir bölmesi nesnesi oluşturur.

```
CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    BOOL bIsStatic=FALSE,
    HICON hIcon=NULL,
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);
```

### <a name="parameters"></a>Parametreler

*nCmdID*<br/>
[in] Bölmenin komut Kimliğini belirtir.

*lpszText*<br/>
[in] Bölmesinde görüntülenecek metin dizesi belirtir.

*bIsStatic*<br/>
[in] TRUE ise, durumu bölmesinde vurgulanmış veya olamaz tıklayarak seçili.

*hIcon*<br/>
[in] Bölmesinde görüntülenecek bir simge için bir tanıtıcı belirtir.

*lpszAlmostLargeText*<br/>
[in] Bölmede görüntülenen en uzun metin dizesi belirtir.

*hBmpAnimationList*<br/>
[in] Animasyon için kullanılan bir görüntü listesi için bir tanıtıcı belirtir.

*cxAnimation*<br/>
[in] Piksel cinsinden görüntü listesinde animasyon için kullanılan simge genişliğini belirtir.

*clrTrnsp*<br/>
[in] Animasyon için kullanılan görüntü listesinde görüntüleri saydam rengini belirtir.

*uiAnimationListResID*<br/>
[in] Animasyon için kullanılan bir görüntü listesi kaynak Kimliğini belirtir.

##  <a name="getalmostlargetext"></a>  CMFCRibbonStatusBarPane::GetAlmostLargeText

Durum çubuğu bölmesini görüntülemek en uzun metin dizesi alır.

```
LPCTSTR GetAlmostLargeText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu bölmesini görüntülemek en uzun metin dizesi.

##  <a name="gettextalign"></a>  CMFCRibbonStatusBarPane::GetTextAlign

Durum çubuğu bölmesinin etiketin metin hizalamasını geçerli ayarını alır.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdakilerden herhangi birini geçerli metin hizalama:

- TA_LEFT

- TA_CENTER

- TA_RIGHT.

##  <a name="isanimation"></a>  CMFCRibbonStatusBarPane::IsAnimation

Animasyon ediyor olup olmadığını belirler.

```
BOOL IsAnimation() const;
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon sürüyorsa TRUE; FALSE Aksi takdirde.

##  <a name="isextended"></a>  CMFCRibbonStatusBarPane::IsExtended

Bölmesini Şerit durum çubuğuna genişletilmiş bölümünde bulunup bulunmadığını belirler.

```
BOOL IsExtended() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu genişletilmiş alan bölmesi ise TRUE. FALSE Aksi takdirde.

##  <a name="ondrawborder"></a>  CMFCRibbonStatusBarPane::OnDrawBorder

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

```
virtual void OnDrawBorder(CDC*);
```

### <a name="parameters"></a>Parametreler

[in] *CDC&#42;*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="onfillbackground"></a>  CMFCRibbonStatusBarPane::OnFillBackground

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

```
virtual COLORREF OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

[in] *pDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onfinishanimation"></a>  CMFCRibbonStatusBarPane::OnFinishAnimation

Bölmesine atanan animasyonu bittiğinde framework bu yöntemi çağırır.

```
virtual void OnFinishAnimation();
```

### <a name="remarks"></a>Açıklamalar

`StopAnimation` Yöntem çağrıları `OnFinishAnimation` animasyonu bittiğinde verileri temizlemek için kullanabileceğiniz yöntemi.

##  <a name="setalmostlargetext"></a>  CMFCRibbonStatusBarPane::SetAlmostLargeText

Kesilme olmadan durum çubuğu bölmesinde görüntülenebilen en uzun metin tanımlayın.

```
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```

### <a name="parameters"></a>Parametreler

*lpszAlmostLargeText*<br/>
[in] Durum çubuğu bölmesi kesmeden gösterilebilir en uzun dizeyi belirtir.

### <a name="remarks"></a>Açıklamalar

Kitaplığı metin boyutunu hesaplar, *lpszAlmostLargeText* belirtir ve bölmesinde buna göre yeniden boyutlandırır. Bunu hala bölmesinde uygun değilse, metin kesilecek.

##  <a name="setanimationlist"></a>  CMFCRibbonStatusBarPane::SetAnimationList

Animasyon için kullanılabilecek bir görüntü listesi durum çubuğu bölmesine ekler.

```
void SetAnimationList(
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```

### <a name="parameters"></a>Parametreler

*hBmpAnimationList*<br/>
[in] Görüntü listesi için bir tanıtıcı belirtir.

*cxAnimation*<br/>
[in] Görüntü listesi çerçevede piksel cinsinden genişliğini belirtir.

*clrTransp*<br/>
[in] Görüntü listesi saydam rengini belirtir.

*uiAnimationListResID*<br/>
[in] Görüntü listesi kaynak Kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Görüntü listesi durum çubuğu bölmesine başarıyla eklenirse TRUE; FALSE Aksi takdirde.

##  <a name="settextalign"></a>  CMFCRibbonStatusBarPane::SetTextAlign

Durum çubuğu bölmesinin etiketin metin hizalamasını ayarlar.

```
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Parametreler

*nAlign*<br/>
[in] Metin hizalamasını belirtir.

### <a name="remarks"></a>Açıklamalar

*nAlign* aşağıdaki değerlerden biri olabilir:

- TA_LEFT: sola hizalama

- TA_CENTER: Ortala

- TA_RIGHT: sağa hizalama

##  <a name="startanimation"></a>  CMFCRibbonStatusBarPane::StartAnimation

Bölmesine atadığınız animasyonu başlatır.

```
void StartAnimation(
    UINT nFrameDelay=500,
    UINT nDuration=-1);
```

### <a name="parameters"></a>Parametreler

*nFrameDelay*<br/>
[in] Animasyon kare hızı, milisaniye cinsinden belirtir.

*nDuration*<br/>
[in] Ne kadar süre, milisaniye cinsinden, animasyonun çalmaya belirtir. Sonsuz bir döngü için-1 değerini kullanın.

### <a name="remarks"></a>Açıklamalar

Çağırmadan önce resim listesi için bir tanıtıcı belirtmelisiniz `StartAnimation` kullanarak `SetAnimationList`.

##  <a name="stopanimation"></a>  CMFCRibbonStatusBarPane::StopAnimation

Durum çubuğu bölmesine atanan animasyon durdurur.

```
void StopAnimation();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonStatusBar Sınıfı](../../mfc/reference/cmfcribbonstatusbar-class.md)
