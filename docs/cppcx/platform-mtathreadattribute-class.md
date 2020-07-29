---
title: 'Platform:: MTAThreadAttribute sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::MTAThreadAttribute::Equals
- VCCORLIB/Platform::MTAThreadAttribute::GetHashCode
- VCCORLIB/Platform::MTAThreadAttribute::ToString
helpviewer_keywords:
- Platform::MTAThreadAttribute Class
ms.assetid: bfc546a7-4333-4407-85b4-4721565e1f44
ms.openlocfilehash: 700eeae226be48c1f6659d621f2f5c0ed397bb7f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213053"
---
# <a name="platformmtathreadattribute-class"></a>Platform:: MTAThreadAttribute sınıfı

Bir uygulama için iş parçacığı modelinin çok iş parçacıklı apartman (MTA) olduğunu gösterir.

## <a name="syntax"></a>Sözdizimi

```
public ref class MTAThreadAttribute sealed : Attribute
```

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[MTAThreadAttribute Oluşturucu 1](#ctor) Oluşturucusu|Sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

MTAThreadAttribute özniteliği [Platform:: Object sınıfından](../cppcx/platform-object-class.md)devralınır. MTAThreadAttribute Ayrıca, aşağıdaki üyelere de aşırı yükler veya sahiptir:

|Ad|Açıklama|
|----------|-----------------|
|[MTAThreadAttribute:: Equals](#equals)|Belirtilen nesnenin geçerli nesneye eşit olup olmadığını belirler.|
|[MTAThreadAttribute:: GetHashCode](#gethashcode)|Bu örneğe ilişkin karma kodu döndürür.|
|[MTAThreadAttribute:: ToString](#tostring)|Geçerli nesneyi temsil eden dizeyi döndürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Platform`

### <a name="requirements"></a>Gereksinimler

**Meta veri:** platform. winmd

**Ad alanı:** Platformunun

## <a name="mtathreadattribute-constructor"></a><a name="ctor"></a>MTAThreadAttribute Oluşturucusu

MTAThreadAttribute sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
public:MTAThreadAttribute();
```

## <a name="mtathreadattributeequals"></a><a name="equals"></a>MTAThreadAttribute:: Equals

Belirtilen nesnenin geçerli nesneye eşit olup olmadığını belirler.

### <a name="syntax"></a>Söz dizimi

```cpp
public:virtual override bool Equals( Object^ obj );
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
Karşılaştırma yapılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** nesneler eşitse; Aksi takdirde, **`false`** .

## <a name="mtathreadattributegethashcode"></a><a name="gethashcode"></a>MTAThreadAttribute:: GetHashCode

Bu örneğe ilişkin karma kodu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Dönüş Değeri

Bu örneğin karma kodu.

## <a name="mtathreadattributetostring"></a><a name="tostring"></a>MTAThreadAttribute:: ToString

Geçerli nesneyi temsil eden dizeyi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
public:String^ ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneyi temsil eden dize.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)
