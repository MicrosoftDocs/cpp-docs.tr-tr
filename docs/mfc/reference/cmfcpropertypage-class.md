---
title: CMFCPropertyPage Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
ms.openlocfilehash: e493f016b6384a768935186c31e3fc71ade6382f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361768"
---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage Sınıfı

Sınıf, `CMFCPropertyPage` özellik sayfasında açılır menülerin görüntülenmesini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCÖzellik Sayfası::CMFCÖzellik Sayfası](#cmfcpropertypage)|Bir `CMFCPropertyPage` nesne inşa eder.|
|`CMFCPropertyPage::~CMFCPropertyPage`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|`CMFCPropertyPage::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|`CMFCPropertyPage::OnSetActive`|Bu üye işlev, sayfa kullanıcı tarafından seçildiğinde ve etkin sayfa olduğunda çerçeve tarafından çağrılır. (CPropertyPage geçersiz [kılar::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|
|`CMFCPropertyPage::PreTranslateMessage`|Pencere iletilerini [Çeviri İletisi](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine gönderilmeden önce çevirir. Daha fazla bilgi ve yöntem sözdizimi için [Bkz. CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz `CPropertyPage::PreTranslateMessage`kılar .)|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CMFCPropertyPage` bir özellik sayfasının tek tek sayfalarını, aksi takdirde sekme iletişim kutusu olarak bilinir.

`CMFCPropertyPage` [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) sınıfıyla birlikte sınıfı kullanın. Özellik sayfasındaki menüleri kullanmak için sınıfın tüm `CPropertyPage` oluşumlarını `CMFCPropertyPage` sınıfla değiştirin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[Cpropertypage](../../mfc/reference/cpropertypage-class.md)

[CMFCÖzellik Sayfası](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertypage.h

## <a name="cmfcpropertypagecmfcpropertypage"></a><a name="cmfcpropertypage"></a>CMFCÖzellik Sayfası::CMFCÖzellik Sayfası

Bir `CMFCPropertyPage` nesne inşa eder.

```
CMFCPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption=0);

CMFCPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption=0);
```

### <a name="parameters"></a>Parametreler

*nIDTemplate*<br/>
Bu sayfaiçin şablonun kaynak kimliği.

*nIDCaption*<br/>
Bu sayfanın sekmesine koymak için etiketin kaynak kimliği. 0 ise, ad bu sayfanın iletişim kutusu şablonundan elde edilir. Varsayılan değer 0’dır.

*lpszTemplateName*<br/>
Bu sayfanın şablonunun adını gösterir. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Oluşturucu parametrelerhakkında daha fazla bilgi için [Bkz. CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertySheet Sınıfı](../../mfc/reference/cmfcpropertysheet-class.md)
