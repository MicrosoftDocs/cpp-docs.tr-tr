---
title: CMFCAcceleratorKeyAssignCtrl Sınıfı
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
ms.openlocfilehash: 2021a2069885c6314859a65d528cf03712c524b6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751739"
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl Sınıfı

Sınıf, `CMFCAcceleratorKeyAssignCtrl` ALT, CONTROL ve SHIFT gibi ek sistem düğmelerini desteklemek için [CEdit Sınıfını](../../mfc/reference/cedit-class.md) genişletir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCAcceleratorKeyAssignCtrl : public CEdit
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](#cmfcacceleratorkeyassignctrl)|Bir `CMFCAcceleratorKeyAssignCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)|Nesneye `ACCEL` basılmış bir kısayol tuşu için yapıyı `CMFCAcceleratorKeyAssignCtrl` alır.|
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](#isfocused)||
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|Bir kısayol anahtarının tanımlanıp tanımlanmadığını belirler.|
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|[CWinApp](../../mfc/reference/cwinapp-class.md) sınıfı tarafından, pencere iletilerini [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine gönderilmeden önce çevirmek için kullanılır. [(CWnd geçersiz kılar::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|Kısayol anahtarını sıfırlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, hızlandırıcı `CEdit` tuşları olarak da bilinen kısayol tuşlarını destekleyerek sınıfın işlevselliğini genişletir. Sınıf `CMFCAcceleratorKeyAssignCtrl` [bir CEdit Sınıfı](../../mfc/reference/cedit-class.md) olarak işlev görür ve sistem düğmelerini de tanıyabilir.

Bu sınıf, fiziksel kısayol tuşu birleşimlerini dize değerleriyle eşler. Örneğin, ALT + B tuş kombinasyonunun "Alt + B" dizesine eşlendirildigini varsayalım. Kullanıcı bu tuş kombinasyonunu bir `CMFCAcceleratorKeyAssignCtrl` nesnede bastığında kullanıcıya "Alt + B" görüntülenir. Kısayol tuşları ve dize biçimi arasındaki eşleme hakkında daha fazla bilgi için [CMFCAcceleratorKey Class'a](../../mfc/reference/cmfcacceleratorkey-class.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCAcceleratorKeyAssignCtrl` nesnenin nasıl oluşturup kısayol anahtarını sıfırlamak için yöntemini `ResetKey` nasıl kullanılacağını gösterir.

[!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cedit](../../mfc/reference/cedit-class.md)

`CMFCAcceleratorKeyAssignCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxacceleratorkeyassignctrl.h

## <a name="cmfcacceleratorkeyassignctrlcmfcacceleratorkeyassignctrl"></a><a name="cmfcacceleratorkeyassignctrl"></a>CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl

[CMFCAcceleratorKeyAssignCtrl nesnesi](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) oluşturuyor.

```
CMFCAcceleratorKeyAssignCtrl();
```

## <a name="cmfcacceleratorkeyassignctrlgetaccel"></a><a name="getaccel"></a>CMFCAcceleratorKeyAssignCtrl::GetAccel

`ACCEL` [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesnesinde basıldığında bir kısayol tuşu için yapıyı alır.

```
ACCEL const* GetAccel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kısayol anahtarını açıklayan bir `ACCEL` yapı.

### <a name="remarks"></a>Açıklamalar

Kullanıcının nesnenize `CMFCAcceleratorKeyAssignCtrl` `ACCEL` girdiği bir kısayol anahtarı için yapıyı almak için bu işlevi kullanın.

## <a name="cmfcacceleratorkeyassignctrlisfocused"></a><a name="isfocused"></a>CMFCAcceleratorKeyAssignCtrl::IsFocused

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
BOOL IsFocused() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcacceleratorkeyassignctrliskeydefined"></a><a name="iskeydefined"></a>CMFCAcceleratorKeyAssignCtrl::IsKeyDefined

[CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesnesinde bir kısayol anahtarının tanımlanıp tanımlanmadığını belirler.

```
BOOL IsKeyDefined() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı bir kısayol tuşu tanımlayan geçerli bir tuş kombinasyonuna basmışsa sıfır alama; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kullanıcının nesnenize `CMFCAcceleratorKeyAssignCtrl` geçerli bir kısayol anahtarı girip girmediğini belirlemek için bu işlevi kullanın. Bir kısayol tuşu varsa, [cmfcacceleratorKeyAssignCtrl::GetAccel](#getaccel) yöntemini `ACCEL` kullanarak bu kısayol tuşuile ilişkili yapıyı elde edebilirsiniz.

## <a name="cmfcacceleratorkeyassignctrlpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

[içinde] *pMsg*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcacceleratorkeyassignctrlresetkey"></a><a name="resetkey"></a>CMFCAcceleratorKeyAssignCtrl::ResetKey

Kısayol anahtarını sıfırlar.

```cpp
void ResetKey();
```

### <a name="remarks"></a>Açıklamalar

İşlev, denetim metnini edinimi temizler. Bu, kullanıcının bastığı tüm kısayol tuşlarını içerir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAcceleratorKey Sınıfı](../../mfc/reference/cmfcacceleratorkey-class.md)
