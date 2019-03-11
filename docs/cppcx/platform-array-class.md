---
title: Platform::Array sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Array Constructors
- VCCORLIB/Namespace not found::Platform::Array::Value
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
ms.openlocfilehash: 597f8e32e2da95370169cdbfe2ccd209296322cc
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751667"
---
# <a name="platformarray-class"></a>Platform::Array sınıfı

Alınan ve uygulama ikili arabiriminde (ABI) geçirilen tek boyutlu, değiştirilebilir bir dizisini temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
private ref class Array<TArg, 1> :
    public WriteOnlyArray<TArg, 1>,
    public IBoxArray<TArg>
```

### <a name="members"></a>Üyeler

Platform::Array devralır, tüm yöntemlerden [Platform::WriteOnlyArray sınıfı](../cppcx/platform-writeonlyarray-class.md) ve uygulayan `Value` özelliği [Platform::ıboxarray arabirimi](../cppcx/platform-iboxarray-interface.md).

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Dizi oluşturucular](#ctor)|Sınıf şablonu parametresi tarafından belirtilen tür tek boyutlu, değiştirilebilir bir dizi başlatır *T*.|

### <a name="methods"></a>Yöntemler

Bkz: [Platform::WriteOnlyArray sınıfı](../cppcx/platform-writeonlyarray-class.md).

### <a name="properties"></a>Özellikler

|||
|-|-|
|[Array::Value](#value)|Geçerli dizi için bir tanıtıcı alır.|

### <a name="remarks"></a>Açıklamalar

Array sınıfı korumalı ve devralınamaz.

Windows çalışma zamanı tür sistemi, düzensiz diziler kavramını desteklemiyor ve bu nedenle bir Ivector geçirilemez < Platform::Array\<T >> dönüş değeri veya yöntemin parametre olarak. Basit bir dizi veya sıralarının ABI arasında geçirmek için kullanmak `IVector<IVector<T>^>`.

Ne zaman ve nasıl Platform::Array kullanılacağı hakkında daha fazla bilgi için bkz. [dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

Windows çalışma zamanı tür sistemi, düzensiz diziler kavramını desteklemiyor ve bu nedenle bir Ivector geçirilemez < Platform::Array\<T >> dönüş değeri veya yöntemin parametre olarak. Basit bir dizi veya sıralarının ABI arasında geçirmek için kullanmak `IVector<IVector<T>^>`.

Bu sınıf, derleyici tarafından otomatik olarak eklenir vccorlib.h üstbilgisinde tanımlanır. Platform.winmd içinde tanımlanan ortak bir tür olmadığından IntelliSense ancak içinde olmayan nesne tarayıcısı görülebilir.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

## <a name="ctor"></a>  Dizi oluşturucular

Sınıf şablonu parametresi tarafından belirtilen tür tek boyutlu, değiştirilebilir bir dizi başlatır *T*.

## <a name="syntax"></a>Sözdizimi

```cpp
Array(unsigned int size);
Array(T* data, unsigned int size);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon parametresi sınıf.

*Boyutu*<br/>
Dizideki öğelerin sayısı

*Veri*<br/>
Bir dizi veri türü için bir işaretçi `T` bu dizi nesnesini başlatmak için kullanılır.

### <a name="remarks"></a>Açıklamalar

Platform::Array örnekleri oluşturma hakkında daha fazla bilgi için bkz. [dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="get"></a>  Array::GET yöntemi

Belirtilen dizin konumundaki dizi öğesinin bir başvuru alır.

## <a name="syntax"></a>Sözdizimi

```cpp
T& get(unsigned int index)  const;
```

#### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Dizideki bir öğe tanımlar sıfır tabanlı dizini. En düşük dizin 0 ve en fazla dizin tarafından belirtilen değer `size` parametresinde [Array Oluşturucusu](#ctor).

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen dizi öğesi `index` parametresi.

## <a name="value"></a>  Array::Value özelliği

Geçerli dizi için bir tanıtıcı alır.

## <a name="syntax"></a>Sözdizimi

```cpp
property Array^ Value;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dizi için bir tanıtıcı.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)<br/>
[Dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
