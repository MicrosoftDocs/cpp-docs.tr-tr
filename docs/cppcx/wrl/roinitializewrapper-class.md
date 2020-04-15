---
title: RoInitializeWrapper Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::HRESULT
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
helpviewer_keywords:
- Microsoft::WRL::Wrappers::RoInitializeWrapper class
- Microsoft::WRL::Wrappers::RoInitializeWrapper::operator HRESULT operator
- Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper, constructor
- Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper, destructor
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
ms.openlocfilehash: eba9162f17b98d13a9caf956b4f110b89dd81c37
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371239"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper Sınıfı

Windows Runtime'ı başharfe adaytır.

## <a name="syntax"></a>Sözdizimi

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>Açıklamalar

`RoInitializeWrapper`Windows Runtime'ı başlatılan ve işlemin başarılı olup olmadığını gösteren bir HRESULT döndüren bir kolaylıktır. Sınıf yıkıcı çağrıları `::Windows::Foundation::Uninitialize`olduğundan, örnekleri genel `RoInitializeWrapper` veya üst düzey kapsamda bildirilmelidir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                                                    | Açıklama
----------------------------------------------------------------------- | -----------------------------------------------------------------
[RoInitialize Wrapper::RoInitializeWrapper](#roinitializewrapper)        | `RoInitializeWrapper` sınıfının yeni bir örneğini başlatır.
[RoInitialize Wrapper::~RoInitializeWrapper](#tilde-roinitializewrapper) | Sınıfın geçerli örneğini `RoInitializeWrapper` yok eder.

### <a name="public-operators"></a>Ortak İşleçler

Adı                                       | Açıklama
------------------------------------------ | ------------------------------------------------------------------------
[RoInitialize Sarılayıcı::HRESULT()](#hresult) | Oluşturucu tarafından üretilen HRESULT'ı `RoInitializeWrapper` alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RoInitializeWrapper`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar

## <a name="roinitializewrapperhresult"></a><a name="hresult"></a>RoInitialize Sarılayıcı::HRESULT()

Son `RoInitializeWrapper` oluşturucu tarafından üretilen HRESULT değerini alır.

```cpp
operator HRESULT()
```

## <a name="roinitializewrapperroinitializewrapper"></a><a name="roinitializewrapper"></a>RoInitialize Wrapper::RoInitializeWrapper

`RoInitializeWrapper` sınıfının yeni bir örneğini başlatır.

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>Parametreler

*bayraklar*<br/>
Windows Runtime tarafından sağlanan desteği belirten RO_INIT_TYPE sayılardan biri.

### <a name="remarks"></a>Açıklamalar

Sınıf `RoInitializeWrapper` `Windows::Foundation::Initialize(flags)`çağırır.

## <a name="roinitializewrapperroinitializewrapper"></a><a name="tilde-roinitializewrapper"></a>RoInitialize Wrapper::~RoInitializeWrapper

Windows Runtime'ı başlatmayı uninitialize eder.

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>Açıklamalar

Sınıf `RoInitializeWrapper` `Windows::Foundation::Uninitialize()`çağırır.
