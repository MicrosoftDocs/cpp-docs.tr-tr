---
title: CMFCAcceleratorKeyAssignCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::GetAccel
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsFocused
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::ResetKey
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl [MFC], CMFCAcceleratorKeyAssignCtrl
- CMFCAcceleratorKeyAssignCtrl [MFC], GetAccel
- CMFCAcceleratorKeyAssignCtrl [MFC], IsFocused
- CMFCAcceleratorKeyAssignCtrl [MFC], IsKeyDefined
- CMFCAcceleratorKeyAssignCtrl [MFC], PreTranslateMessage
- CMFCAcceleratorKeyAssignCtrl [MFC], ResetKey
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92b2fb4d9d96045886533f287fa7048d0b07c866
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388023"
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl sınıfı

`CMFCAcceleratorKeyAssignCtrl` Sınıfını genişleten [CEdit sınıfı](../../mfc/reference/cedit-class.md) ALT, CONTROL ve SHIFT gibi ek sistem düğmelerini desteklemek için.

## <a name="syntax"></a>Sözdizimi

```
class CMFCAcceleratorKeyAssignCtrl : public CEdit
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](#cmfcacceleratorkeyassignctrl)|Oluşturur bir `CMFCAcceleratorKeyAssignCtrl` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)|Alır `ACCEL` bir kısayol tuşu basılı için yapı `CMFCAcceleratorKeyAssignCtrl` nesne.|
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](#isfocused)||
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|Bir kısayol tuşu tanımlı olup olmadığını belirler.|
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|Sınıfı tarafından kullanılan [CWinApp](../../mfc/reference/cwinapp-class.md) için dağıtılmadan önce pencere iletilerini çevrilecek [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows işlevleri. (Geçersiz kılmaları [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|Kısayol tuşu sıfırlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf işlevselliğini genişletir `CEdit` kısayol tuşları, olarak da bilinen hızlandırma tuşları destekleyerek sınıfı. `CMFCAcceleratorKeyAssignCtrl` Sınıf işlevler olarak bir [CEdit sınıfı](../../mfc/reference/cedit-class.md) ve sistem düğmelerini tanıyabilir.

Bu sınıf, fiziksel kısayol tuş birleşimleri için dize değerlerini eşler. Örneğin, ALT tuş bileşimi varsayın + B "Alt + B" dizesine eşlenir. Bu tuş bileşimi, kullanıcının bastığında bir `CMFCAcceleratorKeyAssignCtrl` nesne "Alt + B", kullanıcıya görüntülenir. Kısayol tuşları ve dize biçimi arasındaki eşleme hakkında daha fazla bilgi için bkz: [CMFCAcceleratorKey sınıfı](../../mfc/reference/cmfcacceleratorkey-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCAcceleratorKeyAssignCtrl` nesne ve kullanmak, `ResetKey` kısayol tuşunu sıfırlamak için yöntemi.

[!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CMFCAcceleratorKeyAssignCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxacceleratorkeyassignctrl.h

##  <a name="cmfcacceleratorkeyassignctrl"></a>  CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl

Oluşturur bir [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesne.

```
CMFCAcceleratorKeyAssignCtrl();
```

##  <a name="getaccel"></a>  CMFCAcceleratorKeyAssignCtrl::GetAccel

Alır `ACCEL` bir kısayol tuşu basılı için yapı [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesne.

```
ACCEL const* GetAccel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `ACCEL` kısayol tuşunu açıklayan yapısı.

### <a name="remarks"></a>Açıklamalar

Almak için bu işlevi kullanın `ACCEL` yapısı için girilen kullanıcı bir kısayol tuşu, `CMFCAcceleratorKeyAssignCtrl` nesne.

##  <a name="isfocused"></a>  CMFCAcceleratorKeyAssignCtrl::IsFocused

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

```
BOOL IsFocused() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="iskeydefined"></a>  CMFCAcceleratorKeyAssignCtrl::IsKeyDefined

Bir kısayol tuşu içinde tanımlanmış olup olmadığını belirler [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesne.

```
BOOL IsKeyDefined() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı zaten bir kısayol tuşu tanımlayan anahtar geçerli bir bileşim bastığını olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Geçerli bir kısayol tuşu, kullanıcı tarafından girilen olup olmadığını belirlemek için bu işlevi kullanın, `CMFCAcceleratorKeyAssignCtrl` nesne. Bir kısayol tuşu varsa, kullanabileceğiniz [CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel) elde etmek için yöntemi `ACCEL` yapısı bu kısayol tuşu ile ilişkili.

##  <a name="pretranslatemessage"></a>  CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

[in] *pMsg*

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="resetkey"></a>  CMFCAcceleratorKeyAssignCtrl::ResetKey

Kısayol tuşu sıfırlar.

```
void ResetKey();
```

### <a name="remarks"></a>Açıklamalar

İşlev düzenleme denetimi metni temizler. Bu kullanıcı basılan tüm kısayol tuşları içerir.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAcceleratorKey Sınıfı](../../mfc/reference/cmfcacceleratorkey-class.md)
