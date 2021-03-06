---
description: ': Platform:: ıboxarray arabirimi hakkında daha fazla bilgi edinin'
title: 'Platform:: ıboxarray arabirimi'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IBoxArray
- VCCORLIB/Platform::IBoxArray::Value
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
ms.openlocfilehash: 8b87a00d709bec8af016de4532c7c4ec759d72fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195152"
---
# <a name="platformiboxarray-interface"></a>Platform:: ıboxarray arabirimi

`IBoxArray` , uygulama ikili arabirimine (ABı) geçirilen veya `Platform::Object^` xaml denetimlerinde bulunanlar gibi öğelerin koleksiyonlarında depolanan değer türlerinin dizileri için sarmalayıcıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
interface class IBoxArray
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Her dizi öğesindeki kutulanmış değerin türü.

### <a name="remarks"></a>Açıklamalar

`IBoxArray` , için C++/CX adıdır `Windows::Foundation::IReferenceArray` .

### <a name="members"></a>Üyeler

`IBoxArray`Arabirim `IValueType` arabiriminden devralır. `IBoxArray` Şu üyelere de sahiptir:

|Yöntem|Açıklama|
|------------|-----------------|
|[Değer](#value)|Bu örnekte daha önce depolanan kutulanmamış diziyi döndürür `IBoxArray` .|

## <a name="iboxarrayvalue-property"></a><a name="value"></a> Iboxarray:: Value özelliği

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

[Dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
