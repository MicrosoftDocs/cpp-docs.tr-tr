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
ms.openlocfilehash: b43d5bb2f553d298584ab2ae497c22637d3beb0d
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54334963"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper Sınıfı

Windows çalışma zamanı'nı başlatır.

## <a name="syntax"></a>Sözdizimi

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>Açıklamalar

`RoInitializeWrapper` Windows çalışma zamanı başlatır ve işlemin başarılı olup olmadığını belirten bir HRESULT döndüren bir kolaylık bir özelliktir. Sınıf yok edicisini çağırır çünkü `::Windows::Foundation::Uninitialize`, örneklerini `RoInitializeWrapper` genel veya üst düzey kapsamda bildirilmelidir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                                    | Açıklama
----------------------------------------------------------------------- | -----------------------------------------------------------------
[Roınitializewrapper::roınitializewrapper](#roinitializewrapper)        | Yeni bir örneğini başlatır `RoInitializeWrapper` sınıfı.
[Roınitializewrapper:: ~ Roınitializewrapper](#tilde-roinitializewrapper) | Geçerli örneğini yok eder `RoInitializeWrapper` sınıfı.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                       | Açıklama
------------------------------------------ | ------------------------------------------------------------------------
[Roınitializewrapper:: HRESULT()](#hresult) | Tarafından üretilen HRESULT alır `RoInitializeWrapper` Oluşturucusu.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RoInitializeWrapper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="hresult"></a>Roınitializewrapper:: HRESULT()

HRESULT değerini son tarafından üretilen alır `RoInitializeWrapper` Oluşturucusu.

```cpp
operator HRESULT()
```

## <a name="roinitializewrapper"></a>Roınitializewrapper::roınitializewrapper

Yeni bir örneğini başlatır `RoInitializeWrapper` sınıfı.

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>Parametreler

*bayrakları*<br/>
Windows çalışma zamanı tarafından sağlanan desteğin belirtir RO_INIT_TYPE numaralandırmalardan biri.

### <a name="remarks"></a>Açıklamalar

`RoInitializeWrapper` Sınıfı çağırır `Windows::Foundation::Initialize(flags)`.

## <a name="tilde-roinitializewrapper"></a>Roınitializewrapper:: ~ Roınitializewrapper

Windows çalışma zamanının başlamasını iptal eder.

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>Açıklamalar

`RoInitializeWrapper` Sınıfı çağırır `Windows::Foundation::Uninitialize()`.
