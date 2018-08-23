---
title: 'Platform::Collections:: Vector Class | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Vector::Vector
- COLLECTION/Platform::Collections::Vector::Append
- COLLECTION/Platform::Collections::Vector::Clear
- COLLECTION/Platform::Collections::Vector::First
- COLLECTION/Platform::Collections::Vector::GetAt
- COLLECTION/Platform::Collections::Vector::GetMany
- COLLECTION/Platform::Collections::Vector::GetView
- COLLECTION/Platform::Collections::Vector::IndexOf
- COLLECTION/Platform::Collections::Vector::InsertAt
- COLLECTION/Platform::Collections::Vector::ReplaceAll
- COLLECTION/Platform::Collections::Vector::RemoveAt
- COLLECTION/Platform::Collections::Vector::RemoveAtEnd
- COLLECTION/Platform::Collections::Vector::SetAt
- COLLECTION/Platform::Collections::Vector::Size
- COLLECTION/Platform::Collections::Vector::VectorChanged
dev_langs:
- C++
helpviewer_keywords:
- Vector Class (C++/Cx)
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 550a1e40d3fee80b4c9666457a60772ed49b580a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590241"
---
# <a name="platformcollectionsvector-class"></a>Platform::Collections:: Vector sınıfı

Tek tek dizin tarafından erişilebilen nesneler için sıralı bir koleksiyonu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <typename T, typename E>
   ref class Vector sealed;
```

### <a name="parameters"></a>Parametreler

*T*  
Vektör nesnesinde yer alan öğelerin türü.

*E*  
Türündeki değerlerle eşitlik testi için bir ikili koşula belirtir *T*. Varsayılan değer `std::equal_to<T>` şeklindedir.

### <a name="remarks"></a>Açıklamalar

İzin verilen türleri şunlardır:

1. tamsayılar

1. arabirim sınıfı ^

1. Genel başvuru sınıfı ^

1. değer yapısı

1. Genel sabit listesi sınıfı

**Vektör** sınıfı, C++ somut uygulamasını [Windows::Foundation::Collections::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_) arabirimi.

Kullanmayı denerseniz bir **vektör** türü ortak dönüş değeri veya parametre, derleyici hatası C3986 oluşturulur. Parametre değiştirerek hatayı düzeltin ya da dönüş değeri türüne [Windows::Foundation::Collections::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_). Daha fazla bilgi için [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Vector::Vector](#ctor)|Vektör sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Vector::Append](#append)|Geçerli bir vektör içindeki son öğeden sonra belirtilen öğeyi ekler.|
|[Vector::Clear](#clear)|Geçerli vektör tüm öğeleri siler.|
|[Vector::First](#first)|Vektör ilk öğeyi belirten bir yineleyici döndürür.|
|[Vector::GetAt](#getat)|İdentifed belirtilen dizine göre olan geçerli vektör öğesinin alır.|
|[Vector::GetMany](#getmany)|Belirtilen dizinden başlayarak geçerli vektör öğelerinin bir dizisini alır.|
|[Vector::GetView](#getview)|Bir vektör salt okunur bir görünümünü verir. diğer bir deyişle, bir [Platform::Collections:: vectorview](../cppcx/platform-collections-vectorview-class.md).|
|[Vector::IndexOf](#indexof)|Belirtilen öğe geçerli vektördeki arar ve bulundu, döndürür öğenin dizini.|
|[Vector::InsertAt](#insertat)|Belirtilen öğe geçerli vektöre sonra tarafından belirtilen dizine belirtilen öğeyi ekler.|
|[Vector::ReplaceAll](#replaceall)|Geçerli vektör öğeleri siler ve sonra belirtilen diziden öğeleri ekler.|
|[Vector::RemoveAt](#removeat)|Belirtilen dizinden geçerli vektör tarafından tanımlanan öğeyi silin.|
|[Vector::RemoveAtEnd](#removeatend)|Geçerli vektör sonundaki öğeyi silin.|
|[Vector::SetAt](#setat)|Belirtilen dizin tarafından tanımlanan geçerli vektör öğesine belirtilen değeri atar.|
|[Vector::size](#size)|Geçerli bir vektör nesnesi öğelerin sayısını döndürür.|

### <a name="events"></a>Olaylar

|||
|-|-|
|Ad|Açıklama|
|olay [Windows::Foundation::Collection::VectorChangedEventHandler\<T > ^ VectorChanged](http://go.microsoft.com/fwlink/p/?LinkId=262644)|Vektör değiştiğinde gerçekleşir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Vector`

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Platform::Collections

## <a name="append"></a>  Vector::Append yöntemi

Geçerli bir vektör içindeki son öğeden sonra belirtilen öğeyi ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Append(T item);
```

### <a name="parameters"></a>Parametreler

*Dizin*  
Vektöre eklenecek öğe. Türünü *öğesi* tarafından tanımlanan *T* typename.

## <a name="clear"></a>  Vector::Clear yöntemi

Geçerli vektör tüm öğeleri siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Clear();
```

## <a name="first"></a>  Vector::First yöntemi

Bir yineleyicinin vektör içindeki ilk öğeye döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator <T>^ First();
```

### <a name="return-value"></a>Dönüş Değeri

Vektör içindeki ilk öğeyi gösteren bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile bildirilen bir değişken atamak First() tarafından döndürülen yineleyici tutmak için kullanışlı bir yol olan **otomatik** kesinti anahtar sözcüğü yazın. Örneğin, `auto x = myVector->First();`. Bu yineleyici koleksiyonu uzunluğunu bilir.

Bir STL işleve Yineleyicilerin bir çiftini gerektiğinde ücretsiz işlevleri kullanmak [Windows::Foundation:: Collections:: başlamak](../cppcx/begin-function.md) ve [Windows::Foundation::Collections::end](../cppcx/end-function.md)

## <a name="getat"></a>  Vector::GetAt yöntemi

İdentifed belirtilen dizine göre olan geçerli vektör öğesinin alır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual T GetAt(unsigned int index);
```

### <a name="parameters"></a>Parametreler

*Dizin*  
Belirli bir öğenin vektör nesnesi belirtir. sıfır tabanlı, işaretsiz bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen öğenin *dizin* parametresi. Öğe türü tarafından tanımlanan *T* typename.

## <a name="getmany"></a>  Vector::GetMany yöntemi

Belirtilen dizinden başlayarak geçerli vektör öğelerinin bir dizisini alır ve bunları arayana ayrılan dizi içine kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual unsigned int GetMany(
    unsigned int startIndex,
    Platform::WriteOnlyArray<T>^ dest);
```

### <a name="parameters"></a>Parametreler

*startIndex*  
Alınacak öğelerin başladığı sıfır tabanlı dizini.

*Hedef*  
Belirtilen öğede başlayan öğeleri arayana ayrılan dizi *startIndex* ve vektör içindeki son öğeden sonunda.

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısını alınır.

### <a name="remarks"></a>Açıklamalar

Bu işlev, doğrudan istemci kodu tarafından kullanılmak üzere tasarlanmamıştır. Buna dahili olarak kullanılan [to_vector işlevi](../cppcx/to-vector-function.md) verimli dönüştürülmesi std::vector örnekleri Platform::Vector uygulamalara sağlamak.

## <a name="getview"></a>  Vector::GetView yöntemi

Bir vektör salt okunur bir görünümünü verir. diğer bir deyişle, bir IVectorView.

### <a name="syntax"></a>Sözdizimi

```cpp
Windows::Foundation::Collections::IVectorView<T>^ GetView();
```

### <a name="return-value"></a>Dönüş Değeri

IVectorView nesne.

## <a name="indexof"></a>  Vector::IndexOf yöntemi

Belirtilen öğe geçerli vektördeki arar ve bulundu, döndürür öğenin dizini.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual bool IndexOf(T value, unsigned int* index);
```

### <a name="parameters"></a>Parametreler

*value*  
Bulunacak öğe.

*Dizin*  
Öğenin sıfır tabanlı dizini, parametre *değer* bulundu; Aksi takdirde, 0.

*Dizin* parametresi ise 0 öğe vektör ilk öğesidir ya da öğe bulunamadı. Dönüş değeri ise `true`, öğe bulundu ve ilk öğedir; Aksi takdirde, öğe bulunamadı.

### <a name="return-value"></a>Dönüş Değeri

`true` Belirtilen öğe bulunursa; Aksi takdirde, `false`.

### <a name="remarks"></a>Açıklamalar

IndexOf std::find_if öğeyi bulmak için kullanır. Özel öğe türleri == dolayısıyla aşırı ve! = işleci eşitlik etkinleştirmek için bu find_if karşılaştırma gerektirir.

##  <a name="insertat"></a>  Vector::InsertAt yöntemi

Belirtilen öğe geçerli vektöre sonra tarafından belirtilen dizine belirtilen öğeyi ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void InsertAt(unsigned int index, T item)
```

### <a name="parameters"></a>Parametreler

*Dizin*  
Belirli bir öğenin vektör nesnesi belirtir. sıfır tabanlı, işaretsiz bir tamsayı.

*Öğesi*  
Bir öğe tarafından belirtilen öğenin sonra vektöre Ekle *dizin*. Türünü *öğesi* tarafından tanımlanan *T* typename.

## <a name="removeat"></a>  Vector::RemoveAt yöntemi

Belirtilen dizinden geçerli vektör tarafından tanımlanan öğeyi silin.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void RemoveAt(unsigned int index);
```

### <a name="parameters"></a>Parametreler

*Dizin*  
Belirli bir öğenin vektör nesnesi belirtir. sıfır tabanlı, işaretsiz bir tamsayı.

## <a name="removeatend"></a>  Vector::RemoveAtEnd yöntemi

Geçerli vektör sonundaki öğeyi silin.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void RemoveAtEnd();
```

## <a name="replaceall"></a>  Vector::ReplaceAll yöntemi

Geçerli vektör öğeleri siler ve sonra belirtilen diziden öğeleri ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);
```

### <a name="parameters"></a>Parametreler

*arr*  
Bir dizi türü tarafından tanımlanan nesnelerin *T* typename.

## <a name="setat"></a>  Vector::SetAt yöntemi

Belirtilen dizin tarafından tanımlanan geçerli vektör öğesine belirtilen değeri atar.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void SetAt(unsigned int index, T item);
```

### <a name="parameters"></a>Parametreler

*Dizin*  
Belirli bir öğenin vektör nesnesi belirtir. sıfır tabanlı, işaretsiz bir tamsayı.

*Öğesi*  
Belirtilen öğe için atanacak değer. Türünü *öğesi* tarafından tanımlanan *T* typename.

## <a name="size"></a>  Vector::size yöntemi

Geçerli bir vektör nesnesi öğelerin sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli vektördeki öğe sayısı.

## <a name="ctor"></a>  Vector::Vector Oluşturucusu

Vektör sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
Vector();

explicit Vector(unsigned int size);
Vector( unsigned int size, T value);
template <typename U> explicit Vector( const ::std::vector<U>& v);
template <typename U> explicit Vector( std::vector<U>&& v);

Vector( const T * ptr, unsigned int size);
template <size_t N> explicit Vector(const T(&arr)[N]);
template <size_t N> explicit Vector(const std::array<T, N>& a);
explicit Vector(const Array<T>^ arr);

template <typename InIt> Vector(InIt first, InIt last);
Vector(std::initializer_list<T> il);
```

### <a name="parameters"></a>Parametreler

*a*  
A [std::array](../standard-library/array-class-stl.md) vektör başlatmak için kullanılır.

*arr*  
A [Platform::Array](../cppcx/platform-array-class.md) vektör başlatmak için kullanılır.

*InIt*  
Geçerli vektör başlatmak için kullanılan bir koleksiyon nesnelerin türü.

*IL*  
A [std::initializer_list](../standard-library/initializer-list-class.md) türünde nesne *T* vektör başlatmak için kullanılır.

*N*  
Bir koleksiyondaki öğeleri geçerli vektör başlatmak için kullanılan nesnelerin sayısı.

*Boyutu*  
Vektördeki öğe sayısı.

*value*  
Geçerli bir vektör içindeki her öğeyi başlatmak için kullanılan bir değer.

*v*  
Bir [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir [std::vector](../standard-library/vector-class.md) geçerli vektör başlatmak için kullanılır.

*ptr*  
İşaretçi bir `std::vector` geçerli vektör başlatmak için kullanılır.

*ilk*  
Geçerli vektör başlatmak için kullanılan nesnelerin bir dizideki ilk öğe. Türünü *ilk* yoluyla geçirilen *kusursuz iletme*. Daha fazla bilgi için [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

*Son*  
Son öğeden bir dizideki nesnelerin geçerli vektör başlatmak için kullanılır. Türünü *son* yoluyla geçirilen *kusursuz iletme*. Daha fazla bilgi için [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Platform Namespace](platform-namespace-c-cx.md)  
[C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)  