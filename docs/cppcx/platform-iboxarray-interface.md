---
title: Platform::ıboxarray arabirimi
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
ms.openlocfilehash: a35a8b7d9f23bcb624755353e27e52de4b873c5d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497050"
---
# <a name="platformiboxarray-interface"></a>Platform::ıboxarray arabirimi

`IBoxArray` Uygulama ikili arabiriminde (ABI) geçirilen veya koleksiyonları içinde depolanan değer türü diziler için bir sarmalayıcı olan `Platform::Object^` XAML denetimleri de gibi öğeleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
interface class IBoxArray
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Her dizi öğesi kutulanmış değer türü.

### <a name="remarks"></a>Açıklamalar

`IBoxArray` olan C + +/ CX adını `Windows::Foundation::IReferenceArray`.

### <a name="members"></a>Üyeler

`IBoxArray` Arabirimi devralır `IValueType` arabirimi. `IBoxArray` Ayrıca bu üyeleri içerir:

|Yöntem|Açıklama|
|------------|-----------------|
|[Değer](#value)|Bu konuda daha önce depolanan sarmalanmamış bir dizi döndürür `IBoxArray` örneği.|

## <a name="value"></a> IBoxArray::Value özelliği

Bu nesnesinde depolanan değeri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
property T Value {T get();}
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Paketlenmiş değer türü.

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Bu nesnesinde depolanan değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bir örnek için bkz. [kutulama](../cppcx/boxing-c-cx.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)