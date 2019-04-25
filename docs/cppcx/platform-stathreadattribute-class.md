---
title: Platform::STAThreadAttribute sınıfı
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
ms.openlocfilehash: 05fb2879839c504f49f56e25ffe28329aa969c69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183389"
---
# <a name="platformstathreadattribute-class"></a>Platform::STAThreadAttribute sınıfı

Bir uygulama için iş parçacığı modeli tek iş parçacıklı grup (STA) olduğunu gösterir.

## <a name="syntax"></a>Sözdizimi

```
public ref class STAThreadAttribute sealed : Attribute
```

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[STAThreadAttribute Oluşturucusu 1](#ctor)|Sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

STAThreadAttribute özniteliğini devraldığı [Platform::Object sınıfı](../cppcx/platform-object-class.md). STAThreadAttribute aşırı veya aşağıdaki üyeleri içerir:

|Ad|Açıklama|
|----------|-----------------|
|[STAThreadAttribute::Equals](#equals)|Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.|
|[STAThreadAttribute::GetHashCode](#gethashcode)|Bu örneğin karma kodunu döndürür.|
|[STAThreadAttribute::ToString](#tostring)|Geçerli nesneyi temsil eden bir dize döndürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Platform`

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Platform

## <a name="ctor"></a> STAThreadAttribute Oluşturucusu

STAThreadAttribute sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
public:STAThreadAttribute();
```

## <a name="equals"></a> STAThreadAttribute::Equals

Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
public:virtual override bool Equals( Object^ obj );
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
Karşılaştırma yapılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneler eşit; Aksi takdirde, **false**.

## <a name="gethashcode"></a> STAThreadAttribute::GetHashCode

Bu örneğin karma kodunu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Dönüş Değeri

Bu örneğin karma kodu.

## <a name="tostring"></a> STAThreadAttribute::ToString

Geçerli nesneyi temsil eden bir dize döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
public:String^ ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneyi temsil eden bir dize.

## <a name="see-also"></a>Ayrıca bkz.

[Platform Namespace](platform-namespace-c-cx.md)
