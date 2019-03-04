---
title: CMFCDesktopAlertWndButton sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
helpviewer_keywords:
- CMFCDesktopAlertWndButton [MFC], IsCaptionButton
- CMFCDesktopAlertWndButton [MFC], IsCloseButton
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
ms.openlocfilehash: 2a9ade332c87f293719872e426fb459b011d2d35
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270273"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton sınıfı

Bir Masaüstü Uyarısı iletişim kutusu için eklenmesi için düğmeler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDesktopAlertWndButton : public CMFCButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Varsayılan Oluşturucu.|
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|Düğme Uyarısı iletişim kutusu başlık alanında görüntülenip görüntülenmeyeceğini belirler.|
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|Düğme uyarı iletişim kutusu kapanır olup olmadığını belirler.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|Ad|Açıklama|
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Düğme Uyarısı iletişim kutusu başlık alanında görüntülenip görüntülenmeyeceğini belirten bir Boole değeri.|
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Düğme uyarı iletişim kutusu kapanır olup olmadığını belirten bir Boole değeri.|

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, oluşturucu ayarlar `m_bIsCaptionButton` ve `m_bIsCloseButton` veri üyeleri false. Üst `CMFCDesktopAlertDialog` nesne kümeleri `m_bIsCaptionButton` düğme Uyarısı iletişim kutusu başlık alanında konumlandırılır varsa TRUE. `CMFCDesktopAlertDialog` Sınıfı oluşturur bir `CMFCDesktopAlertWndButton` uyarı iletişim kutusu kapanır düğme olarak görev yapar kutusuna ve ayarlar nesnesi `m_bIsCloseButton` true.

Ekleme `CMFCDesktopAlertWndButton` nesneleri için bir `CMFCDesktopAlertDialog` nesnesi, herhangi bir düğme olduğu gibi. Hakkında daha fazla bilgi için `CMFCDesktopAlertDialog`, bkz: [CMFCDesktopAlertDialog sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `SetImage` yönteminde `CMFCDesktopAlertWndButton` sınıfı. Bu kod parçacığı parçasıdır [Masaüstü uyarı gösterim örneği](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdesktopalertwnd.h

##  <a name="iscaptionbutton"></a>  CMFCDesktopAlertWndButton::IsCaptionButton

Düğme Uyarısı iletişim kutusu başlık alanında görüntülenip görüntülenmeyeceğini belirler.

```
BOOL IsCaptionButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme Uyarısı iletişim kutusu başlık alanında görüntülenen olursa sıfır dışı; Aksi takdirde 0.

##  <a name="isclosebutton"></a>  CMFCDesktopAlertWndButton::IsCloseButton

Düğme uyarı iletişim kutusu kapanır olup olmadığını belirler.

```
BOOL IsCloseButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme uyarı iletişim kutusu kapanır olursa sıfır dışı; Aksi takdirde 0.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertDialog Sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md)
