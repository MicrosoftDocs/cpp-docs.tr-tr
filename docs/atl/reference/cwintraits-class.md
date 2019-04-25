---
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
ms.openlocfilehash: 840433ffb325a4f181848371306607b62373e75a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276789"
---
# <a name="cwintraits-class"></a>CWinTraits sınıfı

Bu sınıf, bir pencere nesnesi oluşturulurken kullanılan stilleri Standartlaştırma için bir yöntem sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```

#### <a name="parameters"></a>Parametreler

*t_dwStyle*<br/>
Varsayılan standart pencere stilleri.

*t_dwExStyle*<br/>
Genişletilmiş pencere stilleri varsayılan olarak.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(Statik) Genişletilmiş stillerini alır `CWinTraits` nesne.|
|[CWinTraits::GetWndStyle](#getwndstyle)|(Statik) Standart stillerini alır `CWinTraits` nesne.|

## <a name="remarks"></a>Açıklamalar

Bu [pencere özelliklerini](../../atl/understanding-window-traits.md) sınıfı bir ATL pencere nesnesi oluşturmak için kullanılan stilleri Standartlaştırma için basit bir yöntem sağlar. Bu sınıfın özelleştirmesi için bir şablon parametresi olarak kullanmak [Cwindowımpl](../../atl/reference/cwindowimpl-class.md) veya başka bir ATL pencere sınıfları için kullanılan varsayılan standart ve genişletilmiş stiller belirtmek için bu pencere sınıfının örneği.

Diğer bir stilleri çağrısında belirtildiğinde, kullanılacak pencere stilleri varsayılan sağlamak istediğinizde bu şablonu kullanın [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).

ATL pencere stilleri yaygın olarak kullanılan birleşimleri için bu şablonun önceden tanımlanmış üç uzmanlıklar sağlar:

- `CControlWinTraits`

   Bir standart denetim penceresi için tasarlanmıştır. Aşağıdaki standart stilleri kullanılır: WS_CHILD, ws_vısıble, ws_clıpchıldren ve ws_clıpsıblıngs. Genişletilmiş Stil vardır.

- `CFrameWinTraits`

   Standart bir çerçeve için tasarlanmıştır. Kullanılan standart stiller şunlardır: Ws_overlappedwındow ws_clıpchıldren ve ws_clıpsıblıngs. Kullanılan genişletilmiş stiller şunlardır: Ws_ex_appwındow ve ws_ex_wındowedge.

- `CMDIChildWinTraits`

   Standart bir MDI alt penceresi için tasarlanmıştır. Kullanılan standart stiller şunlardır: Ws_overlappedwındow, WS_CHILD, ws_vısıble, ws_clıpchıldren ve ws_clıpsıblıngs. Kullanılan genişletilmiş stiller şunlardır: WS_EX_MDICHILD.

Tek başına örnek temelinde ayarlamak için diğer stilleri erişimine izin verme sırasında penceresi sınıfın tüm örnekleri kullanmak için belirli stilleri ayarlandığından emin olmak istiyorsanız [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) yerine.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

##  <a name="getwndstyle"></a>  CWinTraits::GetWndStyle

Standart stillerini almak için bu işlevi çağırın `CWinTraits` nesne.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Bir pencere oluşturmak için kullanılan standart stilleri. Varsa *dwStyle* şablon stili değerleri 0'dır (`t_dwStyle`) döndürülür. Varsa *dwStyle* sıfır değilse, *dwStyle* döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin standart pencere stilleri.

##  <a name="getwndexstyle"></a>  CWinTraits::GetWndExStyle

Genişletilmiş stillerini almak için bu işlevi çağırın `CWinTraits` nesne.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Bir pencere oluşturmak için kullanılan genişletilmiş stiller. Varsa *dwExStyle* şablon stili değerleri 0'dır (`t_dwExStyle`) döndürülür. Varsa *dwExStyle* sıfır değilse, *dwExStyle* döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Genişletilmiş pencere stilleri nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Pencere Özelliklerini Anlama](../../atl/understanding-window-traits.md)
