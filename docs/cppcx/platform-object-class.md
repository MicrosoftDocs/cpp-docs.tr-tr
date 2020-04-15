---
title: Platform::Nesne Sınıfı
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
ms.openlocfilehash: 8300ec484bdb58919ce8e450b706dd07c275ceee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363681"
---
# <a name="platformobject-class"></a>Platform::Nesne Sınıfı

Windows Runtime uygulamalarında ref sınıfları ve ref structs için ortak davranış sağlar. Tüm ref sınıfı ve ref struct örnekleri dolaylı olarak Platform::Object^ dönüştürülebilir ve sanal ToString yöntemini geçersiz kılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class Object : Object
```

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Nesne::Nesne](#ctor)|Nesne sınıfının yeni bir örneğini başolarak adlandırır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Nesne::Eşittir](#equals)|Belirtilen nesnenin geçerli nesneye eşit olup olmadığını belirler.|
|[Nesne::GetHashCode](#gethashcode)|Bu örneğe ilişkin karma kodu döndürür.|
|[Nesne::ReferenceEquals](#referenceequals)|Belirtilen Nesne örneklerinin aynı örnek olup olmadığını belirler.|
|[ToString](#tostring)|Geçerli nesneyi temsil eden dizeyi döndürür. Geçersiz kılınabilir.|
|[GetType](#gettype)|Bir [Platform alır::Geçerli](../cppcx/platform-type-class.md) örneği açıklayan tür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Object`

`Object`

### <a name="requirements"></a>Gereksinimler

**Başlık:** vccorlib.h

**Ad alanı:** Platform

## <a name="objectequals-method"></a><a name="equals"></a>Nesne::Eşittir Yöntemi

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

nesneler eşitse **doğru,** aksi takdirde **yanlış**.

## <a name="objectgethashcode-method"></a><a name="gethashcode"></a>Nesne::GetHashCode Yöntemi

Com `IUnknown`nesnesi yse bu örnek için * kimlik değerini veya com nesnesi değilse hesaplanmış karma değeri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesneyi benzersiz olarak tanımlayan sayısal bir değer.

### <a name="remarks"></a>Açıklamalar

Haritalardaki nesneler için anahtarlar oluşturmak için GetHashCode'u kullanabilirsiniz. Karma kodları [Nesne::Equals'ı](#equals)kullanarak karşılaştırabilirsiniz. Kod yolu son derece `GetHashCode` kritikse ve `Equals` yeterince hızlı değilse, temel COM katmanına `IUnknown` düşebilir ve yerel işaretçi karşılaştırmaları yapabilirsiniz.

## <a name="objectgettype-method"></a><a name="gettype"></a>Nesne::GetType Yöntemi

Platform [döndürür::Bir](../cppcx/platform-type-class.md) nesnenin çalışma zamanı türünü açıklayan nesne yazın.

### <a name="syntax"></a>Sözdizimi

```cpp
Object::GetType();
```

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

[Bir Platform::Nesnenin](../cppcx/platform-type-class.md) çalışma zamanı türünü açıklayan nesne yazın.

### <a name="remarks"></a>Açıklamalar

Statik [Tür::GetTypeCode](../cppcx/platform-type-class.md#gettypecode) bir Platform almak için [kullanılabilir::Geçerli](../cppcx/platform-typecode-enumeration.md) türü temsil eden TypeCode Numaralandırma değeri. Bu, çoğunlukla yerleşik türleri için yararlıdır. [Platform::String](../cppcx/platform-string-class.md) is Object (1) dışında herhangi bir ref sınıfının tür kodudur.

[Windows:UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename) sınıfı, Windows API'lerinde Windows bileşenleri ve uygulamalar arasında tür bilgilerini aktarmanın dilden bağımsız bir yolu olarak kullanılır. T[Platformu::Type Class](../cppcx/platform-type-class.md) arasında `Type` dönüştürme için `TypeName`işleçleri vardır.

Örneğin XAML sayfaları `Platform::Type` arasında gezinirken bir sınıf adı için bir nesne döndürmek için [typeid](../extensions/typeid-cpp-component-extensions.md) işleci kullanın:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

## <a name="objectobject-constructor"></a><a name="ctor"></a>Nesne::Nesne Oluşturucu

Nesne sınıfının yeni bir örneğini başolarak adlandırır.

### <a name="syntax"></a>Sözdizimi

```cpp
public:Object();
```

## <a name="objectreferenceequals-method"></a><a name="referenceequals"></a>Nesne::ReferenceEquals Yöntemi

Belirtilen Nesne örneklerinin aynı örnek olup olmadığını belirler.

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

iki nesne aynıysa **doğrudur;** aksi takdirde, **yanlış**.

## <a name="objecttostring-method-ccx"></a><a name="tostring"></a>Nesne::ToString Yöntemi (C++/CX)

Geçerli nesneyi temsil eden dizeyi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
public:
virtual String^ ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneyi temsil eden dize. Ref sınıfınızda veya yapınızda özel bir dize iletisi sağlamak için bu yöntemi geçersiz kılabilirsiniz:

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

[Platform İsim Alanı](platform-namespace-c-cx.md)<br/>
[Platform::Type Sınıfı](platform-type-class.md)<br/>
[Tür Sistemi](type-system-c-cx.md)
