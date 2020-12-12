---
description: 'Daha fazla bilgi edinin: CMFCRibbonStatusBarPane Class'
title: CMFCRibbonStatusBarPane sınıfı
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
ms.openlocfilehash: 4ddbee5a6c44411ef2ac34bff3e07b47c3d950a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264992"
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane sınıfı

`CMFCRibbonStatusBarPane`Sınıfı, şerit durum çubuğuna ekleyebileceğiniz bir şerit öğesi uygular.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonStatusBarPane : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Bir nesnesi oluşturur ve başlatır `CMFCRibbonStatusBarPane` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBarPane:: GetAlmostLargeText](#getalmostlargetext)|Bölmeden, kesilmeksizin görüntülenebilen en uzun metin dizesini tanımlayan dizeyi döndürür.|
|[CMFCRibbonStatusBarPane:: GetTextAlign](#gettextalign)|Metin hizalaması için geçerli ayarı döndürür.|
|[CMFCRibbonStatusBarPane:: ısanimation](#isanimation)|Animasyonun devam edilip edilmeyeceğini belirler.|
|[CMFCRibbonStatusBarPane:: ısextended](#isextended)|Bölmenin şerit durum çubuğunun genişletilmiş alanında olup olmadığını belirler.|
|[CMFCRibbonStatusBarPane:: OnDrawBorder](#ondrawborder)|( [CMFCRibbonButton:: OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder)geçersiz kılar.)|
|[CMFCRibbonStatusBarPane:: OnFillBackground](#onfillbackground)|( [CMFCRibbonButton:: OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground)geçersiz kılar.)|
|[CMFCRibbonStatusBarPane:: SetAlmostLargeText](#setalmostlargetext)|Bölmeden, kesilmeksizin görüntülenebilen en uzun metin dizesini tanımlar.|
|[CMFCRibbonStatusBarPane:: SetAnimationList](#setanimationlist)|Animasyon için kullanılabilecek bir resim listesini bölmeye atar.|
|[CMFCRibbonStatusBarPane:: SetTextAlign](#settextalign)|Metin hizalamasını ayarlar.|
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Bölmeye atanan animasyonu başlatır.|
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Bölmeye atanan animasyonu sonlandırır. .|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Bölmeye atanan animasyon durdurulduğunda Framework tarafından çağırılır.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfındaki çeşitli yöntemlerin nasıl kullanılacağını göstermektedir `CMFCRibbonStatusBarPane` . Örnek, bir nesnenin nasıl oluşturulduğunu gösterir `CMFCRibbonStatusBarPane` , durum çubuğu bölmesinin etiketinin metin hizalamasını ayarlar, kesme olmadan durum çubuğu bölmesinde görüntülenebilen en uzun metni tanımlar, durum çubuğu bölmesine animasyon için kullanılabilecek bir görüntü listesi ekleyin ve animasyonu başlatın.

[!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbondüğmesi](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonstatusbarpane. h

## <a name="cmfcribbonstatusbarpanecmfcribbonstatusbarpane"></a><a name="cmfcribbonstatusbarpane"></a> CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane

Durum çubuğunda bir bölme nesnesi oluşturun.

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
'ndaki Bölmenin komut KIMLIĞINI belirtir.

*lpszText*<br/>
'ndaki Bölmede görüntülenecek metin dizesini belirtir.

*Bıtik*<br/>
'ndaki TRUE ise durum bölmesi tıklanamaz veya seçili olmaz.

*HICON*<br/>
'ndaki Bölmede görüntülenecek simgeye yönelik bir tanıtıcı belirtir.

*lpszAlmostLargeText*<br/>
'ndaki Bölme tarafından görüntülenebilen en uzun metin dizesini belirtir.

*hBmpAnimationList*<br/>
'ndaki Animasyon için kullanılan bir görüntü listesi için bir tanıtıcı belirtir.

*cxAnimation*<br/>
'ndaki Animasyon için kullanılan görüntü listesindeki simgenin genişliğini piksel cinsinden belirtir.

*clrTrnsp*<br/>
'ndaki Animasyon için kullanılan görüntü listesindeki görüntülerin saydam rengini belirtir.

*Uıanimationlistresd*<br/>
'ndaki Animasyon için kullanılan bir görüntü listesinin kaynak KIMLIĞINI belirtir.

## <a name="cmfcribbonstatusbarpanegetalmostlargetext"></a><a name="getalmostlargetext"></a> CMFCRibbonStatusBarPane:: GetAlmostLargeText

Durum çubuğu bölmesinin görüntüleyeceği en uzun metin dizesini alır.

```
LPCTSTR GetAlmostLargeText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu bölmesinin görüntüleyeceği en uzun metin dizesi.

## <a name="cmfcribbonstatusbarpanegettextalign"></a><a name="gettextalign"></a> CMFCRibbonStatusBarPane:: GetTextAlign

Durum çubuğu bölmesinin etiketinin Metin hizalamasının geçerli ayarını alır.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anki metin hizalaması, aşağıdakilerden biri olabilir:

- TA_LEFT

- TA_CENTER

- TA_RIGHT.

## <a name="cmfcribbonstatusbarpaneisanimation"></a><a name="isanimation"></a> CMFCRibbonStatusBarPane:: ısanimation

Animasyonun devam edilip edilmeyeceğini belirler.

```
BOOL IsAnimation() const;
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon devam ediyorsa doğru; Aksi takdirde FALSE.

## <a name="cmfcribbonstatusbarpaneisextended"></a><a name="isextended"></a> CMFCRibbonStatusBarPane:: ısextended

Bölmenin şerit durum çubuğunun genişletilmiş alanında bulunup bulunmadığını belirleme.

```
BOOL IsExtended() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme, durum çubuğu genişletilmiş alanında ise TRUE. Aksi takdirde FALSE.

## <a name="cmfcribbonstatusbarpaneondrawborder"></a><a name="ondrawborder"></a> CMFCRibbonStatusBarPane:: OnDrawBorder

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual void OnDrawBorder(CDC*);
```

### <a name="parameters"></a>Parametreler

'ndaki *CDC&#42;*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarpaneonfillbackground"></a><a name="onfillbackground"></a> CMFCRibbonStatusBarPane:: OnFillBackground

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual COLORREF OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarpaneonfinishanimation"></a><a name="onfinishanimation"></a> CMFCRibbonStatusBarPane::OnFinishAnimation

Bölmeye atanan animasyon sona erdiğinde Framework bu yöntemi çağırır.

```
virtual void OnFinishAnimation();
```

### <a name="remarks"></a>Açıklamalar

`StopAnimation` yöntemi `OnFinishAnimation` , animasyon sona erdiğinde verileri temizlemek için kullanabileceğiniz yöntemini çağırır.

## <a name="cmfcribbonstatusbarpanesetalmostlargetext"></a><a name="setalmostlargetext"></a> CMFCRibbonStatusBarPane:: SetAlmostLargeText

Durum çubuğu bölmesinde, kesilmeden görüntülenebilen en uzun metni tanımlayın.

```cpp
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```

### <a name="parameters"></a>Parametreler

*lpszAlmostLargeText*<br/>
'ndaki Durum çubuğu bölmesinde, kesilmeden görüntülenebilen en uzun dizeyi belirtir.

### <a name="remarks"></a>Açıklamalar

Kitaplık, *lpszAlmostLargeText* tarafından görüntülenen metnin boyutunu hesaplar ve bölmeyi uygun şekilde yeniden boyutlandırır. Metin, hala bölmeye uymuyorsa kesilir.

## <a name="cmfcribbonstatusbarpanesetanimationlist"></a><a name="setanimationlist"></a> CMFCRibbonStatusBarPane:: SetAnimationList

Animasyon için kullanılabilecek bir görüntü listesi olan durum çubuğu bölmesine ekler.

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
'ndaki Bir görüntü listesi için bir tanıtıcı belirtir.

*cxAnimation*<br/>
'ndaki Görüntü listesindeki çerçevenin genişliğini piksel cinsinden belirtir.

*clrTransp*<br/>
'ndaki Görüntü listesinin saydam rengini belirtir.

*Uıanimationlistresd*<br/>
'ndaki Görüntü listesinin kaynak KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Görüntü listesi, durum çubuğu bölmesine başarıyla eklenmişse doğru; Aksi takdirde FALSE.

## <a name="cmfcribbonstatusbarpanesettextalign"></a><a name="settextalign"></a> CMFCRibbonStatusBarPane:: SetTextAlign

Durum çubuğu bölmesinin etiketinin metin hizalamasını ayarlar.

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Parametreler

*nAlign*<br/>
'ndaki Metin hizalamasını belirtir.

### <a name="remarks"></a>Açıklamalar

*Nalıgn* aşağıdaki değerlerden birine sahip olabilir:

- TA_LEFT: sola hizalama

- TA_CENTER: Ortala

- TA_RIGHT: sağa hizalama

## <a name="cmfcribbonstatusbarpanestartanimation"></a><a name="startanimation"></a> CMFCRibbonStatusBarPane::StartAnimation

Bölmesine atadığınız animasyonu başlatır.

```cpp
void StartAnimation(
    UINT nFrameDelay=500,
    UINT nDuration=-1);
```

### <a name="parameters"></a>Parametreler

*nFrameDelay*<br/>
'ndaki Animasyon kare hızını milisaniye cinsinden belirtir.

*nSüre*<br/>
'ndaki Animasyonun ne kadar süreyle (milisaniye cinsinden) çalınmasını belirtir. Sonsuz döngü için-1 kullanın.

### <a name="remarks"></a>Açıklamalar

Kullanarak çağırmadan önce bir resim listesi için tanıtıcı belirtmeniz gerekir `StartAnimation` `SetAnimationList` .

## <a name="cmfcribbonstatusbarpanestopanimation"></a><a name="stopanimation"></a> CMFCRibbonStatusBarPane::StopAnimation

Durum çubuğu bölmesine atadığınız animasyonu sonlandırır.

```cpp
void StopAnimation();
```

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonStatusBar sınıfı](../../mfc/reference/cmfcribbonstatusbar-class.md)
