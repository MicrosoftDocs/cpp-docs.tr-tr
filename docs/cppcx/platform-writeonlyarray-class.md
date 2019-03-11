---
title: Platform::WriteOnlyArray sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WriteOnlyArray::begin
- VCCORLIB/Platform::WriteOnlyArray::Data
- VCCORLIB/Platform::WriteOnlyArray::end
- VCCORLIB/Platform::WriteOnlyArray::FastPass
- VCCORLIB/Platform::WriteOnlyArray::Length
- VCCORLIB/Platform::WriteOnlyArray::set
helpviewer_keywords:
- Platform::WriteOnlyArray Class
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
ms.openlocfilehash: fb582106fe2f18e939f11180048a125c683ca2f6
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744399"
---
# <a name="platformwriteonlyarray-class"></a>Platform::WriteOnlyArray sınıfı

Doldur yönteminin bir dizi çağırana başarılı olduğunda giriş parametresi olarak kullanılan bir tek boyutlu dizi temsil eder.

Bu başvuru sınıfı, private olarak vccorlib.h bildirilir; Bu nedenle, meta verilerde yayılır değildir ve yalnızca C++'tan tüketilebilir. Bu sınıf, çağırana ayırdığı bir dizi alan bir giriş parametresi olarak kullanılmak üzere yalnızca yöneliktir. Kullanıcı kodundan atmamalıdır değil. Doğrudan bu diziye yazmak C++ yöntemi sağlar — olarak bilinen bir deseni *FillArray* deseni. Daha fazla bilgi için [dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="syntax"></a>Sözdizimi

```cpp
private ref class WriteOnlyArray<T, 1>
```

### <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Bu yöntemleri dahili erişilebilirlik sahip — diğer bir deyişle, bunlar yalnızca C++ uygulama veya bileşen içinde erişilebilir.

|Ad|Açıklama|
|----------|-----------------|
|[WriteOnlyArray::begin](#begin)|Dizinin ilk öğeyi gösteren bir yineleyici.|
|[WriteOnlyArray::Data](#data)|Veri arabelleği için bir işaretçi.|
|[WriteOnlyArray::end](#end)|Dizi içindeki son öğeden bir öncekine gösteren bir yineleyici.|
|[WriteOnlyArray::FastPass](#fastpass)|Dizi şeffaf bir şekilde sistem tarafından gerçekleştirilen bir iyileştirme FastPass mekanizması kullanıp kullanamayacağını belirtir. Bu, kodunuzda kullanma|
|[WriteOnlyArray::Length](#length)|Dizideki öğelerin sayısını döndürür.|
|[WriteOnlyArray::set](#set)|Belirtilen öğeyi belirtilen değere ayarlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WriteOnlyArray`

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

**Meta veri:** Platform.winmd

**Namespace:** Platform

## <a name="begin"></a>  WriteOnlyArray::begin yöntemi

Dizideki ilk öğe için bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
T* begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki ilk öğe işaretçisi.

### <a name="remarks"></a>Açıklamalar

STL algoritmaları ile bu yineleyici gibi kullanılabilir `std::sort` dizideki öğeler üzerinde çalışılacak.

## <a name="data"></a>  WriteOnlyArray::Data özelliği

Veri arabelleği için işaretçi.

### <a name="syntax"></a>Sözdizimi

```cpp
property T* Data{
   T* get() const;
}
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin ham bayt için bir işaretçi.

## <a name="end"></a>  WriteOnlyArray::end yöntemi

Dizi içindeki son öğeden bir öncekine bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
T* end() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizi içindeki son öğeden bir öncekine işaretçi yineleyici.

### <a name="remarks"></a>Açıklamalar

STL algoritmaları ile bu yineleyici gibi işlemleri gerçekleştirmek için kullanılabilir `std::sort` dizi öğeleri üzerinde.

## <a name="fastpass"></a>  WriteOnlyArray::FastPass özelliği

İç FastPass iyileştirme gerçekleştirip gerçekleştirmediğini belirtir. Kullanıcı kodu tarafından kullanılmak üzere tasarlanmamıştır.

### <a name="syntax"></a>Sözdizimi

```cpp
property bool FastPass{
   bool get() const;
}
```

### <a name="return-value"></a>Dönüş Değeri

Dizi FastPass olup olmadığını gösteren Boole değeri.

## <a name="get"></a>  WriteOnlyArray::get yöntemi

Belirtilen dizindeki öğeyi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
T& get(unsigned int indexArg) const;
```

### <a name="parameters"></a>Parametreler

*indexArg*<br/>
Kullanılacak dizin.

### <a name="return-value"></a>Dönüş Değeri

## <a name="length"></a>  WriteOnlyArray::Length özelliği

Arayana ayrılan dizideki öğelerin sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
property unsigned int Length{
   unsigned int get() const;
}
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki öğelerin sayısı

## <a name="set"></a>  WriteOnlyArray::set işlevi

Dizi belirtilen dizindeki belirtilen değere ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
T& set(
   unsigned int indexArg,
   T valueArg);
```

### <a name="parameters"></a>Parametreler

*indexArg*<br/>
Ayarlanacak öğenin dizini.

*valueArg*<br/>
Ayarlanan değer `indexArg`.

### <a name="return-value"></a>Dönüş Değeri

Ayarlamanız yeterlidir öğeye bir başvuru.

### <a name="remarks"></a>Açıklamalar

HRESULT değerini yorumlama hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes).

## <a name="see-also"></a>Ayrıca bkz.

[Platform Namespace](platform-namespace-c-cx.md)<br/>
[C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
