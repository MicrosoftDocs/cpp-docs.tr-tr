---
title: 'Platform:: Array sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Array
- VCCORLIB/Platform::Array::Value
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
ms.openlocfilehash: 7d9fca4de954b5ba9c7cbcb3bdfce0fe3263dbd7
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445805"
---
# <a name="platformarray-class"></a>Platform:: Array sınıfı

Uygulama ikili arabirimine (ABı) alınabilecek ve geçirilebilecek tek boyutlu, değiştirilebilir bir diziyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
private ref class Array<TArg, 1> :
    public WriteOnlyArray<TArg, 1>,
    public IBoxArray<TArg>
```

### <a name="members"></a>Üyeler

Platform:: Array, [Platform:: WriteOnlyArray sınıfından](../cppcx/platform-writeonlyarray-class.md) tüm yöntemlerini devralır ve [Platform:: ıboxarray arabiriminin](../cppcx/platform-iboxarray-interface.md)`Value` özelliğini uygular.

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Dizi oluşturucular](#ctor)|Sınıf şablonu parametresi, *T*tarafından belirtilen tek boyutlu, değiştirilebilir bir dizi türü başlatır.|

### <a name="methods"></a>Yöntemler

Bkz. [Platform:: WriteOnlyArray sınıfı](../cppcx/platform-writeonlyarray-class.md).

### <a name="properties"></a>Özellikler

|||
|-|-|
|[Array:: Value](#value)|Geçerli diziye bir tanıtıcı alır.|

### <a name="remarks"></a>Açıklamalar

Dizi sınıfı mühürlü ve devralınamaz.

Windows Çalışma Zamanı tür sistemi, pürüzlü Diziler kavramını desteklemez ve bu nedenle bir IVector < Platform:: Array\<T > > dönüş değeri veya yöntem parametresi olarak geçirilemez. ABı genelinde pürüzlü bir diziyi veya dizi dizilerini geçirmek için `IVector<IVector<T>^>`kullanın.

Platform:: Array öğesinin ne zaman ve nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [Array ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

Bu sınıf, derleyici tarafından otomatik olarak eklenen vccorlib. h üst bilgisinde tanımlanmıştır. Bu, IntelliSense 'de görünür ancak platform. winmd içinde tanımlı bir genel tür olmadığından Nesne Tarayıcısı değildir.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

## <a name="ctor"></a>Dizi oluşturucular

Sınıf şablonu parametresi, *T*tarafından belirtilen tek boyutlu, değiştirilebilir bir dizi türü başlatır.

## <a name="syntax"></a>Sözdizimi

```cpp
Array(unsigned int size);
Array(T* data, unsigned int size);
```

#### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıf şablonu parametresi.

*boyutla*<br/>
Dizideki öğelerin sayısı

*verileri*<br/>
Bu dizi nesnesini başlatmak için kullanılan `T` türünde bir veri dizisine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Platform:: Array örnekleri oluşturma hakkında daha fazla bilgi için bkz. [Array ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="get"></a>Array:: get yöntemi

Belirtilen dizin konumundaki dizi öğesine bir başvuru alır.

## <a name="syntax"></a>Sözdizimi

```cpp
T& get(unsigned int index)  const;
```

#### <a name="parameters"></a>Parametreler

*indeks*<br/>
Dizide bir öğe tanımlayan sıfır tabanlı dizin. En düşük dizin 0 ' dır ve en yüksek dizin, [dizi oluşturucusunda](#ctor)`size` parametresi tarafından belirtilen değerdir.

### <a name="return-value"></a>Dönüş Değeri

`index` parametresi tarafından belirtilen dizi öğesi.

## <a name="value"></a>Array:: Value özelliği

Geçerli diziye bir tanıtıcı alır.

## <a name="syntax"></a>Sözdizimi

```cpp
property Array^ Value;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli diziye yönelik bir tanıtıcı.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)<br/>
[Dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
