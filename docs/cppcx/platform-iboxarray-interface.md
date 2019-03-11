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
ms.openlocfilehash: ea2517ad64cfd6742ef072d24e94a9b3899cea2d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747105"
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

## <a name="see-also"></a>Ayrıca bkz.

[Dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
