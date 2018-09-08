---
title: is_trivially_copy_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 688252b4b361357f4dba862574ce6698d61b7c86
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102765"
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
