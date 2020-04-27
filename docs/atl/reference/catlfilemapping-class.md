---
title: CAtlFileMapping Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: 7516349e4ec54d8cb90fa6ff23b0ded954aa043b
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168130"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping Sınıfı

Bu sınıf, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)yöntemlerine bir atama işleci ekleyerek, bellek eşlemeli bir dosyayı temsil eder.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Atama işleci için kullanılan veri türü.

## <a name="members"></a>Üyeler

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlFileMapping:: operator T *](#operator_t_star)|`CAtlFileMapping` Nesnelerin örtülü dönüştürmelerine izin verir `T*`.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, `CAtlFileMapping` nesnelerin örtük dönüştürülmesine izin vermek için tek bir cast işleci ekler `T*`. Diğer Üyeler, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)temel sınıfı tarafından sağlanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlfile. h

## <a name="catlfilemappingoperator-t"></a><a name="operator_t_star"></a>CAtlFileMapping:: operator T *

`CAtlFileMapping` Nesnelerin örtülü dönüştürmelerine izin verir `T*`.

```cpp
operator T*() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bellek eşlemeli `T*` dosyanın başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlFileMappingBase:: GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) çağırır ve döndürülen işaretçiyi, bu sınıfın şablon parametresi `T*` olarak kullanılan tür *T* olarak yeniden yorumlar.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlFileMappingBase Sınıfı](../../atl/reference/catlfilemappingbase-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
