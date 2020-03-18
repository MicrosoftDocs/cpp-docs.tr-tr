---
title: 'Platform:: ıboxarray arabirimi'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IBoxArray
- VCCORLIB/Platform::IBoxArray::Value
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
ms.openlocfilehash: 493770cab092c2bb719d47e5d3a9d6a9f0646489
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444164"
---
# <a name="platformiboxarray-interface"></a>Platform:: ıboxarray arabirimi

`IBoxArray`, uygulama ikili arabirimine (ABı) geçirilen veya XAML denetimlerinde bulunan `Platform::Object^` öğelerinin koleksiyonlarında depolanan değer türlerinin dizileri için sarmalayıcıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
interface class IBoxArray
```

#### <a name="parameters"></a>Parametreler

*Şı*<br/>
Her dizi öğesindeki kutulanmış değerin türü.

### <a name="remarks"></a>Açıklamalar

`IBoxArray`, `Windows::Foundation::IReferenceArray`C++için/CX adıdır.

### <a name="members"></a>Üyeler

`IBoxArray` arabirimi `IValueType` arabiriminden devralır. `IBoxArray` Ayrıca şu üyelere sahiptir:

|Yöntem|Açıklama|
|------------|-----------------|
|[Değer](#value)|Daha önce bu `IBoxArray` örneğinde depolanan kutulanmamış diziyi döndürür.|

## <a name="value"></a>Iboxarray:: Value özelliği

Bu nesnede ilk olarak depolanan değeri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
property T Value {T get();}
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Paketlenmiş değerin türü.

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Bu nesnede ilk olarak depolanan değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bir örnek için bkz. [paketleme](../cppcx/boxing-c-cx.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
