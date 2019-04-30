---
title: is_trivially_default_constructible Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_default_constructible
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
ms.openlocfilehash: b35458ca280285eb699c9b12b15b705660299ef2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413417"
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
