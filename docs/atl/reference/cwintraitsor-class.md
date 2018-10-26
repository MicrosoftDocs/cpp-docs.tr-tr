---
title: CWinTraitsOR sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3883065d9d7222d5e9d98806f0baadf0bc209213
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072310"
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR sınıfı

Bu sınıf, bir pencere nesnesi oluşturulurken kullanılan stilleri Standartlaştırma için bir yöntem sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

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
Genişletilmiş pencere stilleri varsayılan olarak.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|Genişletilmiş stillerini alır `CWinTraitsOR` nesne.|
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|Standart stillerini alır `CWinTraitsOR` nesne.|

## <a name="remarks"></a>Açıklamalar

Bu [pencere özelliklerini](../../atl/understanding-window-traits.md) sınıfı bir ATL pencere nesnesi oluşturmak için kullanılan stilleri Standartlaştırma için basit bir yöntem sağlar. Bu sınıfın özelleştirmesi için bir şablon parametresi olarak kullanmak [Cwindowımpl](../../atl/reference/cwindowimpl-class.md) veya başka bir ATL pencere sınıfları için kullanılmak üzere standart ve genişletilmiş stiller en düşük kümesini belirtmek için bu pencere sınıfının örneği.

Belirli stilleri penceresi sınıfın tüm örnekleri için diğer stilleri erişimine izin verme çağrısında örnek başına temelinde ayarlamak için ayarlandığından emin olmak istiyorsanız bu şablonunun bir özelleştirmesi kullanın [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create).

Diğer bir stilleri çağrısında belirtildiğinde, kullanılacak pencere stilleri varsayılan sağlamak istiyorsanız `CWindowImpl::Create`, kullanın [CWinTraits](../../atl/reference/cwintraits-class.md) yerine.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

##  <a name="getwndstyle"></a>  CWinTraitsOR::GetWndStyle

Standart stillerini birleşimi (mantıksal veya işlecini kullanarak) almak için bu işlevi çağırın `CWinTraits` nesnesi ve tarafından belirtilen varsayılan stillerini *t_dwStyle*.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Bir pencere oluşturmak için kullanılan stilleri.

### <a name="return-value"></a>Dönüş Değeri

Geçirilir stilleri birleşimi *dwStyle* ve olanları belirtilen varsayılan `t_dwStyle`, mantıksal OR operatörü kullanılarak birleştirilmelidir.

##  <a name="getwndexstyle"></a>  CWinTraitsOR::GetWndExStyle

Genişletilmiş stillerini birleşimi (mantıksal veya işlecini kullanarak) almak için bu işlevi çağırın `CWinTraits` nesnesi ve tarafından belirtilen varsayılan stillerini `t_dwStyle`.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Bir pencere oluşturmak için kullanılan genişletilmiş stiller.

### <a name="return-value"></a>Dönüş Değeri

Geçirilir genişletilmiş stiller birleşimi *dwExStyle* ve tarafından belirtilen varsayılan `t_dwExStyle`, mantıksal OR işlecinin kullanma

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Pencere Özelliklerini Anlama](../../atl/understanding-window-traits.md)

