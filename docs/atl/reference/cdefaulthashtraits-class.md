---
description: 'Daha fazla bilgi edinin: CDefaultHashTraits Class'
title: CDefaultHashTraits sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
ms.openlocfilehash: 85cc881466be03931d435d91a48548456d74305b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141888"
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits sınıfı

Bu sınıf, karma değerleri hesaplamak için statik bir işlev sağlar.

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

|Ad|Açıklama|
|----------|-----------------|
|[CDefaultHashTraits:: Hash](#hash)|Se Verilen bir öğe için bir karma değer hesaplamak üzere bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, belirli bir öğe için bir karma değer döndüren tek bir statik işlev içerir. Bu sınıf [Cdefaultelementnitelikler sınıfı](../../atl/reference/cdefaultelementtraits-class.md)tarafından kullanılır.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cdefaulthashtraitshash"></a><a name="hash"></a> CDefaultHashTraits:: Hash

Verilen bir öğe için bir karma değer hesaplamak üzere bu işlevi çağırın.

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>Parametreler

*dosyalarında*<br/>
Öğesi.

### <a name="return-value"></a>Dönüş Değeri

Karma değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan karma algoritması çok basittir: dönüş değeri öğe numarasıdır. Daha karmaşık bir algoritma gerekliyse, bu işlevi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
