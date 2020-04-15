---
title: CMFCDesktopAlertWndButton Sınıfı
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
ms.openlocfilehash: 5b18a15f8bfd98396acae0558d121b32bc4127c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367620"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton Sınıfı

Düğmelerin masaüstü uyarı iletişim kutusuna eklenmesine izin verir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDesktopAlertWndButton : public CMFCButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Varsayılan oluşturucu.|
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|Düğmenin uyarı iletişim kutusunun resim yazısı alanında görüntülenip görüntülenmediğini belirler.|
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|Düğmenin uyarı iletişim kutusunu kapatıp kapatmayacağını belirler.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|Adı|Açıklama|
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Düğmenin uyarı iletişim kutusunun resim yazısı alanında görüntülenip görüntülenmediğini belirten bir Boolean değeri.|
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Düğmenin uyarı iletişim kutusunu kapatıp kapatmadığını belirten bir Boolean değeri.|

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, oluşturucu `m_bIsCaptionButton` ve `m_bIsCloseButton` veri üyelerini FALSE olarak ayarlar. Düğme `CMFCDesktopAlertDialog` uyarı `m_bIsCaptionButton` iletişim kutusunun resim yazısı alanında konumlandırılmışsa, ana nesne TRUE olarak ayarlar. Sınıf, `CMFCDesktopAlertDialog` uyarı `CMFCDesktopAlertWndButton` iletişim kutusunu kapatan ve TRUE'ya ayarlayan `m_bIsCloseButton` düğme olarak hizmet veren bir nesne oluşturur.

Herhangi `CMFCDesktopAlertWndButton` bir düğme `CMFCDesktopAlertDialog` eklergibi bir nesneye nesneler ekleyin. Hakkında `CMFCDesktopAlertDialog`daha fazla bilgi için [CMFCDesktopAlertDialog Class'a](../../mfc/reference/cmfcdesktopalertdialog-class.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemin sınıfta `SetImage` nasıl `CMFCDesktopAlertWndButton` kullanılacağını göstermektedir. Bu kod snippet [Masaüstü Uyarı Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cbutton](../../mfc/reference/cbutton-class.md)

[CMFCDüğmesi](../../mfc/reference/cmfcbutton-class.md)

[CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdesktopalertwnd.h

## <a name="cmfcdesktopalertwndbuttoniscaptionbutton"></a><a name="iscaptionbutton"></a>CMFCDesktopAlertWndButton::IsCaptionButton

Düğmenin uyarı iletişim kutusunun resim yazısı alanında görüntülenip görüntülenmediğini belirler.

```
BOOL IsCaptionButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uyarı iletişim kutusunun resim yazısı alanında düğme görüntüleniyorsa sıfıra sıfır değildir; aksi takdirde, 0.

## <a name="cmfcdesktopalertwndbuttonisclosebutton"></a><a name="isclosebutton"></a>CMFCDesktopAlertWndButton::IsCloseButton

Düğmenin uyarı iletişim kutusunu kapatıp kapatmayacağını belirler.

```
BOOL IsCloseButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme uyarı iletişim kutusunu kapatırsa sıfıra inme; aksi takdirde, 0.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertDialog Sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md)
