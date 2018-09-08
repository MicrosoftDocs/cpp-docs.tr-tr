---
title: is_trivially_default_constructible sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73bdd8186f2ce56e4a6ecec0fa4f9468d9da8e8c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102713"
---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible Sınıfı

Önemsiz bir varsayılan oluşturucu türüne sahip olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* false tuttuğu Önemsiz Oluşturucu, aksi takdirde sahip bir sınıftır.

Bir sınıf için bir varsayılan oluşturucu *Ty* gereksizse, varsa:

- örtük olarak bildirilmiş bir varsayılan oluşturucusu olan

- sınıf *Ty* sahip sanal işlev yok

- sınıf *Ty* hiçbir sanal temellere sahip

- tüm doğrudan tabanları sınıfının *Ty* Önemsiz oluşturuculara sahip

- tüm statik olmayan veri üyeleri sınıf türünün sınıflarını Önemsiz oluşturuculara sahip

- dizi sınıf türünde tüm statik olmayan veri üyelerinin sınıflarını Önemsiz oluşturuculara sahip

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
