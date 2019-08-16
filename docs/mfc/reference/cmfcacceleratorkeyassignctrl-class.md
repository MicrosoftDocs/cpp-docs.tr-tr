---
title: CMFCAcceleratorKeyAssignCtrl sınıfı
ms.date: 10/18/2018
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::GetAccel
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsFocused
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::ResetKey
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl [MFC], CMFCAcceleratorKeyAssignCtrl
- CMFCAcceleratorKeyAssignCtrl [MFC], GetAccel
- CMFCAcceleratorKeyAssignCtrl [MFC], IsFocused
- CMFCAcceleratorKeyAssignCtrl [MFC], IsKeyDefined
- CMFCAcceleratorKeyAssignCtrl [MFC], PreTranslateMessage
- CMFCAcceleratorKeyAssignCtrl [MFC], ResetKey
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
ms.openlocfilehash: 5e57bf149fdbc293692c613afcabcf2d11d32221
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505465"
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl sınıfı

Sınıfı, alt, denetim ve kaydırma gibi ek sistem düğmelerini desteklemek için [cedıt sınıfını genişletir.](../../mfc/reference/cedit-class.md) `CMFCAcceleratorKeyAssignCtrl`

## <a name="syntax"></a>Sözdizimi

```
class CMFCAcceleratorKeyAssignCtrl : public CEdit
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](#cmfcacceleratorkeyassignctrl)|Bir `CMFCAcceleratorKeyAssignCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl:: GetAccel](#getaccel)|Nesnede basılan bir kısayol tuşu için yapıyıalır.`ACCEL` `CMFCAcceleratorKeyAssignCtrl`|
|[CMFCAcceleratorKeyAssignCtrl:: ısodaklanmış](#isfocused)||
|[CMFCAcceleratorKeyAssignCtrl:: ıskeydefined](#iskeydefined)|Bir kısayol tuşunun tanımlanıp tanımlanmadığını belirler.|
|[CMFCAcceleratorKeyAssignCtrl::P reTranslateMessage](#pretranslatemessage)|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini dönüştürmek için [CWinApp](../../mfc/reference/cwinapp-class.md) sınıfı tarafından kullanılır. ( [CWnd::P reTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)geçersiz kılar.)|
|[CMFCAcceleratorKeyAssignCtrl:: ResetKey](#resetkey)|Kısayol tuşunu sıfırlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, hızlandırıcı tuşları olarak da `CEdit` bilinen kısayol tuşlarını destekleyerek sınıfının işlevselliğini genişletir. Sınıfı `CMFCAcceleratorKeyAssignCtrl` , bir [cedıt sınıfı](../../mfc/reference/cedit-class.md) olarak çalışır ve ayrıca sistem düğmelerini de algılayabilir.

Bu sınıf, fiziksel kısayol tuş bileşimlerini dize değerleriyle eşler. Örneğin, ALT + B tuş bileşiminin "alt + B" dizesiyle eşlendiği varsayılır. Kullanıcı bir `CMFCAcceleratorKeyAssignCtrl` nesnedeki bu tuş birleşimine bastığında, "alt + B" kullanıcıya gösterilir. Kısayol tuşları ve dize biçimi arasındaki eşleme hakkında daha fazla bilgi için bkz. [CMFCAcceleratorKey Class](../../mfc/reference/cmfcacceleratorkey-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCAcceleratorKeyAssignCtrl` nesnesinin nasıl oluşturulduğunu ve kısayol tuşunu sıfırlamak için `ResetKey` yönteminin nasıl kullanılacağını gösterir.

[!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CMFCAcceleratorKeyAssignCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxivatorkeyassignctrl. h

##  <a name="cmfcacceleratorkeyassignctrl"></a>CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl

Bir [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesnesi oluşturur.

```
CMFCAcceleratorKeyAssignCtrl();
```

##  <a name="getaccel"></a>CMFCAcceleratorKeyAssignCtrl:: GetAccel

[CMFCAcceleratorKeyAssignCtrl nesnesinde](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) basılan bir kısayol tuşu için yapıyı`ACCEL` alır.

```
ACCEL const* GetAccel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kısayol `ACCEL` tuşunu tanımlayan bir yapı.

### <a name="remarks"></a>Açıklamalar

Kullanıcının `ACCEL` nesneniz`CMFCAcceleratorKeyAssignCtrl` içine girdiği bir kısayol tuşu yapısını almak için bu işlevi kullanın.

##  <a name="isfocused"></a>CMFCAcceleratorKeyAssignCtrl:: ısodaklanmış

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC\\atlmfc\\\\src MFC** klasöründe bulunan kaynak koduna bakın.

```
BOOL IsFocused() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="iskeydefined"></a>CMFCAcceleratorKeyAssignCtrl:: ıskeydefined

[CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesnesinde bir kısayol tuşunun tanımlanıp tanımlanmadığını belirler.

```
BOOL IsKeyDefined() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı bir kısayol tuşunu tanımlayan geçerli bir anahtarlar birleşimini zaten basmışsa sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kullanıcının `CMFCAcceleratorKeyAssignCtrl` nesneniz için geçerli bir kısayol tuşu girilip girmediğini öğrenmek için bu işlevi kullanın. Bir kısayol tuşu varsa, bu kısayol tuşuyla ilişkili `ACCEL` yapıyı elde etmek için [CMFCAcceleratorKeyAssignCtrl:: GetAccel](#getaccel) metodunu kullanabilirsiniz.

##  <a name="pretranslatemessage"></a>CMFCAcceleratorKeyAssignCtrl::P reTranslateMessage

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC\\atlmfc\\\\src MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

'ndaki *pMsg*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="resetkey"></a>CMFCAcceleratorKeyAssignCtrl:: ResetKey

Kısayol tuşunu sıfırlar.

```
void ResetKey();
```

### <a name="remarks"></a>Açıklamalar

İşlevi, düzenleme denetim metnini temizler. Buna kullanıcının bastığı kısayol tuşları dahildir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAcceleratorKey Sınıfı](../../mfc/reference/cmfcacceleratorkey-class.md)
