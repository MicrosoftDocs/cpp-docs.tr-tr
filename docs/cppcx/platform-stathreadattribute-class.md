---
description: 'Daha fazla bilgi edinin: Platform:: STAThreadAttribute sınıfı'
title: 'Platform:: STAThreadAttribute sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
helpviewer_keywords:
- Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
ms.openlocfilehash: a1c235ef9a171e650c960df184b081c4b6511cf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308009"
---
# <a name="platformstathreadattribute-class"></a>Platform:: STAThreadAttribute sınıfı

Bir uygulamanın iş parçacığı modelinin tek iş parçacıklı Apartment (STA) olduğunu gösterir.

## <a name="syntax"></a>Syntax

```
public ref class STAThreadAttribute sealed : Attribute
```

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[STAThreadAttribute Oluşturucu 1](#ctor)|Sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

STAThreadAttribute özniteliği [Platform:: Object sınıfından](../cppcx/platform-object-class.md)devralınır. STAThreadAttribute Ayrıca aşağıdaki üyelere de aşırı yükler veya sahiptir:

|Ad|Açıklama|
|----------|-----------------|
|[STAThreadAttribute:: Equals](#equals)|Belirtilen nesnenin geçerli nesneye eşit olup olmadığını belirler.|
|[STAThreadAttribute:: GetHashCode](#gethashcode)|Bu örneğe ilişkin karma kodu döndürür.|
|[STAThreadAttribute:: ToString](#tostring)|Geçerli nesneyi temsil eden dizeyi döndürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Platform`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platformunun

## <a name="stathreadattribute-constructor"></a><a name="ctor"></a> STAThreadAttribute Oluşturucusu

STAThreadAttribute sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Syntax

```cpp
public:STAThreadAttribute();
```

## <a name="stathreadattributeequals"></a><a name="equals"></a> STAThreadAttribute:: Equals

Belirtilen nesnenin geçerli nesneye eşit olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
public:virtual override bool Equals( Object^ obj );
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
Karşılaştırma yapılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** nesneler eşitse; Aksi takdirde, **`false`** .

## <a name="stathreadattributegethashcode"></a><a name="gethashcode"></a> STAThreadAttribute:: GetHashCode

Bu örneğe ilişkin karma kodu döndürür.

### <a name="syntax"></a>Syntax

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Dönüş Değeri

Bu örneğin karma kodu.

## <a name="stathreadattributetostring"></a><a name="tostring"></a> STAThreadAttribute:: ToString

Geçerli nesneyi temsil eden dizeyi döndürür.

### <a name="syntax"></a>Syntax

```cpp
public:String^ ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneyi temsil eden dize.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)
