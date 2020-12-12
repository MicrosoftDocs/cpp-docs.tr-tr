---
description: 'Daha fazla bilgi edinin: Platform:: Object Class'
title: 'Platform:: Object sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Object::Object
- VCCORLIB/Platform::Object::Equals
- VCCORLIB/Platform::Object::GetHashCode
- VCCORLIB/Platform::Object::ReferenceEquals
- VCCORLIB/Platform::ToString
- VCCORLIB/Platform::GetType
helpviewer_keywords:
- Object class
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
ms.openlocfilehash: a190d5a56bb27fb95ac2c2c8bd2ba0e0d0572427
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308256"
---
# <a name="platformobject-class"></a>Platform:: Object sınıfı

Windows Çalışma Zamanı uygulamalarında ref sınıfları ve başvuru yapıları için ortak davranış sağlar. Tüm ref sınıfı ve ref struct örnekleri, dolaylı olarak platform:: Object ^ türüne dönüştürülebilir ve sanal ToString metodunu geçersiz kılabilir.

## <a name="syntax"></a>Syntax

```cpp
public ref class Object : Object
```

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Object:: Object](#ctor)|Nesne sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Nesne:: Equals](#equals)|Belirtilen nesnenin geçerli nesneye eşit olup olmadığını belirler.|
|[Nesne:: GetHashCode](#gethashcode)|Bu örneğe ilişkin karma kodu döndürür.|
|[Nesne:: ReferenceEquals](#referenceequals)|Belirtilen nesne örneklerinin aynı örnek olup olmadığını belirler.|
|[Yönte](#tostring)|Geçerli nesneyi temsil eden dizeyi döndürür. Geçersiz kılınabilir.|
|[GetType](#gettype)|Geçerli örneği açıklayan bir [Platform:: Type](../cppcx/platform-type-class.md) alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Object`

`Object`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** vccorlib. h

**Ad alanı:** Platformunun

## <a name="objectequals-method"></a><a name="equals"></a> Object:: Equals yöntemi

Belirtilen nesnenin geçerli nesneye eşit olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool Equals(
    Object^ obj
)
```

### <a name="parameters"></a>Parametreler

*obj*<br/>
Karşılaştırma yapılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** nesneler eşitse, tersi durumda **`false`** .

## <a name="objectgethashcode-method"></a><a name="gethashcode"></a> Object:: GetHashCode yöntemi

`IUnknown`Bu örnek için BIR com nesnesi veya BIR com nesnesi değilse hesaplanan karma değeri olan * kimlik değerini döndürür.

### <a name="syntax"></a>Syntax

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesneyi benzersiz bir şekilde tanımlayan sayısal bir değer.

### <a name="remarks"></a>Açıklamalar

Eşlemlerdeki nesneler için anahtar oluşturmak üzere GetHashCode kullanabilirsiniz. Karma kodlarını, [nesne:: Equals](#equals)kullanarak karşılaştırabilirsiniz. Kod yolu son derece kritiktir ve `GetHashCode` `Equals` yeterince hızlı değilse, temel alınan com katmanına açılır ve yerel `IUnknown` işaretçi karşılaştırmaları yapabilirsiniz.

## <a name="objectgettype-method"></a><a name="gettype"></a> Object:: GetType yöntemi

Bir nesnenin çalışma zamanı türünü açıklayan bir [Platform:: Type](../cppcx/platform-type-class.md) nesnesi döndürür.

### <a name="syntax"></a>Syntax

```cpp
Object::GetType();
```

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Nesnenin çalışma zamanı türünü açıklayan bir [Platform:: Type](../cppcx/platform-type-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Statik [tür:: GetTypeCode](../cppcx/platform-type-class.md#gettypecode) , geçerli türü temsil eden bir [Platform:: TypeCode numaralandırma](../cppcx/platform-typecode-enumeration.md) değeri almak için kullanılabilir. Bu, çoğunlukla yerleşik türler için yararlıdır. [Platform:: String](../cppcx/platform-string-class.md) 'in yanı sıra herhangi bir ref sınıfı için tür kodu Object (1).

Windows [:: UI:: XAML:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename) sınıfı Windows API 'lerinde Windows bileşenleri ve uygulamalar arasında tür bilgilerini geçirmenin dilden bağımsız bir yolu olarak kullanılır. T[Platform:: Type sınıfında](../cppcx/platform-type-class.md) ve arasında dönüştürme işleçleri vardır `Type` `TypeName` .

Sınıf adı için bir nesne döndürmek için [TypeId](../extensions/typeid-cpp-component-extensions.md) işlecini kullanın `Platform::Type` , örneğin XAML sayfaları arasında gezinirken:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

## <a name="objectobject-constructor"></a><a name="ctor"></a> Object:: Object Oluşturucusu

Nesne sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Syntax

```cpp
public:Object();
```

## <a name="objectreferenceequals-method"></a><a name="referenceequals"></a> Object:: ReferenceEquals yöntemi

Belirtilen nesne örneklerinin aynı örnek olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2);
```

### <a name="parameters"></a>Parametreler

*obj1*<br/>
Karşılaştırma yapılacak ilk nesne.

*obj2*<br/>
Karşılaştırma yapılacak ikinci nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** iki nesne aynı ise, Aksi takdirde, **`false`** .

## <a name="objecttostring-method-ccx"></a><a name="tostring"></a> Object:: ToString yöntemi (C++/CX)

Geçerli nesneyi temsil eden dizeyi döndürür.

### <a name="syntax"></a>Syntax

```cpp
public:
virtual String^ ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneyi temsil eden dize. Başvuru sınıfınıza veya yapısına özel bir dize iletisi sağlamak için bu yöntemi geçersiz kılabilirsiniz:

```cpp
public ref class Tree sealed
{
public:
    Tree(){}
    virtual Platform::String^ ToString() override
    {
      return "I’m a Tree";
    };
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)<br/>
[Platform:: Type sınıfı](platform-type-class.md)<br/>
[Tür sistemi](type-system-c-cx.md)
