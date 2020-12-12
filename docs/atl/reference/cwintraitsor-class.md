---
description: 'Daha fazla bilgi edinin: CWinTraitsOR Class'
title: CWinTraitsOR sınıfı
ms.date: 11/04/2016
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
ms.openlocfilehash: 1d0a7ff8a78ebbdc416bdace2a1ea1f0199c292f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140068"
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR sınıfı

Bu sınıf, bir pencere nesnesi oluştururken kullanılan stilleri standartlaştırarak bir yöntem sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0,
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```

#### <a name="parameters"></a>Parametreler

*t_dwStyle*<br/>
Varsayılan pencere stilleri.

*t_dwExStyle*<br/>
Varsayılan genişletilmiş pencere stilleri.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinTraitsOR:: GetWndExStyle](#getwndexstyle)|Nesnenin genişletilmiş stillerini alır `CWinTraitsOR` .|
|[CWinTraitsOR:: GetWndStyle](#getwndstyle)|Nesnenin standart stillerini alır `CWinTraitsOR` .|

## <a name="remarks"></a>Açıklamalar

Bu [pencere nitelikleri](../../atl/understanding-window-traits.md) sınıfı, atl pencere nesnesi oluşturmak için kullanılan stilleri standartlaştırarak basit bir yöntem sağlar. Bu pencere sınıfının örnekleri için kullanılacak minimum ve genişletilmiş stiller kümesini belirtmek için [CWindowImpl](../../atl/reference/cwindowimpl-class.md) için bir şablon parametresi olarak bu sınıfın bir ÖZELLEŞTIRMESI veya atl pencere sınıflarının başka bir görünümünü kullanın.

Diğer stillerin [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create)çağrısında örnek temelinde ayarlanmaya izin verildiğinden, bu şablonun bir özelleştirmesinin tüm pencere sınıfı örnekleri için ayarlanmış olduğundan emin olmak istiyorsanız bu şablonu özelleştirme kullanın.

Yalnızca çağrıda başka bir stil belirtilmediğinde kullanılacak varsayılan pencere stilleri sağlamak istiyorsanız `CWindowImpl::Create` , bunun yerine [CWinTraits](../../atl/reference/cwintraits-class.md) kullanın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="cwintraitsorgetwndstyle"></a><a name="getwndstyle"></a> CWinTraitsOR:: GetWndStyle

Nesnenin standart stillerinin `CWinTraits` ve *t_dwStyle* tarafından belirtilen varsayılan stillerin BIRLEŞIMINI (mantıksal veya işlecini kullanarak) almak için bu işlevi çağırın.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Pencere oluşturmak için kullanılan stiller.

### <a name="return-value"></a>Dönüş Değeri

*DwStyle* 'a geçirilen stillerin `t_dwStyle` , mantıksal or işleci kullanılarak tarafından belirtilen varsayılan değerler birleşimi.

## <a name="cwintraitsorgetwndexstyle"></a><a name="getwndexstyle"></a> CWinTraitsOR:: GetWndExStyle

Nesnenin genişletilmiş stillerinin `CWinTraits` ve tarafından belirtilen varsayılan stillerin birleşimini (MANTıKSAL veya işlecini kullanarak) almak için bu işlevi çağırın `t_dwStyle` .

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Pencerenin oluşturulması için kullanılan genişletilmiş stiller.

### <a name="return-value"></a>Dönüş Değeri

*DwExStyle* içinde geçirilen genişletilmiş stillerin ve `t_dwExStyle` mantıksal or işleci kullanılarak tarafından belirtilen varsayılan bir birleşimi

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Pencere niteliklerini anlama](../../atl/understanding-window-traits.md)
