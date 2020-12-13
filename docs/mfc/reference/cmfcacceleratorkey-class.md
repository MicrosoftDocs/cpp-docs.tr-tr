---
description: 'Daha fazla bilgi edinin: CMFCAcceleratorKey Class'
title: CMFCAcceleratorKey sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
ms.openlocfilehash: cb7fc24c4cb4d092c5f109ad892b3778d74a906f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336611"
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey sınıfı

Sanal anahtar eşlemesini ve biçimlendirmeyi uygulayan yardımcı sınıf.

## <a name="syntax"></a>Syntax

```
class CMFCAcceleratorKey : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Bir `CMFCAcceleratorKey` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKey:: Format](#format)|ACCEL yapısını görsel gösterimine çevirir.|
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|Nesne için kısayol tuşunu ayarlar `CMFCAcceleratorKey` .|

## <a name="remarks"></a>Açıklamalar

Hızlandırıcı tuşları kısayol tuşları olarak da bilinir. Bir kullanıcının girdiği klavye kısayollarını göstermek istiyorsanız, [CMFCAcceleratorKeyAssignCtrl sınıfı](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) alt + SHIFT + s gibi klavye kısayollarını "alt + SHIFT + s" gibi özel bir metin biçimine eşler. Her `CMFCAcceleratorKey` nesne tek bir kısayol tuşunu bir metin biçimine eşler.

Kısayol tuşlarının ve Hızlandırıcı tablolarının nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [CKeyboardManager sınıfı](../../mfc/reference/ckeyboardmanager-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu ve yönteminin nasıl kullanılacağını gösterir `CMFCAcceleratorKey` `Format` .

[!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAcceleratorKey`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxivatorkey. h

## <a name="cmfcacceleratorkeycmfcacceleratorkey"></a><a name="cmfcacceleratorkey"></a> CMFCAcceleratorKey::CMFCAcceleratorKey

Bir [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) nesnesi oluşturur.

```
CMFCAcceleratorKey();
CMFCAcceleratorKey(LPACCEL lpAccel);
```

### <a name="parameters"></a>Parametreler

*lpAccel*<br/>
'ndaki Kısayol tuşu işaretçisi.

### <a name="remarks"></a>Açıklamalar

Oluştururken bir kısayol tuşu sağlamazsanız `CMFCAccleratorKey` , bir kısayol tuşunu nesneniz ile ilişkilendirmek Için [CMFCAcceleratorKey:: SetAccelerator](#setaccelerator) yöntemini kullanın `CMFCAcceleratorKey` .

## <a name="cmfcacceleratorkeyformat"></a><a name="format"></a> CMFCAcceleratorKey:: Format

ACCEL yapısını ilişkili dize değerine çevirir.

```cpp
void Format(CString& str) const;
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
dışı `CString` Yöntemin çevrilmiş kısayol tuşunu yazdığı bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ilişkili kısayol tuşunun dize biçimini alır. [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) nesnesinin dize biçimini ya oluşturucuyu ya da [CMFCAcceleratorKey:: SetAccelerator](#setaccelerator)yöntemini kullanarak ayarlayabilirsiniz.

## <a name="cmfcacceleratorkeysetaccelerator"></a><a name="setaccelerator"></a> CMFCAcceleratorKey::SetAccelerator

[CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) nesnesi için kısayol tuşunu ayarlar.

```cpp
void SetAccelerator(LPACCEL lpAccel);
```

### <a name="parameters"></a>Parametreler

*lpAccel*<br/>
'ndaki Kısayol tuşu işaretçisi.

### <a name="remarks"></a>Açıklamalar

Oluşturduğunuzda bir kısayol tuşu sağlamazsanız bir için kısayol tuşunu ayarlamak için bu yöntemi kullanın `CMFCAcceleratorKey` `CMFCAcceleratorKey` .

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager sınıfı](../../mfc/reference/ckeyboardmanager-class.md)
