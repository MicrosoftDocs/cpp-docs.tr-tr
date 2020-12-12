---
description: 'Daha fazla bilgi edinin: CWinTraits Class'
title: CWinTraits sınıfı
ms.date: 11/04/2016
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
ms.openlocfilehash: 3f23342cae58d70a602ebce1dcbe7efcddf36781
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140094"
---
# <a name="cwintraits-class"></a>CWinTraits sınıfı

Bu sınıf, bir pencere nesnesi oluştururken kullanılan stilleri standartlaştırarak bir yöntem sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```

#### <a name="parameters"></a>Parametreler

*t_dwStyle*<br/>
Varsayılan standart pencere stilleri.

*t_dwExStyle*<br/>
Varsayılan genişletilmiş pencere stilleri.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinTraits:: GetWndExStyle](#getwndexstyle)|Se Nesnenin genişletilmiş stillerini alır `CWinTraits` .|
|[CWinTraits:: GetWndStyle](#getwndstyle)|Se Nesnenin standart stillerini alır `CWinTraits` .|

## <a name="remarks"></a>Açıklamalar

Bu [pencere nitelikleri](../../atl/understanding-window-traits.md) sınıfı, atl pencere nesnesi oluşturmak için kullanılan stilleri standartlaştırarak basit bir yöntem sağlar. Bu pencere sınıfının örnekleri için kullanılan varsayılan standart ve Genişletilmiş stilleri belirtmek için [CWindowImpl](../../atl/reference/cwindowimpl-class.md) için bir şablon parametresi olarak bu sınıfın bir ÖZELLEŞTIRMESI veya atl pencere sınıflarının başka bir görünümünü kullanın.

Yalnızca [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create)çağrısında başka hiçbir stil belirtilmediğinde kullanılacak varsayılan pencere stilleri sağlamak istediğinizde bu şablonu kullanın.

ATL, pencere stillerinin yaygın olarak kullanılan birleşimleri için bu şablonun önceden tanımlanmış üç uzmanlığını sağlar:

- `CControlWinTraits`

   Standart denetim penceresi için tasarlanmıştır. Aşağıdaki standart Stiller kullanılır: WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN ve WS_CLIPSIBLINGS. Genişletilmiş Stil yok.

- `CFrameWinTraits`

   Standart çerçeve penceresi için tasarlanmıştır. Kullanılan standart stiller şunlardır: WS_OVERLAPPEDWINDOW, WS_CLIPCHILDREN ve WS_CLIPSIBLINGS. Kullanılan genişletilmiş stiller şunlardır: WS_EX_APPWINDOW ve WS_EX_WINDOWEDGE.

- `CMDIChildWinTraits`

   Standart bir MDI alt penceresi için tasarlanmıştır. Kullanılan standart stiller şunlardır: WS_OVERLAPPEDWINDOW, WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN ve WS_CLIPSIBLINGS. Kullanılan genişletilmiş stiller şunları içerir: WS_EX_MDICHILD.

Diğer stillerin örnek temelinde ayarlanmaya izin sağlarken, tüm pencere sınıfı örnekleri için belirli stillerin ayarlandığından emin olmak istiyorsanız, bunun yerine [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) kullanın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="cwintraitsgetwndstyle"></a><a name="getwndstyle"></a> CWinTraits:: GetWndStyle

Nesnenin standart stillerini almak için bu işlevi çağırın `CWinTraits` .

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Pencere oluşturmak için kullanılan standart stiller. *DwStyle* 0 ise, şablon stil değerleri ( `t_dwStyle` ) döndürülür. *DwStyle* sıfır değilse, *dwStyle* döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin standart pencere stilleri.

## <a name="cwintraitsgetwndexstyle"></a><a name="getwndexstyle"></a> CWinTraits:: GetWndExStyle

Nesnenin genişletilmiş stillerini almak için bu işlevi çağırın `CWinTraits` .

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Pencerenin oluşturulması için kullanılan genişletilmiş stiller. *DwExStyle* 0 ise, şablon stil değerleri ( `t_dwExStyle` ) döndürülür. *DwExStyle* sıfırdan farklı olursa *dwExStyle* döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin genişletilmiş pencere stilleri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Pencere niteliklerini anlama](../../atl/understanding-window-traits.md)
