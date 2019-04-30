---
title: is_trivially_copy_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
ms.openlocfilehash: 831e7c5afdd39980876a8e8284a68fec2084a4e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413469"
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable sınıfı

Türü, Önemsiz kopya atama işlecine sahip olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* false tuttuğu Önemsiz kopya atama işlecine, aksi takdirde sahip bir sınıftır.

Bir sınıf için bir atama Oluşturucu *T* , sınıf, örtük olarak sağlanan Önemsiz olduğundan *T* sahip sanal işlev yok, sınıf *T* sahip hiçbir sanal tabanları olan sınıfları tüm statik olmayan veri üyeleri sınıf türünün basit atama işleçleri, ve önemsiz atama işleçleri dizi sınıf türünde tüm statik olmayan veri üyelerinin sınıflarını sahiptir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
