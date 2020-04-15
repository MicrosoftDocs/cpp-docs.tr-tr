---
title: Platform::Dizi Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Array
- VCCORLIB/Platform::Array::Value
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
ms.openlocfilehash: d625d80df67a3c8207467ad629afd4c2bf88db18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318663"
---
# <a name="platformarray-class"></a>Platform::Dizi Sınıfı

Uygulama ikili arabirimi (ABI) üzerinden alınıp geçilebilen tek boyutlu, değiştirilebilir bir diziyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
private ref class Array<TArg, 1> :
    public WriteOnlyArray<TArg, 1>,
    public IBoxArray<TArg>
```

### <a name="members"></a>Üyeler

Platform::Dizi tüm [yöntemlerini Platformdan devralır::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) `Value` Class ve Platformun özelliğini [uygular::IBoxArray Interface.](../cppcx/platform-iboxarray-interface.md)

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Dizi Oluşturucuları](#ctor)|Sınıf şablonu parametresi, *T*tarafından belirtilen türlerin tek boyutlu, değiştirilebilir bir dizi başharf.|

### <a name="methods"></a>Yöntemler

Bkz. [Platform::WriteOnlyArray Sınıfı](../cppcx/platform-writeonlyarray-class.md).

### <a name="properties"></a>Özellikler

|||
|-|-|
|[Dizi::Değer](#value)|Geçerli diziye bir tanıtıcı alır.|

### <a name="remarks"></a>Açıklamalar

Dizi sınıfı mühürlüdür ve devralınamaz.

Windows Runtime türü sistemi pürüzlü diziler kavramını desteklemez ve bu nedenle bir\<IVector<Platformu geçemez::Array T>> bir dönüş değeri veya yöntem parametresi olarak. Pürüzlü bir dizi veya ABI genelinde diziler `IVector<IVector<T>^>`dizisi geçmek için.

Platform::Array'in ne zaman ve nasıl kullanılacağı hakkında daha fazla bilgi için [Array ve WriteOnlyArray'e](../cppcx/array-and-writeonlyarray-c-cx.md)bakın.

Bu sınıf vccorlib.h üstbilgisinde tanımlanır ve bu başlık derleyici tarafından otomatik olarak dahil edilir. Platform.winmd'de tanımlanan genel bir tür olmadığı için IntelliSense'de görünür, ancak Object Browser'da görünmez.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

## <a name="array-constructors"></a><a name="ctor"></a>Dizi Oluşturucuları

Sınıf şablonu parametresi, *T*tarafından belirtilen türlerin tek boyutlu, değiştirilebilir bir dizi başharf.

## <a name="syntax"></a>Sözdizimi

```cpp
Array(unsigned int size);
Array(T* data, unsigned int size);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıf şablonu parametresi.

*Boyutu*<br/>
Dizideki öğelerin sayısı

*Veri*<br/>
Bu Dizi nesnesini başlatmak `T` için kullanılan tür veri dizisine işaretçi.

### <a name="remarks"></a>Açıklamalar

Platform örnekleri nin nasıl oluşturulacağı hakkında daha fazla bilgi için:Dizi, [bkz.](../cppcx/array-and-writeonlyarray-c-cx.md)

## <a name="arrayget-method"></a><a name="get"></a>Dizi::get Method

Belirtilen dizin konumundaki dizi öğesine bir başvuru alır.

## <a name="syntax"></a>Sözdizimi

```cpp
T& get(unsigned int index)  const;
```

#### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Dizideki bir öğeyi tanımlayan sıfır tabanlı dizin. En küçük dizin 0'dır ve en `size` büyük dizin [Dizi oluşturucudaki](#ctor)parametre tarafından belirtilen değerdir.

### <a name="return-value"></a>Dönüş Değeri

`index` Parametre tarafından belirtilen dizi öğesi.

## <a name="arrayvalue-property"></a><a name="value"></a>Dizi::Değer Özelliği

Geçerli diziye bir tanıtıcı alır.

## <a name="syntax"></a>Sözdizimi

```cpp
property Array^ Value;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli diziiçin bir tutamaç.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)<br/>
[Dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
