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
ms.openlocfilehash: 6d296966001dcbc2279a298bdd1d9c21195d61fd
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840785"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton sınıfı

Masaüstü Uyarısı iletişim kutusuna düğmelerin eklenmesine izin verir.

## <a name="syntax"></a>Syntax

```
class CMFCDesktopAlertWndButton : public CMFCButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|-|-|
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Varsayılan Oluşturucu.|
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|[CMFCDesktopAlertWndButton:: IsCaptionButton](#iscaptionbutton)|Düğmenin, uyarı iletişim kutusunun resim yazısı alanında görüntülenip görüntülenmeyeceğini belirler.|
|[CMFCDesktopAlertWndButton:: IsCloseButton](#isclosebutton)|Düğmenin uyarı iletişim kutusunu kapatıp kapatmadığını belirler.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|-|-|
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Düğmenin, uyarı iletişim kutusunun resim yazısı alanında görüntülenip görüntülenmeyeceğini belirten bir Boole değeri.|
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Düğmenin uyarı iletişim kutusunu kapatıp kapatmadığını belirten bir Boole değeri.|

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, Oluşturucu `m_bIsCaptionButton` ve `m_bIsCloseButton` VERI üyelerini yanlış olarak ayarlar. `CMFCDesktopAlertDialog` `m_bIsCaptionButton` Düğme, uyarı iletişim kutusunun resim yazısı alanında konumlandırılmışsa, üst nesne doğru olarak ayarlanır. `CMFCDesktopAlertDialog`Sınıfı, `CMFCDesktopAlertWndButton` uyarı iletişim kutusunu kapatan ve true olarak ayarlayan düğme görevi gören bir nesne oluşturur `m_bIsCloseButton` .

`CMFCDesktopAlertWndButton`Nesneleri bir `CMFCDesktopAlertDialog` düğmeye ekleyeceğiniz şekilde nesne ekleyin. Hakkında daha fazla bilgi için `CMFCDesktopAlertDialog` bkz. [CMFCDesktopAlertDialog sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında yönteminin nasıl kullanılacağını gösterir `SetImage` `CMFCDesktopAlertWndButton` . Bu kod parçacığı, [Masaüstü Uyarısı tanıtım örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

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

**Üstbilgi:** afxDesktopAlertWnd. h

## <a name="cmfcdesktopalertwndbuttoniscaptionbutton"></a><a name="iscaptionbutton"></a> CMFCDesktopAlertWndButton:: IsCaptionButton

Düğmenin, uyarı iletişim kutusunun resim yazısı alanında görüntülenip görüntülenmeyeceğini belirler.

```
BOOL IsCaptionButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme, uyarı iletişim kutusunun resim yazısı alanında görüntüleniyorsa sıfır dışı. Aksi takdirde, 0.

## <a name="cmfcdesktopalertwndbuttonisclosebutton"></a><a name="isclosebutton"></a> CMFCDesktopAlertWndButton:: IsCloseButton

Düğmenin uyarı iletişim kutusunu kapatıp kapatmadığını belirler.

```
BOOL IsCloseButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme, uyarı iletişim kutusunu kapatırsa sıfır dışı. Aksi takdirde, 0.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertDialog sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md)
