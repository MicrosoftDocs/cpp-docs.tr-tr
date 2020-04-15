---
title: CMFCAcceleratorKey Sınıfı
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
ms.openlocfilehash: 7d66e7043325bbbd324f3ac443368787a653ebe1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369923"
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey Sınıfı

Sanal anahtar eşleme ve biçimlendirme uygulayan yardımcı sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CMFCAcceleratorKey : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Bir `CMFCAcceleratorKey` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKey::Biçim](#format)|ACCEL yapısını görsel temsiline çevirir.|
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|Nesne için kısayol `CMFCAcceleratorKey` tuşunu ayarlar.|

## <a name="remarks"></a>Açıklamalar

Hızlandırıcı tuşları kısayol tuşları olarak da bilinir. Bir kullanıcının girdiği klavye kısayollarını görüntülemek istiyorsanız, [CMFCAcceleratorKeyAssignCtrl Class](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) alt+shift+s gibi klavye kısayollarını "Alt + Shift + S" gibi özel bir metin biçimiyle eşler. Her `CMFCAcceleratorKey` nesne metin biçimiyle tek bir kısayol anahtarıyla eşleştirilir.

Kısayol tuşları nın ve hızlandırıcı tablolarının nasıl kullanılacağı hakkında daha fazla bilgi için [CKeyboardManager Sınıfı'na](../../mfc/reference/ckeyboardmanager-class.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCAcceleratorKey` nesnenin nasıl oluşturulabildiğini ve yönteminin nasıl kullanılacağını `Format` gösterir.

[!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CMFCAcceleratorKey`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxacceleratorkey.h

## <a name="cmfcacceleratorkeycmfcacceleratorkey"></a><a name="cmfcacceleratorkey"></a>CMFCAcceleratorKey::CMFCAcceleratorKey

[CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) nesnesi oluşturuyor.

```
CMFCAcceleratorKey();
CMFCAcceleratorKey(LPACCEL lpAccel);
```

### <a name="parameters"></a>Parametreler

*lpAccel*<br/>
[içinde] Kısayol anahtarıiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCAccleratorKey`kısayol tuşu oluştururken bir kısayol tuşu sağlamazsanız, [CMFCAcceleratorKey kullanın::Bir](#setaccelerator) `CMFCAcceleratorKey` kısayol tuşu nesnenizle ilişkilendirmek için SetAccelerator yöntemini kullanın.

## <a name="cmfcacceleratorkeyformat"></a><a name="format"></a>CMFCAcceleratorKey::Biçim

ACCEL yapısını ilişkili dize değerine çevirir.

```
void Format(CString& str) const;
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
[çıkış] Yöntemin çevrilmiş kısayol anahtarını yazdığı bir `CString` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ilişkili kısayol anahtarının dize biçimini alır. [CmFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) nesnesinin dize biçimini oluşturucu yu veya [CMFCAcceleratorKey](#setaccelerator)yöntemini kullanarak ayarlayabilirsiniz:SetAccelerator .

## <a name="cmfcacceleratorkeysetaccelerator"></a><a name="setaccelerator"></a>CMFCAcceleratorKey::SetAccelerator

[CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) nesnesi için kısayol anahtarını ayarlar.

```
void SetAccelerator(LPACCEL lpAccel);
```

### <a name="parameters"></a>Parametreler

*lpAccel*<br/>
[içinde] Kısayol anahtarıiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Oluşturduğunuzda bir kısayol tuşu `CMFCAcceleratorKey` sağlamadıysanız kısayol anahtarını ayarlamak `CMFCAcceleratorKey`için bu yöntemi kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager Sınıfı](../../mfc/reference/ckeyboardmanager-class.md)
