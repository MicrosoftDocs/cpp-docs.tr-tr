---
title: CreatorMap Yapısı
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
- module/Microsoft::WRL::Details::CreatorMap::activationId
- module/Microsoft::WRL::Details::CreatorMap::factoryCache
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
- module/Microsoft::WRL::Details::CreatorMap::serverName
helpviewer_keywords:
- Microsoft::WRL::Details::CreatorMap structure
- Microsoft::WRL::Details::CreatorMap::activationId data member
- Microsoft::WRL::Details::CreatorMap::factoryCache data member
- Microsoft::WRL::Details::CreatorMap::factoryCreator data member
- Microsoft::WRL::Details::CreatorMap::serverName data member
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
ms.openlocfilehash: 1527f81694d1d809d585f3f6504c0e6433a2c26b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372609"
---
# <a name="creatormap-structure"></a>CreatorMap Yapısı

Windows Runtime C++ Şablon Kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>Açıklamalar

Nesneleri başlatma, kaydetme ve kayıt dışı etme hakkında bilgiler içerir.

`CreatorMap`aşağıdaki bilgileri içerir:

- Nesneleri başlatma, kaydetme ve kayıt dışı etme.

- Klasik bir COM veya Windows Runtime fabrikasına bağlı olarak etkinleştirme verilerini karşılaştırma.

- Bir arabirim için fabrika önbelleği ve sunucu adı hakkında bilgi.

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Adı                                          | Açıklama
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[CreatorMap::activationId](#activationid)     | Klasik bir COM sınıf kimliği veya Windows Runtime adı ile tanımlanan bir nesne kimliğini temsil eder.
[CreatorMap::factoryÖnbellek](#factorycache)     | İşaretçiyi fabrika önbelleğine `CreatorMap`saklar.
[CreatorMap::factoryCreator](#factorycreator) | Belirtilen `CreatorMap`ler için bir fabrika oluşturur.
[CreatorMap::serverName](#servername)         | Sunucu adını `CreatorMap`depolar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CreatorMap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** module.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="creatormapactivationid"></a><a name="activationid"></a>CreatorMap::activationId

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
Arayüz kimliği.

*getRuntimeName*<br/>
Bir nesnenin Windows çalışma zamanı adını alan bir işlev.

### <a name="remarks"></a>Açıklamalar

Klasik bir COM sınıf kimliği veya Windows çalışma zamanı adı ile tanımlanan bir nesne kimliğini temsil eder.

## <a name="creatormapfactorycache"></a><a name="factorycache"></a>CreatorMap::factoryÖnbellek

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>Açıklamalar

İşaretçiyi fabrika önbelleğine `CreatorMap`saklar.

## <a name="creatormapfactorycreator"></a><a name="factorycreator"></a>CreatorMap::factoryCreator

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>Parametreler

*akım bayrakları*<br/>
[RuntimeClassType](runtimeclasstype-enumeration.md) sayıcılardan biri.

*Giriş*<br/>
Bir CreatorMap.

*iidClassFactory*<br/>
Sınıf bir fabrikanın arayüz kimliği.

*Fabrika*<br/>
İşlem tamamlandığında, sınıf fabrikasının adresi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen CreatorMap için bir fabrika oluşturur.

## <a name="creatormapservername"></a><a name="servername"></a>CreatorMap::serverName

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>Açıklamalar

CreatorMap için sunucu adını depolar.
