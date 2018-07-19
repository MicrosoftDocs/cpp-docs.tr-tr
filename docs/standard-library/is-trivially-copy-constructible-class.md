---
title: is_trivially_copy_constructible sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 410566c623595cc941ab6e6ad21dd95bd70fe516
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963673"
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible Sınıfı

Önemsiz bir kopya Oluşturucu türüne sahip olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>Parametreler

*T* Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* false tuttuğu Önemsiz kopya Oluşturucu, aksi takdirde sahip bir sınıftır.

Bir sınıf için kopya Oluşturucu *T* örtük olarak bildirilmiş, sınıf gereksizse, *T* sanal işlevler veya sanal tabanları olan sınıfın tüm doğrudan tabanları olmayan *T* sahip Önemsiz kopya oluşturucuları, tüm statik olmayan veri üyeleri sınıf türünün sınıflarını Önemsiz kopya oluşturucuları olması ve dizi sınıf türünde tüm statik olmayan veri üyelerinin sınıflarını Önemsiz kopya oluşturucuları olması.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
