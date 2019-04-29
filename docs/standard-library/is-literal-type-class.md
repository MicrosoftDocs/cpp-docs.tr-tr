---
title: is_literal_type sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_literal_type
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
ms.openlocfilehash: 804ef0462308b967fc0c4c95d8dfa96476475aab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336473"
---
# <a name="isliteraltype-class"></a>is_literal_type sınıfı

Bir tür olarak kullanılabilir olup olmadığını test bir `constexpr` değişkeni veya oluşturulan, tarafından kullanılan veya döndürüldüğü `constexpr` işlevleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* olduğu bir *değişmez değer türü*, aksi takdirde false tutar. Değişmez değer türü geçerli **void**, skaler bir tür, bir başvuru türü, bir dizi değişmez değer türü veya sınıf değişmez değer türü. Bir değişmez değer sınıfı türü önemsiz bir yok Edicisi olan bir sınıf türü, bir toplama türü veya en az bir olmayan-taşıma, kopyalama olmayan sahip `constexpr` oluşturucusu ve tüm temel sınıflar ve statik olmayan veri üyesi geçici olmayan sabit değer türleri olan. Bir sabit değer türü sabit değer türündeki her zaman olsa da, derleyici olarak değerlendirilmesi için herhangi bir şey değişmez değer türü kavramını içerir bir `constexpr` derleme zamanında.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
