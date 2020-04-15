---
title: CDefaultHashTraits Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
ms.openlocfilehash: 43932092621d44cfc8b07270df92e2765665f23f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327080"
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits Sınıfı

Bu sınıf karma değerleri hesaplamak için statik bir işlev sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>
class CDefaultHashTraits
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDefaultHashTraits::Hash](#hash)|(Statik) Belirli bir öğe için karma değeri hesaplamak için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, belirli bir öğe için karma değer döndüren tek bir statik işlev içerir. Bu sınıf [CDefaultElementTraits Sınıfı](../../atl/reference/cdefaultelementtraits-class.md)tarafından kullanılır.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cdefaulthashtraitshash"></a><a name="hash"></a>CDefaultHashTraits::Hash

Belirli bir öğe için karma değeri hesaplamak için bu işlevi çağırın.

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>Parametreler

*Öğe*<br/>
Element.

### <a name="return-value"></a>Dönüş Değeri

Karma değeri verir.

### <a name="remarks"></a>Açıklamalar

Varsayılan karma algoritması çok basittir: döndürme değeri öğe numarasıdır. Daha karmaşık bir algoritma gerekiyorsa bu işlevi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
