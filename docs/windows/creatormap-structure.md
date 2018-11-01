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
ms.openlocfilehash: 98afce8096ee514fc8576bb80074b73acdd658e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582458"
---
# <a name="creatormap-structure"></a>CreatorMap Yapısı

Windows çalışma zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>Açıklamalar

Nesneleri kaydını başlatmak ve kaydetme hakkında bilgi içerir.

`CreatorMap` Aşağıdaki bilgileri içerir:

- Başlatma, kaydedin ve nesneleri kaydını nasıl.

- Klasik COM ya da Windows çalışma zamanı fabrikası bağlı olarak etkinleştirme verileri karşılaştırma yapma.

- Bir arabirim üreteci önbellek ve sunucu adı hakkında bilgi.

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Ad                                          | Açıklama
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[Creatormap::activationıd](#activationid)     | Bir klasik COM sınıfı kimliği veya bir Windows çalışma zamanı adı tanımlanmış bir nesne kimliği temsil eder.
[CreatorMap::factoryCache](#factorycache)     | Üreteci önbellek için yönelik bir işaretçi depolayan `CreatorMap`.
[CreatorMap::factoryCreator](#factorycreator) | İçin belirtilen bir Üreteç oluşturur `CreatorMap`.
[CreatorMap::serverName](#servername)         | Sunucu adını depolar `CreatorMap`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CreatorMap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::wrl:: details

## <a name="activationid"></a>Creatormap::activationıd

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>Parametreler

*CLSID*<br/>
Bir arabirim kimliği.

*getRuntimeName*<br/>
Windows çalışma zamanı adı bir nesne alır. bir işlev.

### <a name="remarks"></a>Açıklamalar

Bir klasik COM sınıfı kimliği veya bir Windows çalışma zamanı adı tanımlanmış bir nesne kimliği temsil eder.

## <a name="factorycache"></a>CreatorMap::factoryCache

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>Açıklamalar

Üreteci önbellek için yönelik bir işaretçi depolayan `CreatorMap`.

## <a name="factorycreator"></a>CreatorMap::factoryCreator

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>Parametreler

*currentflags*<br/>
Aşağıdakilerden birini [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırıcılar.

*entry*<br/>
CreatorMap bir.

*iidClassFactory*<br/>
Bir sınıf üreteci arabirim kimliği.

*Fabrika*<br/>
İşlem tamamlandığında bir sınıf üreteci adresidir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Belirtilen CreatorMap için bir üreteci oluşturur.

## <a name="servername"></a>CreatorMap::serverName

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>Açıklamalar

CreatorMap için sunucu adını depolar.
