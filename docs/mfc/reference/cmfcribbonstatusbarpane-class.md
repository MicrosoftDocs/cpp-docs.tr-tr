---
title: CMFCRibbonStatusBarPane Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: bb4e09eabab17061812ed22b2739d06accd57fee
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753508"
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane Sınıfı

Sınıf, `CMFCRibbonStatusBarPane` şerit durum çubuğuna ekleyebileceğiniz bir şerit öğesi uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonStatusBarPane : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Bir `CMFCRibbonStatusBarPane` nesne yi inşa eder ve başharfe ait hale raz.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Bölmede kesilmeden görüntülenebilen en uzun metin dizesini tanımlayan dizeyi döndürür.|
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|Metin hizalamasının geçerli ayarını verir.|
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|Animasyonun devam edip etmeyeceğini belirler.|
|[CMFCRibbonStatusBarPane::Genişletilmiş](#isextended)|Bölmenin şerit durum çubuğunun genişletilmiş alanında bulunup bulunmadığını belirler.|
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|[(CMFCRibbonButton geçersiz kılar::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|[(CMFCRibbonButton geçersiz kılar::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Bölmede kesilmeden görüntülenebilen en uzun metin dizesini tanımlar.|
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Bölmeye animasyon için kullanılabilecek bir resim listesi atar.|
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Metin hizalanmasını ayarlar.|
|[CMFCRibbonStatusBarPane::Başlangıç Animasyonu](#startanimation)|Bölmeye atanan animasyonu başlatır.|
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Bölmeye atanan animasyonu durdurur. .|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Bölmeye atanan animasyon durduğunda çerçeve tarafından çağrılır.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıftaki çeşitli yöntemlerin `CMFCRibbonStatusBarPane` nasıl kullanılacağını göstermektedir. Örnek, bir `CMFCRibbonStatusBarPane` nesnenin nasıl oluşturulabildiğini, durum çubuğu bölmesinin etiketinin metin hizasını nasıl ayarladığını, durum çubuğu bölmesinde kesilmeden görüntülenebilecek en uzun metni tanımlamayı, durum çubuğuna animasyon için kullanılabilecek bir resim listesi eklemeyi ve animasyonu başlatmayı gösterir.

[!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonstatusbarpane.h

## <a name="cmfcribbonstatusbarpanecmfcribbonstatusbarpane"></a><a name="cmfcribbonstatusbarpane"></a>CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane

Durum çubuğunda bir bölme nesnesi oluştur.

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
[içinde] Bölmenin komut kimliğini belirtir.

*lpszMetin*<br/>
[içinde] Bölmede görüntülenecek metin dizesini belirtir.

*bIsStatic*<br/>
[içinde] TRUE ise, durum bölmesi tıklatılarak vurgulanamaz veya seçilemez.

*Hıcon*<br/>
[içinde] Bölmede görüntülenecek bir simgeiçin bir tutamaç belirtir.

*lpszAlmostLargeText*<br/>
[içinde] Bölme tarafından görüntülenebilen en uzun metin dizesini belirtir.

*hBmpAnimationList*<br/>
[içinde] Animasyon için kullanılan bir görüntü listesine bir tanıtıcı belirtir.

*cxAnimasyon*<br/>
[içinde] Animasyon için kullanılan resim listesindeki simgenin piksel olarak genişliğini belirtir.

*clrTrnsp*<br/>
[içinde] Animasyon için kullanılan görüntü listesindeki görüntülerin saydam rengini belirtir.

*uiAnimationListResID*<br/>
[içinde] Animasyon için kullanılan bir resim listesinin kaynak kimliğini belirtir.

## <a name="cmfcribbonstatusbarpanegetalmostlargetext"></a><a name="getalmostlargetext"></a>CMFCRibbonStatusBarPane::GetAlmostLargeText

Durum çubuğu bölmesinin görüntülebildiği en uzun metin dizesini alır.

```
LPCTSTR GetAlmostLargeText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu bölmesinin görüntülebildiği en uzun metin dizesi.

## <a name="cmfcribbonstatusbarpanegettextalign"></a><a name="gettextalign"></a>CMFCRibbonStatusBarPane::GetTextAlign

Durum çubuğu bölmesinin etiketinin metin hizalamasının geçerli ayarını alır.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdakilerden biri olabilecek geçerli metin hizalaması:

- TA_LEFT

- TA_CENTER

- TA_RIGHT.

## <a name="cmfcribbonstatusbarpaneisanimation"></a><a name="isanimation"></a>CMFCRibbonStatusBarPane::IsAnimation

Animasyonun devam edip etmeyeceğini belirler.

```
BOOL IsAnimation() const;
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon devam ediyorsa DOĞRU; YANLIŞ aksi takdirde.

## <a name="cmfcribbonstatusbarpaneisextended"></a><a name="isextended"></a>CMFCRibbonStatusBarPane::Genişletilmiş

Bölmenin şerit durum çubuğunun genişletilmiş alanında bulunup bulunmadığını belirleyin.

```
BOOL IsExtended() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme durum çubuğu genişletilmiş alanda ise DOĞRU. YANLIŞ aksi takdirde.

## <a name="cmfcribbonstatusbarpaneondrawborder"></a><a name="ondrawborder"></a>CMFCRibbonStatusBarPane::OnDrawBorder

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual void OnDrawBorder(CDC*);
```

### <a name="parameters"></a>Parametreler

[içinde] *CDC&#42;*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarpaneonfillbackground"></a><a name="onfillbackground"></a>CMFCRibbonStatusBarPane::OnFillBackground

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual COLORREF OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarpaneonfinishanimation"></a><a name="onfinishanimation"></a>CMFCRibbonStatusBarPane::OnFinishAnimation

Çerçeve, bölmeye atanan animasyon sona erdiğinde bu yöntemi çağırır.

```
virtual void OnFinishAnimation();
```

### <a name="remarks"></a>Açıklamalar

`StopAnimation`yöntem, `OnFinishAnimation` animasyon sona erdiğinde verileri temizlemek için kullanabileceğiniz yöntemi çağırır.

## <a name="cmfcribbonstatusbarpanesetalmostlargetext"></a><a name="setalmostlargetext"></a>CMFCRibbonStatusBarPane::SetAlmostLargeText

Durum çubuğu bölmesinde kesilmeden görüntülenebilen en uzun metni tanımlayın.

```cpp
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```

### <a name="parameters"></a>Parametreler

*lpszAlmostLargeText*<br/>
[içinde] Durum çubuğu bölmesinde kesilmeden görüntülenebilen en uzun dizeyi belirtir.

### <a name="remarks"></a>Açıklamalar

*Kitaplık, lpszAlmostLargeText'in* belirttiği metnin boyutunu hesaplar ve bölmeyi buna göre yeniden boyutlandırır. Bölmeye hala sığmazsa metin kesilir.

## <a name="cmfcribbonstatusbarpanesetanimationlist"></a><a name="setanimationlist"></a>CMFCRibbonStatusBarPane::SetAnimationList

Durum çubuğuna animasyon için kullanılabilecek bir resim listesi eklenir.

```cpp
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
[içinde] Bir görüntü listesine bir tanıtıcı belirtir.

*cxAnimasyon*<br/>
[içinde] Görüntü listesindeki çerçevenin genişliğini piksel olarak belirtir.

*clrTransp*<br/>
[içinde] Görüntü listesinin saydam rengini belirtir.

*uiAnimationListResID*<br/>
[içinde] Resim listesinin kaynak kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Görüntü listesi durum çubuğu bölmesine başarıyla iliştirilirse DOĞRU; YANLIŞ aksi takdirde.

## <a name="cmfcribbonstatusbarpanesettextalign"></a><a name="settextalign"></a>CMFCRibbonStatusBarPane::SetTextAlign

Durum çubuğu bölmesinin etiketinin metin hizasını ayarlar.

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Parametreler

*nAlign*<br/>
[içinde] Metin hizalamasını belirtir.

### <a name="remarks"></a>Açıklamalar

*nAlign* aşağıdaki değerlerden birine sahip olabilir:

- TA_LEFT: sol hizalama

- TA_CENTER: merkez hizalama

- TA_RIGHT: doğru hizalama

## <a name="cmfcribbonstatusbarpanestartanimation"></a><a name="startanimation"></a>CMFCRibbonStatusBarPane::Başlangıç Animasyonu

Bölmeye atadığınız animasyonu başlatır.

```cpp
void StartAnimation(
    UINT nFrameDelay=500,
    UINT nDuration=-1);
```

### <a name="parameters"></a>Parametreler

*nFrameDelay*<br/>
[içinde] Animasyon kare hızını milisaniye cinsinden belirtir.

*nSüre*<br/>
[içinde] Animasyonun milisaniye cinsinden ne kadar süreyle oynatılabildiğini belirtir. Sonsuz bir döngü için -1'i kullanın.

### <a name="remarks"></a>Açıklamalar

'yi kullanarak `StartAnimation` `SetAnimationList`aramadan önce bir resim listesine bir tanıtıcı belirtmeniz gerekir.

## <a name="cmfcribbonstatusbarpanestopanimation"></a><a name="stopanimation"></a>CMFCRibbonStatusBarPane::StopAnimation

Durum çubuğu bölmesine atadığınız animasyonu durdurur.

```cpp
void StopAnimation();
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonStatusBar Sınıfı](../../mfc/reference/cmfcribbonstatusbar-class.md)
