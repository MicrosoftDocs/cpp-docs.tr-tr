---
description: 'Daha fazla bilgi edinin: RoInitializeWrapper sınıfı'
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
ms.openlocfilehash: b7f2c49bd461f08ad732680f1a02968ee7717116
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319306"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper Sınıfı

Windows Çalışma Zamanı başlatır.

## <a name="syntax"></a>Syntax

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>Açıklamalar

`RoInitializeWrapper` , Windows Çalışma Zamanı başlatan ve işlemin başarılı olup olmadığını gösteren bir HRESULT döndüren bir kolaydır. Sınıf yok edicisi çağırdığı için `::Windows::Foundation::Uninitialize` , örneklerinin `RoInitializeWrapper` genel veya üst düzey kapsamda bildirilmesine gerekir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                                    | Açıklama
----------------------------------------------------------------------- | -----------------------------------------------------------------
[RoInitializeWrapper:: RoInitializeWrapper](#roinitializewrapper)        | `RoInitializeWrapper` sınıfının yeni bir örneğini başlatır.
[RoInitializeWrapper:: ~ RoInitializeWrapper](#tilde-roinitializewrapper) | Sınıfın geçerli örneğini yok eder `RoInitializeWrapper` .

### <a name="public-operators"></a>Ortak İşleçler

Ad                                       | Açıklama
------------------------------------------ | ------------------------------------------------------------------------
[RoInitializeWrapper:: HRESULT ()](#hresult) | Oluşturucu tarafından üretilen HRESULT 'yi alır `RoInitializeWrapper` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RoInitializeWrapper`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="roinitializewrapperhresult"></a><a name="hresult"></a> RoInitializeWrapper:: HRESULT ()

Son Oluşturucu tarafından üretilen HRESULT değerini alır `RoInitializeWrapper` .

```cpp
operator HRESULT()
```

## <a name="roinitializewrapperroinitializewrapper"></a><a name="roinitializewrapper"></a> RoInitializeWrapper:: RoInitializeWrapper

`RoInitializeWrapper` sınıfının yeni bir örneğini başlatır.

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>Parametreler

*bayraklar*<br/>
Windows Çalışma Zamanı tarafından sunulan desteği belirten RO_INIT_TYPE Numaralandırmalardan biri.

### <a name="remarks"></a>Açıklamalar

`RoInitializeWrapper`Sınıfı çağırılır `Windows::Foundation::Initialize(flags)` .

## <a name="roinitializewrapperroinitializewrapper"></a><a name="tilde-roinitializewrapper"></a> RoInitializeWrapper:: ~ RoInitializeWrapper

Windows Çalışma Zamanı başlatır.

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>Açıklamalar

`RoInitializeWrapper`Sınıfı çağırılır `Windows::Foundation::Uninitialize()` .
