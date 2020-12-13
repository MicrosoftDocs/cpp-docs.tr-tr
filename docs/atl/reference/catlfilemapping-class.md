---
description: 'Daha fazla bilgi edinin: CAtlFileMapping sınıfı'
title: CAtlFileMapping sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: 875979d47ad4cb5b9c59047eff1f50acd35d1251
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147426"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping sınıfı

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

|Ad|Açıklama|
|----------|-----------------|
|[CAtlFileMapping:: operator T *](#operator_t_star)|Nesnelerin örtülü dönüştürmelerine izin verir `CAtlFileMapping` `T*` .|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, nesnelerin örtük dönüştürülmesine izin vermek için tek bir cast işleci ekler `CAtlFileMapping` `T*` . Diğer Üyeler, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)temel sınıfı tarafından sağlanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlfile. h

## <a name="catlfilemappingoperator-t"></a><a name="operator_t_star"></a> CAtlFileMapping:: operator T *

Nesnelerin örtülü dönüştürmelerine izin verir `CAtlFileMapping` `T*` .

```cpp
operator T*() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`T*`Bellek eşlemeli dosyanın başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlFileMappingBase:: GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) çağırır ve döndürülen işaretçiyi, `T*` Bu sınıfın şablon parametresi olarak kullanılan tür *T* olarak yeniden yorumlar.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlFileMappingBase sınıfı](../../atl/reference/catlfilemappingbase-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
