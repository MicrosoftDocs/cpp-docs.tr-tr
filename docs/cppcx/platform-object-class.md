---
title: Platform::Object sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Object::Object
- VCCORLIB/Platform::Object::Equals
- VCCORLIB/Platform::Object::GetHashCode
- VCCORLIB/Platform::Object::ReferenceEquals
- VCCORLIB/Platform::ToString
- VCCORLIB/Platform::GetType
dev_langs:
- C++
helpviewer_keywords:
- Object class
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39c51c10ad8c697fcc21c56fcef247c17e8faab5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069769"
---
# <a name="platformobject-class"></a>Platform::Object sınıfı

Başvuru sınıfları ve Windows çalışma zamanı uygulamalarında başvuru yapı birimleri için genel davranış sağlar. Tüm başvuru sınıfı ve ref struct örnekleri Platform::Object için örtük olarak dönüştürülebilir ^ ve kendi sanal ToString yöntemini geçersiz kılabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class Object : Object
```

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Object::Object](#ctor)|Nesne sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Object::Equals](#equals)|Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.|
|[Object::GetHashCode](#gethashcode)|Bu örneğin karma kodunu döndürür.|
|[Object::ReferenceEquals](#referenceequals)|Belirtilen nesne örnekleri aynı örneği olup olmadığını belirler.|
|[ToString](#tostring)|Geçerli nesneyi temsil eden bir dize döndürür. Geçersiz kılınabilir.|
|[GetType](#gettype)|Alır bir [Platform::Type](../cppcx/platform-type-class.md) , geçerli örneğini açıklar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Object`

`Object`

### <a name="requirements"></a>Gereksinimler

**Başlık:** vccorlib.h

**Namespace:** platformu

## <a name="equals"></a> Object::Equals yöntemi

Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.

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

**doğru** aksi nesneler eşitse, **false**.

## <a name="gethashcode"></a>  Object::GetHashCode Yöntemi

Döndürür `IUnknown`* kimlik değeri bir COM nesnesi ise bu örneği için veya bir COM nesnesi değilse, hesaplanan karma değeri.

### <a name="syntax"></a>Sözdizimi

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesneyi benzersiz şekilde tanımlayan bir sayısal değer.

### <a name="remarks"></a>Açıklamalar

GetHashCode maps'a nesneler için anahtarları oluşturmak için kullanabilirsiniz. Karma kodlarını kullanarak karşılaştırabilirsiniz [Object::Equals](#equals). Kod yolu son derece kritik değilse ve `GetHashCode` ve `Equals` temel COM katmana açılır ve yerel yapmak yeterince hızlı olmayan `IUnknown` işaretçi karşılaştırmalar.

## <a name="gettype"></a>  Object::GetType metodu

Döndürür bir [Platform::Type](../cppcx/platform-type-class.md) bir nesnenin çalışma zamanı türü tanımlayan nesne.

### <a name="syntax"></a>Sözdizimi

```cpp
Object::GetType();
```

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

A [Platform::Type](../cppcx/platform-type-class.md) nesnenin çalışma zamanı türünü tanımlayan nesne.

### <a name="remarks"></a>Açıklamalar

Statik [Type::GetTypeCode](../cppcx/platform-type-class.md#gettypecode) almak için kullanılan bir [Platform::TypeCode numaralandırması](../cppcx/platform-typecode-enumeration.md) geçerli türü gösteren bir değer. Bu genellikle yerleşik türler için yararlı olur. Yanı sıra herhangi bir başvuru sınıfı türü kodunu [Platform::String](../cppcx/platform-string-class.md) (1) bir nesnedir.

[Windows::UI::Xaml::Interop::TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) sınıfı Windows API tür bilgileri Windows bileşenleri ve uygulamalar arasında geçirme dil bağımsız bir yol olarak kullanılır. T[Platform::Type sınıfı](../cppcx/platform-type-class.md) arasında dönüştürme işleçleri olan `Type` ve `TypeName`.

Kullanım [TypeID](../windows/typeid-cpp-component-extensions.md) döndürülecek işleci bir `Platform::Type` nesne için XAML sayfalar arasında gezinirken örneğin bir sınıf adı:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

## <a name="see-also"></a>Ayrıca Bkz.

[Platform::Type Sınıfı](../cppcx/platform-type-class.md)<br/>
[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)<br/>
[Türü System] (.. /cppcx/Type-System-c-CX.MD

## <a name="ctor"></a>  Object::Object Oluşturucusu

Nesne sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
public:Object();
```

## <a name="referenceequals"></a>  Object::ReferenceEquals yöntemi

Belirtilen nesne örnekleri aynı örneği olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2);
```

### <a name="parameters"></a>Parametreler

*obj1*<br/>
Karşılaştırılacak ilk nesne.

*obj2*<br/>
Karşılaştırılacak ikinci nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ise iki nesnenin aynı; Aksi takdirde, **false**.

## <a name="tostring"></a>  Object::ToString yöntemi (C + +/ CX)

Geçerli nesneyi temsil eden bir dize döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
public:
virtual String^ ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneyi temsil eden bir dize. Bir özel dize iletisi ref class veya struct sağlamak için bu yöntemi geçersiz kılabilirsiniz:

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

## <a name="see-also"></a>Ayrıca Bkz.

[Platform Namespace](platform-namespace-c-cx.md)