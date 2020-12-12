---
description: 'Daha fazla bilgi edinin: CMFCRibbonSeparator sınıfı'
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
ms.openlocfilehash: db8e7f92089d1e6332fdb2ad057398c465c72f97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321754"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator sınıfı

Şerit ayırıcısını uygular.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonSeparator : public CMFCRibbonBaseElement
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|-|-|
|[CMFCRibbonSeparator:: Cmfcribbonayırıcısı](#cmfcribbonseparator)|Bir `CMFCRibbonSeparator` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|[CMFCRibbonSeparator:: AddToListBox](#addtolistbox)|**Özelleştir** Iletişim kutusundaki **Komutlar** listesine bir ayırıcı ekler. ( [CMFCRibbonBaseElement:: Addtolıst'](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox)i geçersiz kılar.)|
|`CMFCRibbonSeparator::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|`CMFCRibbonSeparator::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|-|-|
|[CMFCRibbonSeparator:: CopyFrom](#copyfrom)|Bir ayırıcının üye değişkenlerini başka bir nesneden ayarlayan bir Copy yöntemi.|
|[CMFCRibbonSeparator:: GetRegularSize](#getregularsize)|Bir ayırıcısının boyutunu döndürür.|
|[CMFCRibbonSeparator:: IsSeparator](#isseparator)|Bu bir ayırıcı olup olmadığını gösterir.|
|[CMFCRibbonSeparator:: IsTabStop](#istabstop)|Bu sekme durağı olup olmadığını gösterir.|
|[CMFCRibbonSeparator:: OnDraw](#ondraw)|Şerit ya da hızlı erişim araç çubuğu üzerinde ayırıcıyı çizmek için sistem tarafından çağırılır.|
|[CMFCRibbonSeparator:: OnDrawOnList](#ondrawonlist)|**Komut** listesinde ayırıcıyı çizmek için sistem tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Şerit ayırıcısı, Şerit öğelerini mantıksal olarak ayıran dikey veya yatay bir çizgi olur. Şerit denetimi, ana uygulama menüsü, şerit durum çubuğu ve hızlı erişim araç çubuğu üzerinde bir ayırıcı çizilebilirler.

Uygulamanızda bir ayırıcı kullanmak için, yeni nesneyi oluşturun ve burada gösterildiği gibi ana uygulama menüsüne ekleyin:

```
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```

Şerit panellere ayırıcılar eklemek için [CMFCRibbonPanel:: AddSeparator ' ı](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) çağırın. Ayırıcılar, yöntemi tarafından dahili olarak ayrılır ve eklenir `AddSeparator` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbonayırıcısı](../../mfc/reference/cmfcribbonseparator-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxbaseribbonelement. h

## <a name="cmfcribbonseparatoraddtolistbox"></a><a name="addtolistbox"></a> CMFCRibbonSeparator:: AddToListBox

**Özelleştir** Iletişim kutusundaki **Komutlar** listesine bir ayırıcı ekler.

```
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,
    BOOL bDeep);
```

### <a name="parameters"></a>Parametreler

*pWndListBox*<br/>
'ndaki Ayırıcı eklendiği **komut** listesine yönelik bir işaretçi.

*Bderin*<br/>
'ndaki LIP.

### <a name="return-value"></a>Dönüş Değeri

*PWndListBox* tarafından belirtilen liste kutusundaki dizenin sıfır tabanlı dizini.

## <a name="cmfcribbonseparatorcmfcribbonseparator"></a><a name="cmfcribbonseparator"></a> CMFCRibbonSeparator:: Cmfcribbonayırıcısı

Bir `CMFCRibbonSeparator` nesnesi oluşturur.

```
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```

### <a name="parameters"></a>Parametreler

*bIsHoriz*<br/>
'ndaki TRUE ise ayırıcı yataydır; YANLıŞSA, ayırıcı dikeydir.

### <a name="remarks"></a>Açıklamalar

Yatay ayırıcılar uygulama menülerinde kullanılır. Dikey ayırıcılar araç çubuklarında kullanılır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu gösterir `CMFCRibbonSeparator` .

[!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]

## <a name="cmfcribbonseparatorcopyfrom"></a><a name="copyfrom"></a> CMFCRibbonSeparator:: CopyFrom

Bir ayırıcının üye değişkenlerini başka bir nesneden ayarlayan bir Copy yöntemi.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parametreler

*YN*<br/>
'ndaki Kopyalanacak kaynak şerit öğesi.

## <a name="cmfcribbonseparatorgetregularsize"></a><a name="getregularsize"></a> CMFCRibbonSeparator:: GetRegularSize

Bir ayırıcısının boyutunu döndürür.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz içeriğine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen cihaz bağlamındaki ayırıcının boyutu.

## <a name="cmfcribbonseparatorisseparator"></a><a name="isseparator"></a> CMFCRibbonSeparator:: IsSeparator

Bu bir ayırıcı olup olmadığını gösterir.

```
virtual BOOL IsSeparator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu sınıf için her zaman TRUE.

## <a name="cmfcribbonseparatoristabstop"></a><a name="istabstop"></a> CMFCRibbonSeparator:: IsTabStop

Bu sekme durağı olup olmadığını gösterir.

```
virtual BOOL IsTabStop() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu sınıf için her zaman FALSE.

### <a name="remarks"></a>Açıklamalar

Şerit ayırıcısı bir sekme durağı değildir.

## <a name="cmfcribbonseparatorondraw"></a><a name="ondraw"></a> CMFCRibbonSeparator:: OnDraw

Şerit ya da hızlı erişim araç çubuğu üzerinde ayırıcıyı çizmek için sistem tarafından çağırılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

## <a name="cmfcribbonseparatorondrawonlist"></a><a name="ondrawonlist"></a> CMFCRibbonSeparator:: OnDrawOnList

**Komut** listesinde ayırıcıyı çizmek için sistem tarafından çağırılır.

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

*Kökündeki*\
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*strText*\
'ndaki Listede görünen metin.

*nTextOffset*\
'ndaki Sınırlayıcı dikdörtgenin metin ve sol kenarı arasındaki Aralık.

*Rect*\
'ndaki Sınırlayıcı dikdörtgeni belirtir.

*bIsSelected*\
'ndaki LIP.

*Bvurgulu*\
'ndaki LIP.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
