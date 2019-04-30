---
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
ms.openlocfilehash: 6a99ad00a43ac7912320ee469d542b6bf9cca3de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403964"
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey sınıfı

Sanal tuş eşlemeyi ve biçimlendirmeyi uygulayan yardımcı sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CMFCAcceleratorKey : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Oluşturur bir `CMFCAcceleratorKey` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAcceleratorKey::Format](#format)|HIZLANDIRMA yapısına visual gösterimine çevirir.|
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|Kısayol tuşu ayarlar `CMFCAcceleratorKey` nesne.|

## <a name="remarks"></a>Açıklamalar

Hızlandırıcı tuşları kısayol tuşlarını da verilir. Kullanıcının girdiği, klavye kısayollarını görüntülemek istiyorsanız [CMFCAcceleratorKeyAssignCtrl sınıfı](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) haritalar klavye kısayolları, Alt + Shift + S gibi "Alt + Shift + S" gibi bir özel metin biçimine. Her `CMFCAcceleratorKey` nesne için bir metin biçimi tek bir kısayol tuşuna eşler.

Kısayol tuşları ve Hızlandırıcı tablolarını kullanma hakkında daha fazla bilgi için bkz. [CKeyboardManager sınıfı](../../mfc/reference/ckeyboardmanager-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCAcceleratorKey` nesne ve nasıl kullanılacağını kendi `Format` yöntemi.

[!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAcceleratorKey`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxacceleratorkey.h

##  <a name="cmfcacceleratorkey"></a>  CMFCAcceleratorKey::CMFCAcceleratorKey

Oluşturur bir [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) nesne.

```
CMFCAcceleratorKey();
CMFCAcceleratorKey(LPACCEL lpAccel);
```

### <a name="parameters"></a>Parametreler

*lpAccel*<br/>
[in] Bir kısayol tuşu işaretçisi.

### <a name="remarks"></a>Açıklamalar

Oluşturduğunuzda, bir kısayol tuşu sağlamaz, bir `CMFCAccleratorKey`, kullanın [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) bir kısayol tuşu ile ilişkilendirilecek yöntemi, `CMFCAcceleratorKey` nesne.

##  <a name="format"></a>  CMFCAcceleratorKey::Format

HIZLANDIRMA yapısı ilişkili dize değerine çevirir.

```
void Format(CString& str) const;
```

### <a name="parameters"></a>Parametreler

*str*<br/>
[out] Bir başvuru bir `CString` yöntemi çevrilmiş kısayol tuşunu nereye yazdığını nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ilişkili bir kısayol tuşu dize biçimi alır. Dize biçimi ayarlayabileceğiniz bir [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) oluşturucu veya yöntemini kullanarak nesne [CMFCAcceleratorKey::SetAccelerator](#setaccelerator).

##  <a name="setaccelerator"></a>  CMFCAcceleratorKey::SetAccelerator

Kısayol tuşu ayarlar [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) nesne.

```
void SetAccelerator(LPACCEL lpAccel);
```

### <a name="parameters"></a>Parametreler

*lpAccel*<br/>
[in] Bir kısayol tuşu işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem için kısayol tuşu ayarlamak için kullanmak bir `CMFCAcceleratorKey` oluşturduğunuz zaman, bir kısayol tuşu sağlamadıysanız `CMFCAcceleratorKey`.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager Sınıfı](../../mfc/reference/ckeyboardmanager-class.md)
