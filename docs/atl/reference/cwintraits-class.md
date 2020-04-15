---
title: CWinTraits Sınıfı
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
ms.openlocfilehash: fd73f733e4eff21da92937d1e1b0cce21552a48c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330308"
---
# <a name="cwintraits-class"></a>CWinTraits Sınıfı

Bu sınıf, bir pencere nesnesi oluştururken kullanılan stilleri standartlaştırmak için bir yöntem sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

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

|Adı|Açıklama|
|----------|-----------------|
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(Statik) `CWinTraits` Nesne için genişletilmiş stilleri alır.|
|[CWinTraits::GetWndStyle](#getwndstyle)|(Statik) Nesnenin standart stillerini `CWinTraits` alır.|

## <a name="remarks"></a>Açıklamalar

Bu [pencere özellikleri](../../atl/understanding-window-traits.md) sınıfı, Bir ATL pencere nesnesinin oluşturulması için kullanılan stilleri standartlaştırmak için basit bir yöntem sağlar. Bu sınıfın uzmanlık alanını, bu pencere sınıfının örnekleri için kullanılan varsayılan standardı ve genişletilmiş stilleri belirtmek için [CWindowImpl'e](../../atl/reference/cwindowimpl-class.md) veya ATL'nin pencere sınıflarından başka birsına şablon parametresi olarak kullanın.

[CWindowImpl'e](../../atl/reference/cwindowimpl-class.md#create)yapılan çağrıda başka stil belirtilmediğinde kullanılacak varsayılan pencere stillerini sağlamak istediğinizde bu şablonu kullanın:Oluştur .

ATL, pencere stillerinin yaygın olarak kullanılan kombinasyonları için bu şablonun önceden tanımlanmış üç uzmanlık özelliğini sağlar:

- `CControlWinTraits`

   Standart bir kontrol penceresi için tasarlanmıştır. Aşağıdaki standart stiller kullanılır: WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN ve WS_CLIPSIBLINGS. Genişletilmiş stiller yoktur.

- `CFrameWinTraits`

   Standart çerçeve penceresi için tasarlanmıştır. Kullanılan standart stiller şunlardır: WS_OVERLAPPEDWINDOW, WS_CLIPCHILDREN ve WS_CLIPSIBLINGS. Kullanılan genişletilmiş stilleri şunlardır: WS_EX_APPWINDOW ve WS_EX_WINDOWEDGE.

- `CMDIChildWinTraits`

   Standart bir MDI alt penceresi için tasarlanmıştır. Kullanılan standart stiller şunlardır: WS_OVERLAPPEDWINDOW, WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN ve WS_CLIPSIBLINGS. Kullanılan genişletilmiş stilleri şunlardır: WS_EX_MDICHILD.

Diğer stillerin her örnek te ayarlanmasına izin verirken, pencere sınıfının tüm örnekleri için belirli stillerin ayarlandığından emin olmak istiyorsanız, bunun yerine [CWinTraitsOR'u](../../atl/reference/cwintraitsor-class.md) kullanın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="cwintraitsgetwndstyle"></a><a name="getwndstyle"></a>CWinTraits::GetWndStyle

`CWinTraits` Nesnenin standart stillerini almak için bu işlevi arayın.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Pencere oluşturmak için kullanılan standart stiller. *dwStyle* 0 ise, şablon stil`t_dwStyle`değerleri ( ) döndürülür. *dwStyle* sıfır değilse, *dwStyle* döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin standart pencere stilleri.

## <a name="cwintraitsgetwndexstyle"></a><a name="getwndexstyle"></a>CWinTraits::GetWndExStyle

Nesnenin genişletilmiş stillerini almak için `CWinTraits` bu işlevi çağırın.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Pencere oluşturmak için kullanılan genişletilmiş stiller. *dwExStyle* 0 ise, şablon stil`t_dwExStyle`değerleri ( ) döndürülür. *dwExStyle* sıfır değilse, *dwExStyle* döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin genişletilmiş pencere stilleri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Pencere Özelliklerini Anlama](../../atl/understanding-window-traits.md)
