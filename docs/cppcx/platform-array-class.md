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
ms.openlocfilehash: 4903c18f981c87c418a6ab08595816ce22a7413c
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742950"
---
# <a name="platformarray-class"></a>Platform:: Array sınıfı

Uygulama ikili arabirimine (ABı) alınabilecek ve geçirilebilecek tek boyutlu, değiştirilebilir bir diziyi temsil eder.

## <a name="syntax"></a>Syntax

```cpp
template <typename T>
private ref class Array<TArg, 1> :
    public WriteOnlyArray<TArg, 1>,
    public IBoxArray<TArg>
```

### <a name="members"></a>Üyeler

Platform:: Array, [Platform:: WriteOnlyArray sınıfından](../cppcx/platform-writeonlyarray-class.md) tüm yöntemlerini devralır ve `Value` [Platform:: ıboxarray arabiriminin](../cppcx/platform-iboxarray-interface.md)özelliğini uygular.

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Dizi oluşturucular](#ctor)|Sınıf şablonu parametresi, *T*tarafından belirtilen tek boyutlu, değiştirilebilir bir dizi türü başlatır.|

### <a name="methods"></a>Yöntemler

Bkz. [Platform:: WriteOnlyArray sınıfı](../cppcx/platform-writeonlyarray-class.md).

### <a name="properties"></a>Özellikler

| Ad | Açıklama |
|--|--|
| [Array:: Value](#value) | Geçerli diziye bir tanıtıcı alır. |

### <a name="remarks"></a>Açıklamalar

Dizi sınıfı mühürlü ve devralınamaz.

Windows Çalışma Zamanı tür sistemi, pürüzlü Diziler kavramını desteklemez ve bu nedenle bir `IVector<Platform::Array<T>>` dönüş değeri veya yöntem parametresi olarak geçirilemez. ABı arasında pürüzlü bir diziyi veya dizi dizilerini geçirmek için kullanın `IVector<IVector<T>^>` .

Platform:: Array öğesinin ne zaman ve nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [Array ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

Bu sınıf, derleyici tarafından otomatik olarak eklenen vccorlib. h üst bilgisinde tanımlanmıştır. Bu, IntelliSense 'de görünür ancak platform. winmd içinde tanımlı bir genel tür olmadığından Nesne Tarayıcısı değildir.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

## <a name="array-constructors"></a><a name="ctor"></a> Dizi oluşturucular

Sınıf şablonu parametresi, *T*tarafından belirtilen tek boyutlu, değiştirilebilir bir dizi türü başlatır.

### <a name="syntax"></a>Söz dizimi

```cpp
Array(unsigned int size);
Array(T* data, unsigned int size);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıf şablonu parametresi.

*boyutla*<br/>
Dizideki öğelerin sayısı

*data*<br/>
`T`Bu dizi nesnesini başlatmak için kullanılan türdeki veri dizisine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Platform:: Array örnekleri oluşturma hakkında daha fazla bilgi için bkz. [Array ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="arrayget-method"></a><a name="get"></a> Array:: get yöntemi

Belirtilen dizin konumundaki dizi öğesine bir başvuru alır.

### <a name="syntax"></a>Söz dizimi

```cpp
T& get(unsigned int index)  const;
```

#### <a name="parameters"></a>Parametreler

*indeks*<br/>
Dizide bir öğe tanımlayan sıfır tabanlı dizin. En düşük dizin 0 ' dır ve en yüksek dizin, `size` [dizi oluşturucusunda](#ctor)parametresi tarafından belirtilen değerdir.

### <a name="return-value"></a>Dönüş Değeri

Parametresi tarafından belirtilen dizi öğesi `index` .

## <a name="arrayvalue-property"></a><a name="value"></a> Array:: Value özelliği

Geçerli diziye bir tanıtıcı alır.

### <a name="syntax"></a>Syntax

```cpp
property Array^ Value;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli diziye yönelik bir tanıtıcı.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)<br/>
[Dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
