---
title: CMFCPropertyPage sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
ms.openlocfilehash: 62e33da998f1e5332436d887c38d3fd65526561b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288525"
---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage sınıfı

`CMFCPropertyPage` Sınıfı, bir özellik sayfasında açılır menülerin görüntülenmesini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|Oluşturur bir `CMFCPropertyPage` nesne.|
|`CMFCPropertyPage::~CMFCPropertyPage`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|`CMFCPropertyPage::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|`CMFCPropertyPage::OnSetActive`|Sayfa kullanıcı tarafından seçilir ve etkin sayfa olur, bu üye işlevi framework tarafından çağırılır. (Geçersiz kılmaları [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|
|`CMFCPropertyPage::PreTranslateMessage`|Pencere iletileri için dağıtılmadan önce çevirir [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows işlevleri. Daha fazla bilgi ve yöntem sözdizimi için bkz. [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz kılmaları `CPropertyPage::PreTranslateMessage`.)|

## <a name="remarks"></a>Açıklamalar

`CMFCPropertyPage` Sınıfı, aksi takdirde bir sekme iletişim kutusu bilinen bir özellik sayfası, her bir sayfayı temsil eder.

Kullanım `CMFCPropertyPage` ile birlikte sınıfı [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) sınıfı. Bir özellik sayfasında menüleri kullanmak için tüm oluşumlarını değiştirin `CPropertyPage` sınıfıyla `CMFCPropertyPage` sınıfı.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxpropertypage.h

##  <a name="cmfcpropertypage"></a>  CMFCPropertyPage::CMFCPropertyPage

Oluşturur bir `CMFCPropertyPage` nesne.

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
Bu sayfa şablonu kaynak kimliği.

*nIDCaption*<br/>
Bu sayfa için sekmesinde koymak için etiketin kaynak kimliği. 0 ise, bu sayfa için iletişim kutusu şablonundan adı elde edilir. Varsayılan değer 0’dır.

*lpszTemplateName*<br/>
Bu sayfa şablonunun adını işaret. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Oluşturucu parametreler hakkında daha fazla bilgi için bkz. [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertySheet Sınıfı](../../mfc/reference/cmfcpropertysheet-class.md)
