---
description: ': Platform:: IBox arabirimi hakkında daha fazla bilgi'
title: 'Platform:: Ibox arabirimi'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
ms.openlocfilehash: abd1b9107fe1d472135f2b2addc7fa4b0f88ecfd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195183"
---
# <a name="platformibox-interface"></a>Platform:: Ibox arabirimi

[Platform:: Ibox](../cppcx/platform-ibox-interface.md) arabirimi, arabirimin C++ adıdır `Windows::Foundation::IReference` .

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
interface class IBox
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Paketlenmiş değerin türü.

### <a name="remarks"></a>Açıklamalar

`IBox<T>`Arabirim öncelikle [değer sınıfları ve yapıları (C++/CX)](../cppcx/value-classes-and-structs-c-cx.md)bölümünde açıklandığı gibi, null olabilen değer türlerini temsil etmek için dahili olarak kullanılır. Arabirim, türünde Parametreler alan C++ yöntemlerine geçirilen değer türlerini Box için de kullanılır `Object^` . Olarak bir giriş parametresini açıkça bildirebilirsiniz `IBox<SomeValueType>` . Bir örnek için bkz. [paketleme](../cppcx/boxing-c-cx.md).

### <a name="requirements"></a>Gereksinimler

### <a name="members"></a>Üyeler

`Platform::IBox`Arabirim [Platform:: ıvaluetype](../cppcx/platform-ivaluetype-interface.md) arabiriminden devralır. `IBox` Şu üyelere sahiptir:

**Özellikler**

|Yöntem|Açıklama|
|------------|-----------------|
|[Değer](#value)|Daha önce Bu örnekte depolanan kutulanmamış değeri döndürür `IBox` .|

## <a name="iboxvalue-property"></a><a name="value"></a> Ibox:: Value özelliği

Bu nesnede ilk olarak depolanan değeri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
property T Value {T get();}
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Paketlenmiş değerin türü.

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Bu nesnede ilk olarak depolanan değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bir örnek için bkz. [paketleme](../cppcx/boxing-c-cx.md).

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
