---
title: Platform::WriteOnlyArray Sınıfı
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
ms.openlocfilehash: d06ed19b7c041f9ae73f862ba521449a206aa321
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374640"
---
# <a name="platformwriteonlyarray-class"></a>Platform::WriteOnlyArray Sınıfı

Arayan, yöntemin dolması için bir dizi geçtiğinde giriş parametresi olarak kullanılan tek boyutlu bir diziyi temsil eder.

Bu ref sınıfı vccorlib.h özel olarak ilan edilir; bu nedenle, meta verilerde yayılan değil ve sadece C++'dan tüketilebilir. Bu sınıf yalnızca arayanın ayırdığı bir diziyi alan bir giriş parametresi olarak kullanılmak üzere tasarlanmıştır. Kullanıcı kodundan yapılamaz. Bir C++ yönteminin doğrudan bu diziye yazmasını sağlar— *fillarray* deseni olarak bilinen bir desen. Daha fazla bilgi için [Array ve WriteOnlyArray'e](../cppcx/array-and-writeonlyarray-c-cx.md)bakın.

## <a name="syntax"></a>Sözdizimi

```cpp
private ref class WriteOnlyArray<T, 1>
```

### <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Bu yöntemler dahili erişilebilirlik var, yani yalnızca C++ uygulaması veya bileşeni içinde erişilebilir.

|Adı|Açıklama|
|----------|-----------------|
|[WriteOnlyArray::başla](#begin)|Dizinin ilk öğesini gösteren bir yineleyici.|
|[WriteOnlyArray::Data](#data)|Veri arabelleği için bir işaretçi.|
|[WriteOnlyArray::end](#end)|Dizideki son öğeyi geçmiş bir öğeye işaret eden bir yineleyici.|
|[WriteOnlyArray::fastpass](#fastpass)|Dizinin sistem tarafından şeffaf bir şekilde gerçekleştirilen bir optimizasyon olan FastPass mekanizmasını kullanıp kullanamayacağını gösterir. Bunu kodunuzda kullanmayın|
|[WriteOnlyArray::Uzunluk](#length)|Dizideki öğe sayısını döndürür.|
|[WriteOnlyArray::set](#set)|Belirtilen öğeyi belirtilen değere ayarlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WriteOnlyArray`

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

**Meta veriler:** Platform.winmd

**Ad alanı:** Platform

## <a name="writeonlyarraybegin-method"></a><a name="begin"></a>WriteOnlyArray::begin Method

Dizideki ilk öğeye bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
T* begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki ilk öğeiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yineleyici, dizideki öğeler üzerinde çalışmak `std::sort` gibi STL algoritmaları ile kullanılabilir.

## <a name="writeonlyarraydata-property"></a><a name="data"></a>WriteOnlyArray::Data Özellik

Veri arabelleği için işaretçi.

### <a name="syntax"></a>Sözdizimi

```cpp
property T* Data{
   T* get() const;
}
```

### <a name="return-value"></a>Dönüş Değeri

Ham dizi baytları için bir işaretçi.

## <a name="writeonlyarrayend-method"></a><a name="end"></a>WriteOnlyArray::end Yöntem

Bir işaretçiyi dizideki son öğeyi geçmiş bir işaretçiye döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
T* end() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki son öğeyi geçmiş bir işaretçi yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu yineleyici, dizi öğeleri gibi `std::sort` işlemleri gerçekleştirmek için STL algoritmaları ile kullanılabilir.

## <a name="writeonlyarrayfastpass-property"></a><a name="fastpass"></a>WriteOnlyArray::FastPass Özelliği

Dahili FastPass optimizasyonunun yapılıp yapılamayacağını gösterir. Kullanıcı kodu tarafından kullanılmak üzere tasarlanmamıştır.

### <a name="syntax"></a>Sözdizimi

```cpp
property bool FastPass{
   bool get() const;
}
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin FastPass olup olmadığını gösteren Boolean değeri.

## <a name="writeonlyarrayget-method"></a><a name="get"></a>WriteOnlyArray::get Method

Belirtilen dizindeki öğeyi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
T& get(unsigned int indexArg) const;
```

### <a name="parameters"></a>Parametreler

*indexArg*<br/>
Kullanılacak dizin.

### <a name="return-value"></a>Dönüş Değeri

## <a name="writeonlyarraylength-property"></a><a name="length"></a>WriteOnlyArray::Uzunluk Özelliği

Arayanın tahsis ettiği dizideki öğe sayısını verir.

### <a name="syntax"></a>Sözdizimi

```cpp
property unsigned int Length{
   unsigned int get() const;
}
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki öğelerin sayısı

## <a name="writeonlyarrayset-function"></a><a name="set"></a>WriteOnlyArray::set Fonksiyonu

Dizide belirtilen dizinde belirtilen değeri ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
T& set(
   unsigned int indexArg,
   T valueArg);
```

### <a name="parameters"></a>Parametreler

*indexArg*<br/>
Ayarlanan öğenin dizin.

*valueArg*<br/>
' de ayarlanan `indexArg`değer

### <a name="return-value"></a>Dönüş Değeri

Yeni ayarlanan öğeye bir başvuru.

### <a name="remarks"></a>Açıklamalar

HRESULT değerinin nasıl yorumlanacağı hakkında daha fazla bilgi için [COM Hata Kodlarının Yapısı'na](/windows/win32/com/structure-of-com-error-codes)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Platform İsim Alanı](platform-namespace-c-cx.md)<br/>
[C++'da Windows Runtime Bileşenleri Oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
