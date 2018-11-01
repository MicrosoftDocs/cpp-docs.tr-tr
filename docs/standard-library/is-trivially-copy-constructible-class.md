---
title: is_trivially_copy_constructible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
ms.openlocfilehash: aa6d6b19ae2bd5d6967c57db61c5697c0c6153e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630522"
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible Sınıfı

Önemsiz bir kopya Oluşturucu türüne sahip olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* false tuttuğu Önemsiz kopya Oluşturucu, aksi takdirde sahip bir sınıftır.

Bir sınıf için kopya Oluşturucu *T* örtük olarak bildirilmiş, sınıf gereksizse, *T* sanal işlevler veya sanal tabanları olan sınıfın tüm doğrudan tabanları olmayan *T* sahip Önemsiz kopya oluşturucuları, tüm statik olmayan veri üyeleri sınıf türünün sınıflarını Önemsiz kopya oluşturucuları olması ve dizi sınıf türünde tüm statik olmayan veri üyelerinin sınıflarını Önemsiz kopya oluşturucuları olması.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
