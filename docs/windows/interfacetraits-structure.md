---
title: Interfacetraits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
dev_langs:
- C++
helpviewer_keywords:
- InterfaceTraits structure
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 966759acdac3cf78625cfd072471245a6e42ad63
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597121"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
   typename I0
>
struct __declspec(novtable) InterfaceTraits;
template<typename CloakedType>
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;

template<>
struct __declspec(novtable) InterfaceTraits<Nil>;
```

### <a name="parameters"></a>Parametreler

*I0*  
Bir arabirimin adı.

*CloakedType*  
İçin `RuntimeClass`, `Implements` ve `ChainInterfaces`, arabirim kimlikleri listesinde olmayacak bir arabirim desteklenir.

## <a name="remarks"></a>Açıklamalar

Genel özelliklerini bir arabirim uygular.

İkinci bir özelleştirmesi gizlenmiş arabirimleri için şablonudur. Nil parametreleri için bir özelleştirmesi üçüncü şablonudur.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`Base`|İçin bir eşanlamlı *I0* şablon parametresi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[InterfaceTraits::CanCastTo Metodu](../windows/interfacetraits-cancastto-method.md)|Belirtilen işaretçi işaretçisi içerip içermeyeceğini belirten `Base`.|
|[InterfaceTraits::CastToBase Metodu](../windows/interfacetraits-casttobase-method.md)|Belirtilen bir işaretçi işaretçisi bıraktığı `Base`.|
|[InterfaceTraits::CastToUnknown Metodu](../windows/interfacetraits-casttounknown-method.md)|Belirtilen bir işaretçi işaretçisi bıraktığı `IUnknown`.|
|[InterfaceTraits::FillArrayWithIid Metodu](../windows/interfacetraits-fillarraywithiid-method.md)|Arabirim kimliği atar `Base` dizini bağımsız değişkeni tarafından belirtilen dizi öğesi için.|
|[InterfaceTraits::Verify Metodu](../windows/interfacetraits-verify-method.md)|Doğrular `Base` düzgün şekilde türetilir.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[InterfaceTraits::IidCount Sabiti](../windows/interfacetraits-iidcount-constant.md)|Geçerli ile ilişkili kimlikleri arabirimi sayısını tutar **Interfacetraits** nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InterfaceTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)