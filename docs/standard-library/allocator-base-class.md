---
title: allocator_base sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/stdext::allocator_base
- allocators/stdext::allocators::allocator_base
- allocators/stdext::allocator_base::const_pointer
- allocators/stdext::allocator_base::const_reference
- allocators/stdext::allocator_base::difference_type
- allocators/stdext::allocator_base::pointer
- allocators/stdext::allocator_base::reference
- allocators/stdext::allocator_base::size_type
- allocators/stdext::allocator_base::value_type
- allocators/stdext::allocator_base::_Charalloc
- allocators/stdext::allocator_base::_Chardealloc
- allocators/stdext::allocator_base::address
- allocators/stdext::allocator_base::allocate
- allocators/stdext::allocator_base::construct
- allocators/stdext::allocator_base::deallocate
- allocators/stdext::allocator_base::destroy
- allocators/stdext::allocator_base::max_size
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocator_base [C++]
- stdext::allocators [C++], allocator_base
- stdext::allocator_base [C++], const_pointer
- stdext::allocator_base [C++], const_reference
- stdext::allocator_base [C++], difference_type
- stdext::allocator_base [C++], pointer
- stdext::allocator_base [C++], reference
- stdext::allocator_base [C++], size_type
- stdext::allocator_base [C++], value_type
- stdext::allocator_base [C++], _Charalloc
- stdext::allocator_base [C++], _Chardealloc
- stdext::allocator_base [C++], address
- stdext::allocator_base [C++], allocate
- stdext::allocator_base [C++], construct
- stdext::allocator_base [C++], deallocate
- stdext::allocator_base [C++], destroy
- stdext::allocator_base [C++], max_size
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6b4509b426a8d7371c194cf14d95f83c64683067
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="allocatorbase-class"></a>allocator_base Sınıfı

Kullanıcı tanımlı bir ayırıcı eşitleme filtresi oluşturmak için gereken genel işlevler ve temel sınıf tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Sync>
class allocator_base
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Type`|Ayırıcı tarafından ayrılan öğelerin türü.|
|`Sync`|Eşitleme ilkesi olan ayırıcısı için [sync_none sınıfı](../standard-library/sync-none-class.md), [sync_per_kapsayıcı sınıfı](../standard-library/sync-per-container-class.md), [sync_per_thread sınıfı](../standard-library/sync-per-thread-class.md), veya [sync_shared Sınıf](../standard-library/sync-shared-class.md).|

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[allocator_base](#allocator_base)|Türünde bir nesne oluşturur `allocator_base`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[const_pointer](#const_pointer)|Ayırıcı tarafından yönetilen nesne türü için sabit bir işaretçi sağlayan türü.|
|[const_reference](#const_reference)|Ayırıcı tarafından yönetilen nesne türü için sabit bir başvuru sağlar türü.|
|[difference_type](#difference_type)|Ayırıcı tarafından yönetilen nesne türü işaretçileri değerler arasındaki farkın gösterebilir imzalı tam sayı türü.|
|[İşaretçi](#pointer)|Ayırıcı tarafından yönetilen nesne türü için bir işaretçi sağlayan türü.|
|[Başvuru](#reference)|Ayırıcı tarafından yönetilen nesne türü için bir başvuru sağlar türü.|
|[size_type](#size_type)|Herhangi bir uzunluğunu temsil edebilen imzasız tamsayı türü sıra şablon sınıfın bir nesnesi `allocator_base` ayırabilirsiniz.|
|[value_type](#value_type)|Ayırıcı tarafından yönetilen türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[_Charalloc](#charalloc)|Depolama türü için bir dizi ayırır `char`.|
|[_Chardealloc](#chardealloc)|Türündeki öğeler içeren bir dizi için depolama boşaltır `char`.|
|[Adres](#address)|Değeri belirtilen bir nesne adresini bulur.|
|[allocate](#allocate)|Bir en az bazı belirtilen sayıda öğeyi depolamak için büyük bellek bloğu ayırır.|
|[Yapı](#construct)|Belirli bir nesne belirli bir değerle başlatılır belirtilen adresteki türünü oluşturur.|
|[Serbest bırakma](#deallocate)|Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.|
|[yok](#destroy)|Nesneleri yok Edicisi bellek ayırmayı kaldırma olmadan nesne saklandığı çağırır.|
|[max_size](#max_size)|Türündeki öğe sayısını döndürür `Type` , ayrılan bir sınıf ayırıcısı nesnesiyle boş bellek kullanılmadan önce.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<allocators >

**Namespace:** stdext

## <a name="charalloc"></a>  allocator_base::_Charalloc

Depolama türü için bir dizi ayırır `char`.

```cpp
char *_Charalloc(size_type count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`count`|Ayrılacak dizideki öğelerin sayısı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yeniden bağlamasını derlenemiyor bir derleyici ile derlendiğinde kapsayıcıları tarafından kullanılır. Bunu uygulayan `_Charalloc` yapılan bir çağrı sonucunu döndürerek kullanıcı tanımlı ayırıcısı için `allocate` eşitleme filtresi işlevi.

## <a name="chardealloc"></a>  allocator_base::_Chardealloc

Türündeki öğeler içeren bir dizi için depolama boşaltır `char`.

```cpp
void _Chardealloc(void* ptr, size_type count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`ptr`|Depolama biriminden bırakılmasına ilk nesne için bir işaretçi.|
|`count`|Depolama biriminden bırakılmasına nesnelerin sayısı.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yeniden bağlamasını derlenemiyor bir derleyici ile derlendiğinde kapsayıcıları tarafından kullanılır. Bunu uygulayan `_Chardealloc` çağırarak kullanıcı tanımlı ayırıcısı için `deallocate` eşitleme filtresi işlevi. İşaretçi ptr daha önce bir çağrı tarafından verilinceye gerekir `_Charalloc` eşit karşılaştırır ayırıcısı nesnenin `*this`, bir dizi nesnesi aynı boyut ve tür ayrılıyor. `_Chardealloc` hiçbir zaman bir özel durum oluşturur.

## <a name="address"></a>  allocator_base::Address

Değeri belirtilen bir nesne adresini bulur.

```cpp
pointer address(reference val);

const_pointer address(const_reference val);
```

### <a name="parameters"></a>Parametreler

`val` Adresini aranır nesnenin const veya nonconst değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir const veya nesnesine nonconst işaretçi sırasıyla const veya nonconst değeri, bulundu.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi için kullanıcı tanımlı ayırıcısı döndürerek uygulanan `&val`.

## <a name="allocate"></a>  allocator_base::allocate

Bir en az bazı belirtilen sayıda öğeyi depolamak için büyük bellek bloğu ayırır.

```cpp
template <class Other>
pointer allocate(size_type _Nx, const Other* _Hint = 0);

pointer allocate(size_type _Nx);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`_Nx`|Ayrılacak dizideki öğelerin sayısı.|
|`_Hint`|Bu parametre yoksayıldı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi için bir çağrı sonucunu döndürerek kullanıcı tanımlı ayırıcısı için bellek ayırma uygulayan `allocate` işlevi türü eşitleme filtresinin `*` varsa `_Nx == 1`, aksi takdirde sonucu döndürerek bir çağrısı `operator new(_Nx * sizeof(Type))` türünü cast `*`.

## <a name="allocator_base"></a>  allocator_base::allocator_base

Türünde bir nesne oluşturur `allocator_base`.

```cpp
allocator_base();

template <class Other>
allocator_base(const allocator_base<Other, Sync>& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`right`|Kopyalanacak ayırıcısı nesnesi.|

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu yapıları bir [allocator_base](../standard-library/allocator-base-class.md) örneği. İkinci oluşturucu yapıları bir `allocator_base` gibi örnek herhangi için `allocator_base<Type, _Sync>` örneği `a`, `allocator_base<Type, Sync>(allocator_base<Other, Sync>(a)) == a`.

## <a name="const_pointer"></a>  allocator_base::const_pointer

Ayırıcı tarafından yönetilen nesne türü için sabit bir işaretçi sağlayan türü.

```cpp
typedef const Type *const_pointer;
```

## <a name="const_reference"></a>  allocator_base::const_reference

Ayırıcı tarafından yönetilen nesne türü için sabit bir başvuru sağlar türü.

```cpp
typedef const Type& const_reference;
```

## <a name="construct"></a>  allocator_base::Construct

Belirli bir nesne belirli bir değerle başlatılır belirtilen adresteki türünü oluşturur.

```cpp
void construct(pointer ptr, const Type& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`ptr`|Nesne oluşturulması bulunduğu konuma bir işaretçi.|
|`val`|Yapılandırılan bir nesne başlatılması olduğu değeri.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırarak için kullanıcı tanımlı ayırıcısı uygulanır `new((void*)ptr Type(val)`.

## <a name="deallocate"></a>  allocator_base::deallocate

Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.

```cpp
void deallocate(pointer ptr, size_type _Nx);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`ptr`|Depolama biriminden bırakılmasına ilk nesne için bir işaretçi.|
|`_Nx`|Depolama biriminden bırakılmasına nesnelerin sayısı.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırarak için kullanıcı tanımlı ayırıcısı uygulanır `deallocate(ptr)` eşitleme filtresini `Sync` varsa `_Nx == 1`, aksi takdirde çağırarak `operator delete(_Nx * ptr)`.

## <a name="destroy"></a>  allocator_base::Destroy

Nesneleri yok Edicisi bellek ayırmayı kaldırma olmadan nesne saklandığı çağırır.

```cpp
void destroy(pointer ptr);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`ptr`|Bir işaretçi yok edilmesi nesnesine adresini belirleme.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırarak için kullanıcı tanımlı ayırıcısı uygulanır `ptr->~Type()`.

## <a name="difference_type"></a>  allocator_base::difference_type

Ayırıcı tarafından yönetilen nesne türü işaretçileri değerler arasındaki farkın gösterebilir imzalı tam sayı türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

## <a name="max_size"></a>  allocator_base::max_size

Türündeki öğe sayısını döndürür `Type` , ayrılan bir sınıf ayırıcısı nesnesiyle boş bellek kullanılmadan önce.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılamadı öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi için kullanıcı tanımlı ayırıcısı döndürerek uygulanan `(size_t)-1 / sizeof(Type)` varsa `0 < (size_t)-1 / sizeof(Type)`, aksi takdirde `1`.

## <a name="pointer"></a>  allocator_base::pointer

Ayırıcı tarafından yönetilen nesne türü için bir işaretçi sağlayan türü.

```cpp
typedef Type *pointer;
```

## <a name="reference"></a>  allocator_base::Reference

Ayırıcı tarafından yönetilen nesne türü için bir başvuru sağlar türü.

```cpp
typedef Type& reference;
```

## <a name="size_type"></a>  allocator_base::size_type

Herhangi bir uzunluğunu temsil edebilen imzasız tamsayı türü sıra şablon sınıfın bir nesnesi `allocator_base` ayırabilirsiniz.

```cpp
typedef std::size_t size_type;
```

## <a name="value_type"></a>  allocator_base::value_type

Ayırıcı tarafından yönetilen türü.

```cpp
typedef Type value_type;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)<br/>
