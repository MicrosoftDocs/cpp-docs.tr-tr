---
title: CMFCRibbonSeparator sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
ms.openlocfilehash: 05ac8b26cb6b6e7d8e622ecbaac1d4a81bfd35e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565938"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator sınıfı

Şerit ayırıcı uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonSeparator : public CMFCRibbonBaseElement
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|Oluşturur bir `CMFCRibbonSeparator` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|Ekler için ayırıcı **komutları** listesinde **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|
|`CMFCRibbonSeparator::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|`CMFCRibbonSeparator::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|Ayırıcı'nın üyesi başka bir nesneden değişkenleri ayarlayan bir kopyalama yöntemi.|
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|Ayırıcı boyutunu döndürür.|
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|Bu ayırıcı olup olmadığını gösterir.|
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|Bu sekme durağı olup olmadığını gösterir.|
|[CMFCRibbonSeparator::OnDraw](#ondraw)|Şerit veya hızlı erişim araç çubuğu ayırıcı çizmek için sistem tarafından çağrılır.|
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|Ayırıcı çizilecek sistem tarafından çağrılan **komutları** listesi.|

## <a name="remarks"></a>Açıklamalar

Bir Şerit ayırıcı mantıksal olarak ayırır öğeleri Şerit, dikey veya yatay bir çizgi var. Ayırıcı, Şerit denetimi, ana uygulama menüsünde, Şerit durum çubuğuna ve hızlı erişim araç çubuğu üzerinde kurulabilir.

Ayırıcı, uygulamanızda kullanmak için yeni bir nesne oluşturmak ve burada gösterildiği gibi ana uygulama menüsüne ekleyin:

```
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```
Çağrı [CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) ayırıcılar için Şerit Panel eklemek için. Ayırıcılar ayrılan ve tarafından dahili olarak eklenen `AddSeparator` yöntemi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxbaseribbonelement.h

##  <a name="addtolistbox"></a>  CMFCRibbonSeparator::AddToListBox

Ekler için ayırıcı **komutları** listesinde **Özelleştir** iletişim kutusu.

```
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,
    BOOL bDeep);
```

### <a name="parameters"></a>Parametreler

*pWndListBox*<br/>
[in] Bir işaretçi **komutları** liste ayırıcı burada eklenir.

*bDeep*<br/>
[in] Yoksayıldı.

### <a name="return-value"></a>Dönüş Değeri

Sıfır tabanlı dizin dizesi tarafından belirtilen liste kutusunda *pWndListBox*.

##  <a name="cmfcribbonseparator"></a>  CMFCRibbonSeparator::CMFCRibbonSeparator

Oluşturur bir `CMFCRibbonSeparator` nesne.

```
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```

### <a name="parameters"></a>Parametreler

*bIsHoriz*<br/>
[in] TRUE ise ayırıcı yatay; FALSE ise, ayırıcı dikeydir.

### <a name="remarks"></a>Açıklamalar

Yatay ayırıcısı uygulama menülerde kullanılır. Dikey ayırıcısı, araç çubuklarını kullanılır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCRibbonSeparator` sınıfı.

[!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]

##  <a name="copyfrom"></a>  CMFCRibbonSeparator::CopyFrom

Ayırıcı'nın üyesi başka bir nesneden değişkenleri ayarlayan bir kopyalama yöntemi.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[in] Kopyalanacak kaynak Şerit öğesi.

##  <a name="getregularsize"></a>  CMFCRibbonSeparator::GetRegularSize

Ayırıcı boyutunu döndürür.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz içeriği için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir cihaz bağlamı ayırıcı boyutu.

##  <a name="isseparator"></a>  CMFCRibbonSeparator::IsSeparator

Bu ayırıcı olup olmadığını gösterir.

```
virtual BOOL IsSeparator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu sınıf için her zaman TRUE.

##  <a name="istabstop"></a>  CMFCRibbonSeparator::IsTabStop

Bu sekme durağı olup olmadığını gösterir.

```
virtual BOOL IsTabStop() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu sınıf için her zaman FALSE.

### <a name="remarks"></a>Açıklamalar

Bir Şerit ayırıcı sekme durağı değil.

##  <a name="ondraw"></a>  CMFCRibbonSeparator::OnDraw

Şerit veya hızlı erişim araç çubuğu ayırıcı çizmek için sistem tarafından çağrılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

##  <a name="ondrawonlist"></a>  CMFCRibbonSeparator::OnDrawOnList

Ayırıcı çizilecek sistem tarafından çağrılan **komutları** listesi.

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pDC*|[in] Bir cihaz bağlamı için bir işaretçi.|
|*strText*|[in] Listede görüntülenecek metin.|
|*nTextOffset*|[in] Metin ile sol tarafındaki dikdörtgen arasındaki boşluk.|
|*Rect*|[in] Sınırlayıcı dikdörtgeni belirtir.|
|*bIsSelected*|[in] Yoksayıldı.|
|*bHighlighted*|[in] Yoksayıldı.|

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
