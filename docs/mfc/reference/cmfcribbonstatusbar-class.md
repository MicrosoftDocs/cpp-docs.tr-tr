---
description: 'Daha fazla bilgi edinin: CMFCRibbonStatusBar sınıfı'
title: CMFCRibbonStatusBar sınıfı
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
ms.openlocfilehash: 01436d535b410fd4a6c70f52760908e3547b7af8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265005"
---
# <a name="cmfcribbonstatusbar-class"></a>CMFCRibbonStatusBar sınıfı

`CMFCRibbonStatusBar`Sınıfı, Şerit öğelerini görüntüleyebilen bir durum çubuğu denetimi uygular.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonStatusBar : public CMFCRibbonBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBar:: AddDynamicElement](#adddynamicelement)|Şerit durum çubuğuna dinamik bir öğe ekler.|
|[CMFCRibbonStatusBar:: AddElement](#addelement)|Şerit durum çubuğuna yeni bir şerit öğesi ekler.|
|[CMFCRibbonStatusBar:: AddExtendedElement](#addextendedelement)|Şerit durum çubuğunun genişletilmiş alanına bir şerit öğesi ekler.|
|[CMFCRibbonStatusBar:: AddSeparator](#addseparator)|Şerit durum çubuğuna bir ayırıcı ekler.|
|[CMFCRibbonStatusBar:: Create](#create)|Bir şerit durum çubuğu oluşturur.|
|[CMFCRibbonStatusBar:: CreateEx](#createex)|Genişletilmiş stille bir şerit durum çubuğu oluşturur.|
|[CMFCRibbonStatusBar:: Findbyıd](#findbyid)||
|[CMFCRibbonStatusBar:: FindElement](#findelement)|Belirtilen komut KIMLIĞINE sahip öğe için bir işaretçi döndürür.|
|[CMFCRibbonStatusBar:: GetCount](#getcount)|Şerit durum çubuğunun ana alanında bulunan öğe sayısını döndürür.|
|[CMFCRibbonStatusBar:: GetElement](#getelement)|Belirtilen dizinde bulunan öğeye bir işaretçi döndürür.|
|[CMFCRibbonStatusBar:: GetExCount](#getexcount)|Şerit durum çubuğunun genişletilmiş alanında bulunan öğe sayısını döndürür.|
|[CMFCRibbonStatusBar:: GetExElement](#getexelement)|Şerit durum çubuğunun genişletilmiş alanındaki belirtilen dizinde bulunan öğeye yönelik bir işaretçi döndürür.|
|[CMFCRibbonStatusBar:: GetBu Dedarea](#getextendedarea)||
|[CMFCRibbonStatusBar:: GetSpace](#getspace)||
|[CMFCRibbonStatusBar:: ıbottomframe](#isbottomframe)||
|[CMFCRibbonStatusBar:: IsExtendedElement](#isextendedelement)||
|[CMFCRibbonStatusBar:: ısınformationmode](#isinformationmode)|Şerit durum çubuğu için bilgi modunun etkin olup olmadığını belirler.|
|[CMFCRibbonStatusBar:: RecalcLayout](#recalclayout)|( [CMFCRibbonBar:: RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).) öğesini geçersiz kılar|
|[CMFCRibbonStatusBar:: RemoveAll](#removeall)|Şerit durum çubuğundan tüm öğeleri kaldırır.|
|[CMFCRibbonStatusBar:: RemoveElement](#removeelement)|Belirtilen komut KIMLIĞINE sahip öğeyi şerit durum çubuğundan kaldırır.|
|[CMFCRibbonStatusBar:: SetInformation](#setinformation)|Şerit durum çubuğu için bilgi modunu etkinleştirilir veya devre dışı bırakır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonStatusBar:: OnDrawInformation](#ondrawinformation)|Bilgi modu etkinleştirildiğinde şerit durum çubuğunda görüntülenen bilgi dizesini görüntüler.|

## <a name="remarks"></a>Açıklamalar

Kullanıcılar, şerit durum çubuğu için yerleşik bağlam menüsünü kullanarak bir şerit durum çubuğundaki şerit öğelerinin görünürlüğünü değiştirebilir. Dinamik olarak öğe ekleyebilir veya kaldırabilirsiniz.

Bir şerit durum çubuğunun iki alanı vardır: ana alan ve genişletilmiş alan. Genişletilmiş alan, şerit durum çubuğunun sağ tarafında görüntülenir ve ana alandan farklı bir renkle gösterilir.

Genellikle, durum çubuğunun ana alanı durum bildirimlerini görüntüler ve genişletilmiş alan görünüm denetimlerini görüntüler. Genişletilmiş alan, Kullanıcı şerit durum çubuğunu yeniden boyutlandırdığında mümkün olduğunca görünür kalır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCRibbonStatusBar` . Örnek, şerit durum çubuğuna yeni bir şerit öğesinin nasıl ekleneceğini gösterir, şerit durum çubuğunun genişletilmiş alanına bir şerit öğesi ekler, bir ayırıcı ekler ve şerit durum çubuğu için normal modu etkinleştirir.

[!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[Cmfcribbonçubuğu](../../mfc/reference/cmfcribbonbar-class.md)

[CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonstatusbar. h

## <a name="cmfcribbonstatusbaradddynamicelement"></a><a name="adddynamicelement"></a> CMFCRibbonStatusBar:: AddDynamicElement

Şerit durum çubuğuna dinamik bir öğe ekler.

```cpp
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```

### <a name="parameters"></a>Parametreler

*pElement*<br/>
'ndaki Dinamik öğe işaretçisi.

### <a name="remarks"></a>Açıklamalar

Normal öğelerin aksine, dinamik öğeler özelleştirilemez ve durum çubuğunun Özelleştir menüsü bunları görüntülemez.

## <a name="cmfcribbonstatusbaraddelement"></a><a name="addelement"></a> CMFCRibbonStatusBar:: AddElement

Şerit durum çubuğuna yeni bir şerit öğesi ekler.

```cpp
void AddElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Parametreler

*pElement*<br/>
'ndaki Eklenen öğeye yönelik bir işaretçi.

*lpszLabel*<br/>
'ndaki Öğenin metin etiketi.

*bIsVisible*<br/>
'ndaki Öğeyi görünür olarak eklemek istiyorsanız TRUE, öğeyi gizli olarak eklemek istiyorsanız FALSE.

## <a name="cmfcribbonstatusbaraddextendedelement"></a><a name="addextendedelement"></a> CMFCRibbonStatusBar:: AddExtendedElement

Şerit durum çubuğunun genişletilmiş alanına bir şerit öğesi ekler.

```cpp
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Parametreler

*pElement*<br/>
'ndaki Eklenen öğeye yönelik bir işaretçi.

*lpszLabel*<br/>
'ndaki Öğenin metin etiketi.

*bIsVisible*<br/>
'ndaki Öğeyi görünür olarak eklemek istiyorsanız TRUE, öğeyi gizli olarak eklemek istiyorsanız FALSE.

### <a name="remarks"></a>Açıklamalar

Genişletilmiş alan, durum çubuğu denetiminin sağ tarafındadır.

## <a name="cmfcribbonstatusbaraddseparator"></a><a name="addseparator"></a> CMFCRibbonStatusBar:: AddSeparator

Şerit durum çubuğuna bir ayırıcı ekler.

```cpp
void AddSeparator();
```

### <a name="remarks"></a>Açıklamalar

Framework, [CMFCRibbonStatusBar:: AddElement](#addelement)yönteminden sonra bir ayırıcı ekler. son öğeyi ekler.

## <a name="cmfcribbonstatusbarcreate"></a><a name="create"></a> CMFCRibbonStatusBar:: Create

Bir şerit durum çubuğu oluşturur.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
'ndaki Ana pencereye yönelik bir işaretçi.

*dwStyle*<br/>
'ndaki Denetim stillerinin mantıksal veya birleşimi.

*NID*<br/>
'ndaki Durum çubuğunun denetim KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu başarıyla oluşturulursa TRUE, aksi takdirde FALSE.

## <a name="cmfcribbonstatusbarcreateex"></a><a name="createex"></a> CMFCRibbonStatusBar:: CreateEx

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
Ana pencereye yönelik bir işaretçi.

*dwCtrlStyle*<br/>
Durum çubuğu nesnesini oluşturmak için ek stillerin mantıksal veya birleşimi.

*dwStyle*<br/>
Durum çubuğunun denetim stili.

*NID*<br/>
Durum çubuğunun denetim KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu başarıyla oluşturulursa TRUE, aksi takdirde FALSE.

## <a name="cmfcribbonstatusbarfindbyid"></a><a name="findbyid"></a> CMFCRibbonStatusBar:: Findbyıd

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```

### <a name="parameters"></a>Parametreler

'ndaki *Uıımıdıd*<br/>
'ndaki *Bool*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarfindelement"></a><a name="findelement"></a> CMFCRibbonStatusBar:: FindElement

Belirtilen komut KIMLIĞINE sahip öğe için bir işaretçi döndürür.

```
CMFCRibbonBaseElement* FindElement(UINT uiID);
```

### <a name="parameters"></a>Parametreler

*Uııd*<br/>
'ndaki Öğenin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komut KIMLIĞINE sahip öğe için bir işaretçi. Böyle bir öğe yoksa NULL.

## <a name="cmfcribbonstatusbargetcount"></a><a name="getcount"></a> CMFCRibbonStatusBar:: GetCount

Şerit durum çubuğunun ana alanında bulunan öğe sayısını döndürür.

```
int GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit durum çubuğunun ana alanında bulunan öğelerin sayısı.

## <a name="cmfcribbonstatusbargetelement"></a><a name="getelement"></a> CMFCRibbonStatusBar:: GetElement

Belirtilen dizinde bulunan öğeye bir işaretçi döndürür.

```
CMFCRibbonBaseElement* GetElement(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki Durum çubuğu denetiminin ana alanında bulunan bir öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizinde bulunan öğeye yönelik bir işaretçi. Dizin negatifse veya durum çubuğundaki öğe sayısını aşarsa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbargetexcount"></a><a name="getexcount"></a> CMFCRibbonStatusBar:: GetExCount

Şerit durum çubuğunun genişletilmiş alanında bulunan öğe sayısını döndürür.

```
int GetExCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şerit durum çubuğunun genişletilmiş alanında bulunan öğe sayısı.

## <a name="cmfcribbonstatusbargetexelement"></a><a name="getexelement"></a> CMFCRibbonStatusBar:: GetExElement

Şerit durum çubuğunun genişletilmiş alanındaki belirtilen dizinde bulunan öğeye yönelik bir işaretçi döndürür. Genişletilmiş alan, durum çubuğu denetiminin sağ tarafındadır.

```
CMFCRibbonBaseElement* GetExElement(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki Durum çubuğu denetiminin genişletilmiş alanında bulunan bir öğenin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Şerit durum çubuğunun genişletilmiş alanındaki belirtilen dizinde bulunan öğeye yönelik bir işaretçi. *NIndex* negatifse veya şerit durum çubuğunun genişletilmiş alanındaki öğelerin SAYıSıNı aşarsa null.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbargetextendedarea"></a><a name="getextendedarea"></a> CMFCRibbonStatusBar:: GetBu Dedarea

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *Rect*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbargetspace"></a><a name="getspace"></a> CMFCRibbonStatusBar:: GetSpace

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
int GetSpace() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarisbottomframe"></a><a name="isbottomframe"></a> CMFCRibbonStatusBar:: ıbottomframe

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
BOOL IsBottomFrame() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarisextendedelement"></a><a name="isextendedelement"></a> CMFCRibbonStatusBar:: IsExtendedElement

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *pElement*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarisinformationmode"></a><a name="isinformationmode"></a> CMFCRibbonStatusBar:: ısınformationmode

Şerit durum çubuğu için bilgi modunun etkin olup olmadığını belirler.

```
BOOL IsInformationMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Durum çubuğu bilgi modunda çalışabiliyorsa, doğru. Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bilgi modunda, durum çubuğu tüm normal bölmeleri gizler ve bir ileti dizesi görüntüler.

## <a name="cmfcribbonstatusbarondrawinformation"></a><a name="ondrawinformation"></a> CMFCRibbonStatusBar:: OnDrawInformation

Bilgi modu etkinleştirildiğinde şerit durum çubuğunda görüntülenen dizeyi görüntüler.

```
virtual void OnDrawInformation(
    CDC* pDC,
    CString& strInfo,
    CRect rectInfo);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*strInfo*<br/>
'ndaki Bilgi dizesi.

*Rectınfo*<br/>
'ndaki Sınırlayıcı dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Durum çubuğundaki bilgi dizesinin görünümünü özelleştirmek istiyorsanız, türetilmiş bir sınıfta bu yöntemi geçersiz kılın. Durum çubuğunu bilgi moduna almak için [CMFCRibbonStatusBar:: SetInformation](#setinformation) metodunu kullanın. Bu modda, durum çubuğu tüm bölmeleri gizler ve *strInfo* tarafından belirtilen bilgi dizesini görüntüler.

## <a name="cmfcribbonstatusbarrecalclayout"></a><a name="recalclayout"></a> CMFCRibbonStatusBar:: RecalcLayout

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonstatusbarremoveall"></a><a name="removeall"></a> CMFCRibbonStatusBar:: RemoveAll

Şerit durum çubuğundan tüm öğeleri kaldırır.

```cpp
void RemoveAll();
```

## <a name="cmfcribbonstatusbarremoveelement"></a><a name="removeelement"></a> CMFCRibbonStatusBar:: RemoveElement

Belirtilen komut KIMLIĞINE sahip öğeyi şerit durum çubuğundan kaldırır.

```
BOOL RemoveElement(UINT uiID);
```

### <a name="parameters"></a>Parametreler

*Uııd*<br/>
'ndaki Durum çubuğundan kaldırılacak öğenin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen *Uııd* 'ye sahip bir öğe kaldırılırsa true. Aksi takdirde FALSE.

## <a name="cmfcribbonstatusbarsetinformation"></a><a name="setinformation"></a> CMFCRibbonStatusBar:: SetInformation

Şerit durum çubuğu için bilgi modunu etkinleştirilir veya devre dışı bırakır.

```cpp
void SetInformation(LPCTSTR lpszInfo);
```

### <a name="parameters"></a>Parametreler

*lpszInfo*<br/>
'ndaki Bilgi dizesi.

### <a name="remarks"></a>Açıklamalar

Durum çubuğunu bilgi moduna almak için bu yöntemi kullanın. Bu modda, durum çubuğu tüm bölmeleri gizler ve *LpszInfo* tarafından belirtilen bilgi dizesini görüntüler.

LpszInfo NULL olduğunda, durum çubuğu normal moda geri döner.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)<br/>
[CMFCRibbonBaseElement sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
