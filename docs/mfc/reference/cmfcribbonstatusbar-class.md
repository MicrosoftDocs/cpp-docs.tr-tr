---
title: CMFCRibbonStatusBar Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddDynamicElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddSeparator
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::Create
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::CreateEx
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindByID
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExtendedArea
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetSpace
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsBottomFrame
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsInformationMode
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RecalcLayout
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveAll
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::SetInformation
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::OnDrawInformation
helpviewer_keywords:
- CMFCRibbonStatusBar [MFC], AddDynamicElement
- CMFCRibbonStatusBar [MFC], AddElement
- CMFCRibbonStatusBar [MFC], AddExtendedElement
- CMFCRibbonStatusBar [MFC], AddSeparator
- CMFCRibbonStatusBar [MFC], Create
- CMFCRibbonStatusBar [MFC], CreateEx
- CMFCRibbonStatusBar [MFC], FindByID
- CMFCRibbonStatusBar [MFC], FindElement
- CMFCRibbonStatusBar [MFC], GetCount
- CMFCRibbonStatusBar [MFC], GetElement
- CMFCRibbonStatusBar [MFC], GetExCount
- CMFCRibbonStatusBar [MFC], GetExElement
- CMFCRibbonStatusBar [MFC], GetExtendedArea
- CMFCRibbonStatusBar [MFC], GetSpace
- CMFCRibbonStatusBar [MFC], IsBottomFrame
- CMFCRibbonStatusBar [MFC], IsExtendedElement
- CMFCRibbonStatusBar [MFC], IsInformationMode
- CMFCRibbonStatusBar [MFC], RecalcLayout
- CMFCRibbonStatusBar [MFC], RemoveAll
- CMFCRibbonStatusBar [MFC], RemoveElement
- CMFCRibbonStatusBar [MFC], SetInformation
- CMFCRibbonStatusBar [MFC], OnDrawInformation
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
ms.openlocfilehash: 8d90e01db022c33edd654e83af05e9986799f2b9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754050"
---
# <a name="cmfcribbonstatusbar-class"></a>CMFCRibbonStatusBar Sınıfı

Sınıf, `CMFCRibbonStatusBar` şerit öğelerini görüntüleyebilen bir durum çubuğu denetimi uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonStatusBar : public CMFCRibbonBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBar::AdddynamicElement](#adddynamicelement)|Şerit durum çubuğuna dinamik bir öğe ekler.|
|[CMFCRibbonStatusBar::Addelement](#addelement)|Şerit durum çubuğuna yeni bir şerit öğesi ekler.|
|[CMFCRibbonStatusBar::AddExtendedElement](#addextendedelement)|Şerit durum çubuğunun genişletilmiş alanına bir şerit öğesi ekler.|
|[CMFCRibbonStatusBar::AddSeparator](#addseparator)|Şerit durum çubuğuna bir ayırıcı ekler.|
|[CMFCRibbonStatusBar::Oluştur](#create)|Şerit durum çubuğu oluşturur.|
|[CMFCRibbonStatusBar::CreateEx](#createex)|Genişletilmiş stili olan bir şerit durum çubuğu oluşturur.|
|[CMFCRibbonStatusBar::FindByID](#findbyid)||
|[CMFCRibbonStatusBar::FindElement](#findelement)|Belirtilen komut kimliğine sahip öğeye bir işaretçi döndürür.|
|[CMFCRibbonStatusBar::GetCount](#getcount)|Şerit durum çubuğunun ana alanında bulunan öğe sayısını verir.|
|[CMFCRibbonStatusBar::GetElement](#getelement)|İşaretçiyi belirtilen bir dizinte bulunan öğeye döndürür.|
|[CMFCRibbonStatusBar::GetExCount](#getexcount)|Şerit durum çubuğunun genişletilmiş alanında bulunan öğe sayısını verir.|
|[CMFCRibbonStatusBar::GetExElement](#getexelement)|Şerit durum çubuğunun genişletilmiş alanında belirtilen bir dizinte bulunan öğeyi işaretçisi döndürür.|
|[CMFCRibbonStatusBar::GetExtendedArea](#getextendedarea)||
|[CMFCRibbonStatusBar::GetSpace](#getspace)||
|[CMFCRibbonStatusBar::IsbottomFrame](#isbottomframe)||
|[CMFCRibbonStatusBar::IsExtendedElement](#isextendedelement)||
|[CMFCRibbonStatusBar::IsInformationMode](#isinformationmode)|Şerit durum çubuğu için bilgi modunun etkin olup olmadığını belirler.|
|[CMFCRibbonStatusBar::RecalcLayout](#recalclayout)|[(CMFCRibbonBar geçersiz kılar::RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).)|
|[CMFCRibbonStatusBar::RemoveAll](#removeall)|Şerit durum çubuğundaki tüm öğeleri kaldırır.|
|[CMFCRibbonStatusBar::RemoveElement](#removeelement)|Şerit durum çubuğundan belirli bir komut kimliğine sahip öğeyi kaldırır.|
|[CMFCRibbonStatusBar::SetInformation](#setinformation)|Şerit durum çubuğunun bilgi modunu etkinleştirer veya devre dışı kılabilir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBar::OnDrawInformation](#ondrawinformation)|Bilgi modu etkinleştirildiğinde şerit durum çubuğunda görünen bilgi dizesini görüntüler.|

## <a name="remarks"></a>Açıklamalar

Kullanıcılar, şerit durum çubuğunun yerleşik bağlam menüsünü kullanarak şerit durum çubuğundaki şerit öğelerinin görünürlüğünü değiştirebilir. Öğeleri dinamik olarak ekleyebilir veya kaldırabilirsiniz.

Şerit durum çubuğunun iki alanı vardır: ana alan ve genişletilmiş alan. Genişletilmiş alan şerit durum çubuğunun sağ tarafında görüntülenir ve ana alandan farklı bir renkte görüntülenir.

Genellikle durum çubuğunun ana alanı durum bildirimlerini görüntüler ve genişletilmiş alan görünüm denetimlerini görüntüler. Genişletilmiş alan, kullanıcı şerit durum çubuğunu yeniden boyutlandırdığında mümkün olduğunca uzun süre görünür kalır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCRibbonStatusBar` nasıl kullanılacağını göstermektedir. Örnek, şerit durum çubuğuna yeni bir şerit öğesi nin nasıl ekleyeceğini, şerit durum çubuğunun genişletilmiş alanına şerit öğesi eklemeyi, ayırıcı eklemeyi ve şerit durum çubuğu için normal modu nasıl etkinleştireceklerini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[Cmfcribbonbar](../../mfc/reference/cmfcribbonbar-class.md)

[CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonstatusbar.h

## <a name="cmfcribbonstatusbaradddynamicelement"></a><a name="adddynamicelement"></a>CMFCRibbonStatusBar::AdddynamicElement

Şerit durum çubuğuna dinamik bir öğe ekler.

```cpp
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```

### <a name="parameters"></a>Parametreler

*pElement*<br/>
[içinde] Dinamik bir öğeiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Normal öğelerin aksine, dinamik öğeler özelleştirilebilir değildir ve durum çubuğunun özelleştir menüsü bunları görüntülemez.

## <a name="cmfcribbonstatusbaraddelement"></a><a name="addelement"></a>CMFCRibbonStatusBar::Addelement

Şerit durum çubuğuna yeni bir şerit öğesi ekler.

```cpp
void AddElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Parametreler

*pElement*<br/>
[içinde] Eklenen öğeiçin bir işaretçi.

*lpszEtiket*<br/>
[içinde] Öğenin metin etiketi.

*bIsVisible*<br/>
[içinde] Doğru öğeyi görünür olarak eklemek istiyorsanız, FALSE öğeyi gizli olarak eklemek istiyorsanız.

## <a name="cmfcribbonstatusbaraddextendedelement"></a><a name="addextendedelement"></a>CMFCRibbonStatusBar::AddExtendedElement

Şerit durum çubuğunun genişletilmiş alanına bir şerit öğesi ekler.

```cpp
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Parametreler

*pElement*<br/>
[içinde] Eklenen öğeiçin bir işaretçi.

*lpszEtiket*<br/>
[içinde] Öğenin metin etiketi.

*bIsVisible*<br/>
[içinde] Doğru öğeyi görünür olarak eklemek istiyorsanız, FALSE öğeyi gizli olarak eklemek istiyorsanız.

### <a name="remarks"></a>Açıklamalar

Genişletilmiş alan durum çubuğu denetiminin sağ tarafındadır.

## <a name="cmfcribbonstatusbaraddseparator"></a><a name="addseparator"></a>CMFCRibbonStatusBar::AddSeparator

Şerit durum çubuğuna bir ayırıcı ekler.

```cpp
void AddSeparator();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, [CMFCRibbonStatusBar::AddElement](#addelement)yönteminden sonra bir ayırıcı ekler. son öğeyi ekler.

## <a name="cmfcribbonstatusbarcreate"></a><a name="create"></a>CMFCRibbonStatusBar::Oluştur

Şerit durum çubuğu oluşturur.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
[içinde] Üst pencereiçin bir işaretçi.

*Dwstyle*<br/>
[içinde] Denetim stillerinin mantıksal or kombinasyonu.

*Nıd*<br/>
[içinde] Durum çubuğunun denetim kimliği.

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu başarıyla oluşturulursa DOĞRU, aksi takdirde FALSE.

## <a name="cmfcribbonstatusbarcreateex"></a><a name="createex"></a>CMFCRibbonStatusBar::CreateEx

Genişletilmiş stili olan bir şerit durum çubuğu oluşturur.

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle=0,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Üst pencereiçin bir işaretçi.

*dwCtrlStyle*<br/>
Durum çubuğu nesnesi oluşturmak için ek stilleri n için mantıksal bir OR bileşimi.

*Dwstyle*<br/>
Durum çubuğunun denetim stili.

*Nıd*<br/>
Durum çubuğunun denetim kimliği.

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu başarıyla oluşturulursa DOĞRU, aksi takdirde FALSE.

## <a name="cmfcribbonstatusbarfindbyid"></a><a name="findbyid"></a>CMFCRibbonStatusBar::FindByID

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```

### <a name="parameters"></a>Parametreler

[içinde] *uiCmdID*<br/>
[içinde] *BOOL*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarfindelement"></a><a name="findelement"></a>CMFCRibbonStatusBar::FindElement

Belirtilen komut kimliğine sahip öğeye bir işaretçi döndürür.

```
CMFCRibbonBaseElement* FindElement(UINT uiID);
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[içinde] Öğenin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komut kimliğine sahip öğenin işaretçisi. Böyle bir öğe yoksa NULL.

## <a name="cmfcribbonstatusbargetcount"></a><a name="getcount"></a>CMFCRibbonStatusBar::GetCount

Şerit durum çubuğunun ana alanında bulunan öğe sayısını verir.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit durum çubuğunun ana alanında bulunan öğelerin sayısı.

## <a name="cmfcribbonstatusbargetelement"></a><a name="getelement"></a>CMFCRibbonStatusBar::GetElement

İşaretçiyi belirtilen bir dizinte bulunan öğeye döndürür.

```
CMFCRibbonBaseElement* GetElement(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] Durum çubuğu denetiminin ana alanında bulunan bir öğenin sıfır tabanlı dizinbelirtir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizinde bulunan öğeiçin bir işaretçi. Dizin negatifse veya durum çubuğundaki öğe sayısını aşıyorsa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbargetexcount"></a><a name="getexcount"></a>CMFCRibbonStatusBar::GetExCount

Şerit durum çubuğunun genişletilmiş alanında bulunan öğe sayısını verir.

```
int GetExCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit durum çubuğunun genişletilmiş alanında bulunan öğelerin sayısı.

## <a name="cmfcribbonstatusbargetexelement"></a><a name="getexelement"></a>CMFCRibbonStatusBar::GetExElement

Şerit durum çubuğunun genişletilmiş alanında belirtilen bir dizinte bulunan öğeyi işaretçisi döndürür. Genişletilmiş alan durum çubuğu denetiminin sağ tarafındadır.

```
CMFCRibbonBaseElement* GetExElement(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] Durum çubuğu denetiminin genişletilmiş alanında bulunan bir öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Şerit durum çubuğunun genişletilmiş alanında belirtilen bir dizinte bulunan öğeiçin bir işaretçi. *nIndex* negatifse veya şerit durum çubuğunun genişletilmiş alanındaki öğe sayısını aşıyorsa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbargetextendedarea"></a><a name="getextendedarea"></a>CMFCRibbonStatusBar::GetExtendedArea

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *rekt*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbargetspace"></a><a name="getspace"></a>CMFCRibbonStatusBar::GetSpace

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
int GetSpace() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarisbottomframe"></a><a name="isbottomframe"></a>CMFCRibbonStatusBar::IsbottomFrame

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
BOOL IsBottomFrame() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarisextendedelement"></a><a name="isextendedelement"></a>CMFCRibbonStatusBar::IsExtendedElement

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *pElement*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarisinformationmode"></a><a name="isinformationmode"></a>CMFCRibbonStatusBar::IsInformationMode

Şerit durum çubuğu için bilgi modunun etkin olup olmadığını belirler.

```
BOOL IsInformationMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu bilgi modunda çalışabiliyorsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bilgi modunda, durum çubuğu tüm normal bölmeleri gizler ve bir ileti dizesini görüntüler.

## <a name="cmfcribbonstatusbarondrawinformation"></a><a name="ondrawinformation"></a>CMFCRibbonStatusBar::OnDrawInformation

Bilgi modu etkinleştirildiğinde şerit durum çubuğunda görünen dizeyi görüntüler.

```
virtual void OnDrawInformation(
    CDC* pDC,
    CString& strInfo,
    CRect rectInfo);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*strInfo*<br/>
[içinde] Bilgi dizesi.

*rectInfo*<br/>
[içinde] Sınırlayıcı dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Durum çubuğundaki bilgi dizesinin görünümünü özelleştirmek istiyorsanız, türetilmiş bir sınıfta bu yöntemi geçersiz kılın. Durum çubuğunu bilgi moduna koymak için [CMFCRibbonStatusBar::SetInformation](#setinformation) yöntemini kullanın. Bu modda, durum çubuğu tüm bölmeleri gizler ve *strInfo*tarafından belirtilen bilgi dizesini görüntüler.

## <a name="cmfcribbonstatusbarrecalclayout"></a><a name="recalclayout"></a>CMFCRibbonStatusBar::RecalcLayout

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarremoveall"></a><a name="removeall"></a>CMFCRibbonStatusBar::RemoveAll

Şerit durum çubuğundaki tüm öğeleri kaldırır.

```cpp
void RemoveAll();
```

## <a name="cmfcribbonstatusbarremoveelement"></a><a name="removeelement"></a>CMFCRibbonStatusBar::RemoveElement

Şerit durum çubuğundan belirli bir komut kimliğine sahip öğeyi kaldırır.

```
BOOL RemoveElement(UINT uiID);
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[içinde] Durum çubuğundan kaldırılacak öğenin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen *uiID'ye* sahip bir öğe kaldırılırsa DOĞRU. YANLIŞ aksi takdirde.

## <a name="cmfcribbonstatusbarsetinformation"></a><a name="setinformation"></a>CMFCRibbonStatusBar::SetInformation

Şerit durum çubuğunun bilgi modunu etkinleştirer veya devre dışı kılabilir.

```cpp
void SetInformation(LPCTSTR lpszInfo);
```

### <a name="parameters"></a>Parametreler

*lpszInfo*<br/>
[içinde] Bilgi dizesi.

### <a name="remarks"></a>Açıklamalar

Durum çubuğunu bilgi moduna koymak için bu yöntemi kullanın. Bu modda, durum çubuğu tüm bölmeleri gizler ve *lpszInfo*tarafından belirtilen bilgi dizesini görüntüler.

LPSZInfo NULL olduğunda, durum çubuğu normal moda döner.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)<br/>
[CMFCRibbonBaseElement Sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
