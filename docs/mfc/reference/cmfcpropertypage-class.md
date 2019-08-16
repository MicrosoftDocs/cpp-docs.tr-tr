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
ms.openlocfilehash: 4be584135ef789d7fbe3b1743ac0ad6ce66ac5b1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505038"
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
|[CMFCPropertyPage:: CMFCPropertyPage](#cmfcpropertypage)|Bir `CMFCPropertyPage` nesnesi oluşturur.|
|`CMFCPropertyPage::~CMFCPropertyPage`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|`CMFCPropertyPage::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|`CMFCPropertyPage::OnSetActive`|Bu üye işlevi, sayfa Kullanıcı tarafından seçildiğinde çerçeve tarafından çağrılır ve etkin sayfa olur. ( [CPropertyPage:: OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive)geçersiz kılar.)|
|`CMFCPropertyPage::PreTranslateMessage`|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini çevirir. Daha fazla bilgi ve Yöntem sözdizimi için bkz. [CWnd::P reTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz `CPropertyPage::PreTranslateMessage`kılmalar.)|

## <a name="remarks"></a>Açıklamalar

`CMFCPropertyPage` Sınıfı, bir özellik sayfasının tek tek sayfalarını temsil eder, aksi halde sekme iletişim kutusu olarak bilinir.

Sınıfını CMFCPropertySheet sınıfıyla birlikte kullanın. [](../../mfc/reference/cmfcpropertysheet-class.md) `CMFCPropertyPage` Bir özellik sayfasında menüleri kullanmak için, `CPropertyPage` sınıfın `CMFCPropertyPage` tüm oluşumlarını sınıfla değiştirin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpropertypage. h

##  <a name="cmfcpropertypage"></a>CMFCPropertyPage:: CMFCPropertyPage

Bir `CMFCPropertyPage` nesnesi oluşturur.

```
CMFCPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption=0);

CMFCPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption=0);
```

### <a name="parameters"></a>Parametreler

*Nıdtemplate*<br/>
Bu sayfa için şablonun kaynak KIMLIĞI.

*nIDCaption*<br/>
Bu sayfanın sekmesine yerleştirilecek etiketin kaynak KIMLIĞI. 0 ise, bu sayfanın iletişim kutusu şablonundan ad alınır. Varsayılan değer 0’dır.

*lpszTemplateName*<br/>
Bu sayfa için şablon adını gösterir. NULL olamaz.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Oluşturucu parametreleri hakkında daha fazla bilgi için bkz. [CPropertyPage:: CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertySheet Sınıfı](../../mfc/reference/cmfcpropertysheet-class.md)
