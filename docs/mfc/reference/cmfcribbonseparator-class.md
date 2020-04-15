---
title: CMFCRibbonSeparator Sınıfı
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
ms.openlocfilehash: 41a958c78719f6aedf1cc02f8e3ff5a2dbbf0e1b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368844"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator Sınıfı

Şerit ayırıcısını uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonSeparator : public CMFCRibbonBaseElement
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|Bir `CMFCRibbonSeparator` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|**Özelleştir** iletişim kutusunda **ki Komutlar** listesine ayırıcı ekler. [(CMFCRibbonBaseElement geçersiz kılar::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|
|`CMFCRibbonSeparator::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|`CMFCRibbonSeparator::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|Ayırıcının üye değişkenlerini başka bir nesneden ayarlayan bir kopyalama yöntemi.|
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|Ayırıcı boyutunu döndürür.|
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|Bunun bir ayırıcı olup olmadığını gösterir.|
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|Bunun bir sekme durağı olup olmadığını gösterir.|
|[CMFCRibbonSeparator::OnDraw](#ondraw)|Şerit veya Hızlı Erişim Araç Çubuğu üzerinde ayırıcı çizmek için sistem tarafından çağrılır.|
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|**Komutlar** listesinde ayırıcı çizmek için sistem tarafından çağrıldı.|

## <a name="remarks"></a>Açıklamalar

Şerit ayırıcı, şerit öğelerini mantıksal olarak ayıran dikey veya yatay bir çizgidir. Şerit denetimine, ana uygulama menüsüne, şerit durum çubuğuna ve Hızlı Erişim Araç Çubuğu'na bir ayırıcı çizilebilir.

Uygulamanızda bir ayırıcı kullanmak için yeni nesne oluşturmak ve burada gösterildiği gibi ana uygulama menüsüne ekleyin:

```
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```

[CmFCRibbonPanel'i arayın:Şerit](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) panellerine ayırıcılar eklemek için AddSeparator'u arayın. `AddSeparator` Ayırıcılar, yöntemle dahili olarak ayrılır ve eklenir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxbaseribbonelement.h

## <a name="cmfcribbonseparatoraddtolistbox"></a><a name="addtolistbox"></a>CMFCRibbonSeparator::AddToListBox

**Özelleştir** iletişim kutusunda **ki Komutlar** listesine ayırıcı ekler.

```
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,
    BOOL bDeep);
```

### <a name="parameters"></a>Parametreler

*pWndListBox*<br/>
[içinde] Ayırıcının eklendiği **Komutlar** listesine işaretçi.

*bDerin*<br/>
[içinde] Göz ardı.

### <a name="return-value"></a>Dönüş Değeri

*pWndListBox*tarafından belirtilen liste kutusundadize sıfır tabanlı dizin.

## <a name="cmfcribbonseparatorcmfcribbonseparator"></a><a name="cmfcribbonseparator"></a>CMFCRibbonSeparator::CMFCRibbonSeparator

Bir `CMFCRibbonSeparator` nesne inşa eder.

```
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```

### <a name="parameters"></a>Parametreler

*bIsHoriz*<br/>
[içinde] DOĞRUysa, ayırıcı yataydır; FALSE ise, ayırıcı dikeydir.

### <a name="remarks"></a>Açıklamalar

Uygulama menülerinde yatay ayırıcılar kullanılır. Araç çubuklarında dikey ayırıcılar kullanılır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCRibbonSeparator` nasıl inşa edilebildiğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]

## <a name="cmfcribbonseparatorcopyfrom"></a><a name="copyfrom"></a>CMFCRibbonSeparator::CopyFrom

Ayırıcının üye değişkenlerini başka bir nesneden ayarlayan bir kopyalama yöntemi.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parametreler

*Src*<br/>
[içinde] Kopyalanması gereken kaynak şerit öğesi.

## <a name="cmfcribbonseparatorgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonSeparator::GetRegularSize

Ayırıcı boyutunu döndürür.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt içeriğiiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Verilen aygıt bağlamında ayırıcının boyutu.

## <a name="cmfcribbonseparatorisseparator"></a><a name="isseparator"></a>CMFCRibbonSeparator::IsSeparator

Bunun bir ayırıcı olup olmadığını gösterir.

```
virtual BOOL IsSeparator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman bu sınıf için DOĞRU.

## <a name="cmfcribbonseparatoristabstop"></a><a name="istabstop"></a>CMFCRibbonSeparator::IsTabStop

Bunun bir sekme durağı olup olmadığını gösterir.

```
virtual BOOL IsTabStop() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman bu sınıf için YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Şerit ayırıcısek sekme durağı değildir.

## <a name="cmfcribbonseparatorondraw"></a><a name="ondraw"></a>CMFCRibbonSeparator::OnDraw

Şerit veya Hızlı Erişim Araç Çubuğu üzerinde ayırıcı çizmek için sistem tarafından çağrılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

## <a name="cmfcribbonseparatorondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonSeparator::OnDrawOnList

**Komutlar** listesinde ayırıcı çizmek için sistem tarafından çağrıldı.

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
|*Pdc*|[içinde] Aygıt bağlamına işaretçi.|
|*strText*|[içinde] Listede görüntülenen metin.|
|*nTextOffset*|[içinde] Metnin ve sınırlayıcı dikdörtgenin sol tarafı arasında boşluk.|
|*Rect*|[içinde] Sınırlayıcı dikdörtgeni belirtir.|
|*bIsSelected*|[içinde] Göz ardı.|
|*bVurgulu*|[içinde] Göz ardı.|

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
