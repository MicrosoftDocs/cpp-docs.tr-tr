---
description: 'Daha fazla bilgi edinin: Platform:: WriteOnlyArray sınıfı'
title: 'Platform:: WriteOnlyArray sınıfı'
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
ms.openlocfilehash: cddbe0d3823ba7b9751bd60844d9ce699546b804
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307775"
---
# <a name="platformwriteonlyarray-class"></a>Platform:: WriteOnlyArray sınıfı

Çağıran yöntemin doldurması için bir dizi geçtiğinde giriş parametresi olarak kullanılan tek boyutlu bir diziyi temsil eder.

Bu başvuru sınıfı vccorlib. h; içinde özel olarak bildirilmiştir Bu nedenle, meta verilerde yer verilmez ve yalnızca C++ ' dan tüketilebilir. Bu sınıf yalnızca çağıranın ayırdığı bir diziyi alan giriş parametresi olarak kullanılmak üzere tasarlanmıştır. Kullanıcı kodundan oluşturulabilir değildir. C++ yönteminin, *FillArray* düzeni olarak bilinen bir model olan bu diziye doğrudan yazmasını sağlar. Daha fazla bilgi için bkz. [Array ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="syntax"></a>Syntax

```cpp
private ref class WriteOnlyArray<T, 1>
```

### <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Bu yöntemlerin iç erişilebilirliği vardır. diğer bir deyişle, yalnızca C++ uygulaması veya bileşeni içinde erişilebilir.

|Ad|Açıklama|
|----------|-----------------|
|[WriteOnlyArray:: Begin](#begin)|Dizinin ilk öğesine işaret eden bir yineleyici.|
|[WriteOnlyArray::D ata](#data)|Veri arabelleği işaretçisi.|
|[WriteOnlyArray:: End](#end)|Dizideki son öğeyi geçen bir yineleyici.|
|[WriteOnlyArray:: FastPass](#fastpass)|Dizinin, sistem tarafından saydam olarak gerçekleştirilen bir iyileştirme olan FastPass mekanizmasını kullanıp kullanamayacağını belirtir. Kodunuzda kullanmayın|
|[WriteOnlyArray:: length](#length)|Dizideki öğe sayısını döndürür.|
|[WriteOnlyArray:: set](#set)|Belirtilen öğeyi belirtilen değere ayarlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WriteOnlyArray`

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

**Meta veriler:** Platform. winmd

**Ad alanı:** Platformunun

## <a name="writeonlyarraybegin-method"></a><a name="begin"></a> WriteOnlyArray:: Begin yöntemi

Dizideki ilk öğeye bir işaretçi döndürür.

### <a name="syntax"></a>Syntax

```cpp
T* begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki ilk öğe için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu Yineleyici `std::sort` , dizideki öğeler üzerinde çalışmak için gıbı STL algoritmalarıyla birlikte kullanılabilir.

## <a name="writeonlyarraydata-property"></a><a name="data"></a> WriteOnlyArray::D ata özelliği

Veri arabelleğinin işaretçisi.

### <a name="syntax"></a>Syntax

```cpp
property T* Data{
   T* get() const;
}
```

### <a name="return-value"></a>Dönüş Değeri

Ham dizi baytlarına yönelik bir işaretçi.

## <a name="writeonlyarrayend-method"></a><a name="end"></a> WriteOnlyArray:: End yöntemi

Dizideki son öğeden sonraki bir işaretçiyi döndürür.

### <a name="syntax"></a>Syntax

```cpp
T* end() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki son öğeden sonraki bir işaretçi yineleyicisi.

### <a name="remarks"></a>Açıklamalar

Bu Yineleyici, dizi öğelerinde gibi işlemleri gerçekleştirmek için STL algoritmalarıyla birlikte kullanılabilir `std::sort` .

## <a name="writeonlyarrayfastpass-property"></a><a name="fastpass"></a> WriteOnlyArray:: FastPass özelliği

İç FastPass iyileştirmesinin gerçekleştirilip gerçekleştirilebileceğini gösterir. Kullanıcı kodu tarafından kullanılmak üzere tasarlanmamıştır.

### <a name="syntax"></a>Syntax

```cpp
property bool FastPass{
   bool get() const;
}
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin FastPass olup olmadığını gösteren Boolean değeri.

## <a name="writeonlyarrayget-method"></a><a name="get"></a> WriteOnlyArray:: get yöntemi

Belirtilen dizindeki öğeyi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
T& get(unsigned int indexArg) const;
```

### <a name="parameters"></a>Parametreler

*ındexarg*<br/>
Kullanılacak dizin.

### <a name="return-value"></a>Dönüş Değeri

## <a name="writeonlyarraylength-property"></a><a name="length"></a> WriteOnlyArray:: length özelliği

Arayan tarafından ayrılan dizideki öğelerin sayısını döndürür.

### <a name="syntax"></a>Syntax

```cpp
property unsigned int Length{
   unsigned int get() const;
}
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki öğelerin sayısı

## <a name="writeonlyarrayset-function"></a><a name="set"></a> WriteOnlyArray:: set Işlevi

Dizideki belirtilen dizinde belirtilen değeri ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
T& set(
   unsigned int indexArg,
   T valueArg);
```

### <a name="parameters"></a>Parametreler

*ındexarg*<br/>
Ayarlanacak öğenin dizini.

*değer Kazang*<br/>
Ayarlanacak değer `indexArg` .

### <a name="return-value"></a>Dönüş Değeri

Yeni ayarlanmış olan öğeye başvuru.

### <a name="remarks"></a>Açıklamalar

HRESULT değerini yorumlama hakkında daha fazla bilgi için bkz. [com hata kodlarının yapısı](/windows/win32/com/structure-of-com-error-codes).

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)<br/>
[C++ ' ta Windows Çalışma Zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
