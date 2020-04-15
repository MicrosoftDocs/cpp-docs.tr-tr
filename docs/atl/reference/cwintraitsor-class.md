---
title: CWinTraitsOR Sınıfı
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
ms.openlocfilehash: 825f79190c6f68cd1372154e4e02f430f545aa48
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330280"
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR Sınıfı

Bu sınıf, bir pencere nesnesi oluştururken kullanılan stilleri standartlaştırmak için bir yöntem sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

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

|Adı|Açıklama|
|----------|-----------------|
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|`CWinTraitsOR` Nesne için genişletilmiş stilleri alır.|
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|Nesnenin standart stillerini `CWinTraitsOR` alır.|

## <a name="remarks"></a>Açıklamalar

Bu [pencere özellikleri](../../atl/understanding-window-traits.md) sınıfı, Bir ATL pencere nesnesinin oluşturulması için kullanılan stilleri standartlaştırmak için basit bir yöntem sağlar. Bu sınıfın uzmanlık alanını, söz ve pencere sınıfı örnekleri için kullanılacak minimum standart ve genişletilmiş stilleri belirtmek için [CWindowImpl'e](../../atl/reference/cwindowimpl-class.md) veya ATL'nin pencere sınıflarından başka birsına şablon parametresi olarak uzmanlık kullanın.

[CWindowImpl'e](../../atl/reference/cwindowimpl-class.md#create)yapılan çağrıda diğer stillerin her örnek te ayarlanmasına izin verirken, belirli stillerin pencere sınıfının tüm örnekleri için ayarlandığından emin olmak istiyorsanız bu şablonun özelleştirilmesini kullanın:Oluştur .

Yalnızca çağrıda başka stil belirtilmediğinde kullanılacak varsayılan pencere stilleri sağlamak `CWindowImpl::Create`istiyorsanız, bunun yerine [CWinTraits'ı](../../atl/reference/cwintraits-class.md) kullanın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="cwintraitsorgetwndstyle"></a><a name="getwndstyle"></a>CWinTraitsOR::GetWndStyle

`CWinTraits` Nesnenin standart stillerinin ve *t_dwStyle*tarafından belirtilen varsayılan stillerin bir birleşimini (mantıksal OR işleci kullanarak) almak için bu işlevi arayın.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Pencere oluşturmak için kullanılan stiller.

### <a name="return-value"></a>Dönüş Değeri

Mantıksal OR işleci kullanarak *dwStyle'da* geçirilen `t_dwStyle`stillerin ve belirtilen varsayılan stillerin birleşimi.

## <a name="cwintraitsorgetwndexstyle"></a><a name="getwndexstyle"></a>CWinTraitsOR::GetWndExStyle

`CWinTraits` Nesnenin genişletilmiş stillerinin ve varsayılan stillerin bir birleşimini (mantıksal OR işleci `t_dwStyle`kullanılarak) almak için bu işlevi arayın.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Pencere oluşturmak için kullanılan genişletilmiş stiller.

### <a name="return-value"></a>Dönüş Değeri

Mantıksal OR işleci kullanılarak *dwExStyle'da* geçirilen genişletilmiş `t_dwExStyle`stillerin ve

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Pencere Özelliklerini Anlama](../../atl/understanding-window-traits.md)
