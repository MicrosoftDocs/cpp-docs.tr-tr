---
description: 'Daha fazla bilgi edinin: CreatorMap yapısı'
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
ms.openlocfilehash: 0ef3b441390a22a6c4b35f274857ccb58de030d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273052"
---
# <a name="creatormap-structure"></a>CreatorMap Yapısı

Windows Çalışma Zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Syntax

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>Açıklamalar

Nesneleri başlatma, kaydetme ve kaydını silme hakkında bilgiler içerir.

`CreatorMap` Aşağıdaki bilgileri içerir:

- Nesneleri başlatma, kaydetme ve kaydını silme.

- Klasik bir COM veya Windows Çalışma Zamanı fabrikasına bağlı olarak etkinleştirme verilerini karşılaştırma.

- Bir arabirimin fabrika önbelleği ve sunucu adı hakkında bilgiler.

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

Ad                                          | Açıklama
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[CreatorMap:: activationId](#activationid)     | Klasik bir COM sınıf KIMLIĞI veya Windows Çalışma Zamanı adı tarafından tanımlanan bir nesne KIMLIĞINI temsil eder.
[CreatorMap:: factoryCache](#factorycache)     | İçin işaretçiyi fabrika önbelleğine depolar `CreatorMap` .
[CreatorMap:: factoryCreator](#factorycreator) | Belirtilen için bir fabrika oluşturur `CreatorMap` .
[CreatorMap:: serverName](#servername)         | İçin sunucu adını depolar `CreatorMap` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CreatorMap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="creatormapactivationid"></a><a name="activationid"></a> CreatorMap:: activationId

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>Parametreler

*in*<br/>
Arabirim KIMLIĞI.

*getRuntimeName*<br/>
Bir nesnenin Windows çalışma zamanı adını alan bir işlev.

### <a name="remarks"></a>Açıklamalar

Klasik bir COM sınıf KIMLIĞIYLE veya bir Windows çalışma zamanı adıyla tanımlanan bir nesne KIMLIĞINI temsil eder.

## <a name="creatormapfactorycache"></a><a name="factorycache"></a> CreatorMap:: factoryCache

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>Açıklamalar

İçin işaretçiyi fabrika önbelleğine depolar `CreatorMap` .

## <a name="creatormapfactorycreator"></a><a name="factorycreator"></a> CreatorMap:: factoryCreator

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
[RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırıcıdan biri.

*girişte*<br/>
Bir CreatorMap.

*ııdclassfactory*<br/>
Sınıf fabrikasının arabirim KIMLIĞI.

*Çar*<br/>
İşlem tamamlandığında, bir sınıf fabrikası adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen CreatorMap için bir fabrika oluşturur.

## <a name="creatormapservername"></a><a name="servername"></a> CreatorMap:: serverName

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>Açıklamalar

CreatorMap için sunucu adını depolar.
