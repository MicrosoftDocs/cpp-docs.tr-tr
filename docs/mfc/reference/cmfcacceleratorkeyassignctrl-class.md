---
description: 'Daha fazla bilgi edinin: CMFCAcceleratorKeyAssignCtrl Class'
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
ms.openlocfilehash: 0f5584dfa521f45841691bff3775d9cd98808b9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336595"
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl sınıfı

`CMFCAcceleratorKeyAssignCtrl`Sınıfı, alt, denetim ve kaydırma gibi ek sistem düğmelerini desteklemek Için [cedıt sınıfını](../../mfc/reference/cedit-class.md) genişletir.

## <a name="syntax"></a>Syntax

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
|[CMFCAcceleratorKeyAssignCtrl:: GetAccel](#getaccel)|`ACCEL`Nesnede basılan bir kısayol tuşu için yapıyı alır `CMFCAcceleratorKeyAssignCtrl` .|
|[CMFCAcceleratorKeyAssignCtrl:: ısodaklanmış](#isfocused)||
|[CMFCAcceleratorKeyAssignCtrl:: ıskeydefined](#iskeydefined)|Bir kısayol tuşunun tanımlanıp tanımlanmadığını belirler.|
|[CMFCAcceleratorKeyAssignCtrl::P reTranslateMessage](#pretranslatemessage)|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini dönüştürmek için [CWinApp](../../mfc/reference/cwinapp-class.md) sınıfı tarafından kullanılır. ( [CWnd::P reTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)geçersiz kılar.)|
|[CMFCAcceleratorKeyAssignCtrl:: ResetKey](#resetkey)|Kısayol tuşunu sıfırlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, `CEdit` hızlandırıcı tuşları olarak da bilinen kısayol tuşlarını destekleyerek sınıfının işlevselliğini genişletir. `CMFCAcceleratorKeyAssignCtrl`Sınıfı, bir [cedıt sınıfı](../../mfc/reference/cedit-class.md) olarak çalışır ve ayrıca sistem düğmelerini de algılayabilir.

Bu sınıf, fiziksel kısayol tuş bileşimlerini dize değerleriyle eşler. Örneğin, ALT + B tuş bileşiminin "alt + B" dizesiyle eşlendiği varsayılır. Kullanıcı bir nesnedeki bu tuş birleşimine bastığında `CMFCAcceleratorKeyAssignCtrl` , "alt + B" kullanıcıya gösterilir. Kısayol tuşları ve dize biçimi arasındaki eşleme hakkında daha fazla bilgi için bkz. [CMFCAcceleratorKey Class](../../mfc/reference/cmfcacceleratorkey-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu `CMFCAcceleratorKeyAssignCtrl` ve `ResetKey` kısayol tuşunu sıfırlamak için yönteminin nasıl kullanılacağını gösterir.

[!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CMFCAcceleratorKeyAssignCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxivatorkeyassignctrl. h

## <a name="cmfcacceleratorkeyassignctrlcmfcacceleratorkeyassignctrl"></a><a name="cmfcacceleratorkeyassignctrl"></a> CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl

Bir [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesnesi oluşturur.

```
CMFCAcceleratorKeyAssignCtrl();
```

## <a name="cmfcacceleratorkeyassignctrlgetaccel"></a><a name="getaccel"></a> CMFCAcceleratorKeyAssignCtrl:: GetAccel

`ACCEL` [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesnesinde basılan bir kısayol tuşu için yapıyı alır.

```
ACCEL const* GetAccel() const;
```

### <a name="return-value"></a>Dönüş Değeri

`ACCEL`Kısayol tuşunu tanımlayan bir yapı.

### <a name="remarks"></a>Açıklamalar

`ACCEL`Kullanıcının nesneniz içine girdiği bir kısayol tuşu yapısını almak için bu işlevi kullanın `CMFCAcceleratorKeyAssignCtrl` .

## <a name="cmfcacceleratorkeyassignctrlisfocused"></a><a name="isfocused"></a> CMFCAcceleratorKeyAssignCtrl:: ısodaklanmış

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
BOOL IsFocused() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcacceleratorkeyassignctrliskeydefined"></a><a name="iskeydefined"></a> CMFCAcceleratorKeyAssignCtrl:: ıskeydefined

[CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesnesinde bir kısayol tuşunun tanımlanıp tanımlanmadığını belirler.

```
BOOL IsKeyDefined() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı bir kısayol tuşunu tanımlayan geçerli bir anahtarlar birleşimini zaten basmışsa sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kullanıcının nesneniz için geçerli bir kısayol tuşu girilip girmediğini öğrenmek için bu işlevi kullanın `CMFCAcceleratorKeyAssignCtrl` . Bir kısayol tuşu varsa, bu kısayol tuşuyla ilişkili yapıyı elde etmek için [CMFCAcceleratorKeyAssignCtrl:: GetAccel](#getaccel) metodunu kullanabilirsiniz `ACCEL` .

## <a name="cmfcacceleratorkeyassignctrlpretranslatemessage"></a><a name="pretranslatemessage"></a> CMFCAcceleratorKeyAssignCtrl::P reTranslateMessage

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

'ndaki *pMsg*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcacceleratorkeyassignctrlresetkey"></a><a name="resetkey"></a> CMFCAcceleratorKeyAssignCtrl:: ResetKey

Kısayol tuşunu sıfırlar.

```cpp
void ResetKey();
```

### <a name="remarks"></a>Açıklamalar

İşlevi, düzenleme denetim metnini temizler. Buna kullanıcının bastığı kısayol tuşları dahildir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAcceleratorKey sınıfı](../../mfc/reference/cmfcacceleratorkey-class.md)
