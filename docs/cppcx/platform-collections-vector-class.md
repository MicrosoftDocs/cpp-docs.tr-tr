---
title: 'Platform:: Collections:: vector Sınıfı'
ms.date: 12/04/2019
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
helpviewer_keywords:
- Vector Class (C++/Cx)
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
ms.openlocfilehash: b7774c2cdab7b9abcb3ebac1453779055eacf897
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857898"
---
# <a name="platformcollectionsvector-class"></a>Platform:: Collections:: vector Sınıfı

Dizin tarafından tek tek erişilebilen nesnelerin sıralı koleksiyonunu temsil eder. XAML [veri bağlamaya](/windows/uwp/data-binding/data-binding-in-depth)yardımcı olmak için [Windows:: Foundation:: Collections:: IObservableVector](/uwp/api/Windows.Foundation.Collections.IObservableVector_T_) uygular.

## <a name="syntax"></a>Sözdizimi

```
template <typename T, typename E>
   ref class Vector sealed;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Vektör nesnesinde içerilen öğelerin türü.

*E*<br/>
*T*tür değerleriyle eşitlik test etmek için bir ikili koşul belirtir. Varsayılan değer `std::equal_to<T>`.

### <a name="remarks"></a>Açıklamalar

İzin verilen türler şunlardır:

1. tamsayılar

1. arabirim sınıfı ^

1. ortak başvuru sınıfı ^

1. değer yapısı

1. ortak enum sınıfı

**Vector** sınıfı, C++ [Windows:: Foundation:: Collections:: IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_) arabiriminin somut uygulamasıdır.

Bir ortak dönüş değeri veya parametresinde bir **vektör** türü kullanmaya çalışırsanız, derleyici hatası C3986 tetiklenir. Bu hatayı, parametre veya dönüş değeri türünü [Windows:: Foundation:: Collections:: IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_)olarak değiştirerek çözebilirsiniz. Daha fazla bilgi için bkz. [koleksiyonlarC++(/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[Vector:: vector](#ctor)|Vektör sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Genel Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[Vector:: Append](#append)|Geçerli Vektördeki son öğeden sonra belirtilen öğeyi ekler.|
|[Vector:: Clear](#clear)|Geçerli Vektördeki tüm öğeleri siler.|
|[Vector:: First](#first)|Vektördeki ilk öğeyi belirten bir yineleyici döndürür.|
|[Vector:: GetAt](#getat)|Belirtilen dizin tarafından belirlenen geçerli vektörün öğesini alır.|
|[Vector:: GetMany](#getmany)|Belirtilen dizinden başlayarak, geçerli vektörden bir öğe dizisi alır.|
|[Vector:: GetView](#getview)|Bir vektörün salt okunurdur görünümünü döndürür; diğer bir deyişle, bir [Platform:: Collections:: VectorView](../cppcx/platform-collections-vectorview-class.md).|
|[Vector:: IndexOf](#indexof)|Geçerli vektörde belirtilen öğeyi arar ve bulunursa öğenin dizinini döndürür.|
|[Vector:: InsertAt](#insertat)|Belirtilen öğeyi belirtilen dizin tarafından tanımlanan öğedeki geçerli vektöre ekler.|
|[Vector:: ReplaceAll](#replaceall)|Geçerli Vektördeki öğeleri siler ve ardından belirtilen diziden öğeleri ekler.|
|[Vector:: RemoveAt](#removeat)|Geçerli vektörden belirtilen dizin tarafından tanımlanan öğeyi siler.|
|[Vector:: RemoveAtEnd](#removeatend)|Geçerli vektörün sonundaki öğeyi siler.|
|[Vector:: SetAt](#setat)|Belirtilen dizin tarafından tanımlanan geçerli vektörde bulunan öğeye belirtilen değeri atar.|
|[Vector:: size](#size)|Geçerli vektör nesnesindeki öğe sayısını döndürür.|

### <a name="events"></a>Olaylar

|||
|-|-|
|Name|Açıklama|
|olay [Windows:: Foundation:: Collection:: VectorChangedEventHandler\<t > ^ Vektörtorchanged](/uwp/api/windows.foundation.collections.vectorchangedeventhandler)|Vektör değiştiğinde gerçekleşir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Vector`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="append"></a>Vector:: Append yöntemi

Geçerli Vektördeki son öğeden sonra belirtilen öğeyi ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Append(T item);
```

### <a name="parameters"></a>Parametreler

*indeks*<br/>
Vektöre eklenecek öğe. *Öğe* türü *T* TypeName tarafından tanımlanır.

## <a name="clear"></a>Vector:: Clear yöntemi

Geçerli Vektördeki tüm öğeleri siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Clear();
```

## <a name="first"></a>Vector:: First yöntemi

Vektördeki ilk öğeyi gösteren bir yineleyici döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator <T>^ First();
```

### <a name="return-value"></a>Dönüş Değeri

Vektördeki ilk öğeyi gösteren bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Ilk () tarafından döndürülen yineleyiciyi tutmanın uygun bir yolu, dönüş değerini **Auto** Type kesintisi anahtar sözcüğüyle belirtilen bir değişkene atamaktır. Örneğin: `auto x = myVector->First();`. Bu Yineleyici, koleksiyonun uzunluğunu bilir.

STL işlevine geçebileceğiniz bir çift yineleyiciye ihtiyacınız olduğunda, ücretsiz işlevler [Windows:: Foundation:: Collections:: Begin](../cppcx/begin-function.md) ve [Windows:: Foundation:: Collections:: End](../cppcx/end-function.md) ' i kullanın.

## <a name="getat"></a>Vector:: GetAt yöntemi

Belirtilen dizin tarafından belirlenen geçerli vektörün öğesini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual T GetAt(unsigned int index);
```

### <a name="parameters"></a>Parametreler

*indeks*<br/>
Vektör nesnesinde belirli bir öğeyi belirten sıfır tabanlı, işaretsiz bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri

*Dizin* parametresi tarafından belirtilen öğe. Öğe türü *T* TypeName tarafından tanımlanır.

## <a name="getmany"></a>Vector:: GetMany yöntemi

Belirtilen dizinden başlayarak, geçerli vektörden bir öğe dizisi alır ve bunları arayan tarafından ayrılan diziye kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual unsigned int GetMany(
    unsigned int startIndex,
    Platform::WriteOnlyArray<T>^ dest);
```

### <a name="parameters"></a>Parametreler

*startIndex*<br/>
Alınacak öğelerin başlangıcına ait sıfır tabanlı dizin.

*HD*<br/>
*StartIndex* tarafından belirtilen öğede başlayan ve Vektördeki son öğede biten, çağıran bir öğe dizisi.

### <a name="return-value"></a>Dönüş Değeri

Alınan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu işlev doğrudan istemci kodu tarafından kullanılmaya yönelik değildir. Platform:: vector örneklerinin std:: vector örneklerine etkin dönüştürülmesini sağlamak için [To_vector işlevinde](../cppcx/to-vector-function.md) dahili olarak kullanılır.

## <a name="getview"></a>Vector:: GetView yöntemi

Bir vektörün salt okunurdur görünümünü döndürür; diğer bir deyişle, bir ıvectorview.

### <a name="syntax"></a>Sözdizimi

```cpp
Windows::Foundation::Collections::IVectorView<T>^ GetView();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ıvectorview nesnesi.

## <a name="indexof"></a>Vector:: IndexOf yöntemi

Geçerli vektörde belirtilen öğeyi arar ve bulunursa öğenin dizinini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual bool IndexOf(T value, unsigned int* index);
```

### <a name="parameters"></a>Parametreler

*value*<br/>
Bulunacak öğe.

*indeks*<br/>
Parametre *değeri* bulunursa öğenin sıfır tabanlı dizini; Aksi takdirde, 0.

Öğe vektör 'in ilk öğesi ise veya öğe bulunmazsa *Dizin* parametresi 0 ' dır. Dönüş değeri **true**ise, öğe bulundu ve ilk öğedir; Aksi takdirde, öğe bulunamadı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe bulunursa **true** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

IndexOf, öğeyi bulmak için std:: find_if kullanır. Bu nedenle, find_if gerektirdiği eşitlik karşılaştırmalarını etkinleştirmek için özel öğe türleri = = ve! = işlecini aşırı yüklemelidir.

##  <a name="insertat"></a>Vector:: InsertAt yöntemi

Belirtilen öğeyi belirtilen dizin tarafından tanımlanan öğedeki geçerli vektöre ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void InsertAt(unsigned int index, T item)
```

### <a name="parameters"></a>Parametreler

*indeks*<br/>
Vektör nesnesinde belirli bir öğeyi belirten sıfır tabanlı, işaretsiz bir tamsayı.

*maddesinin*<br/>
*Dizinle*belirtilen öğede vector öğesine eklenecek bir öğe. *Öğe* türü *T* TypeName tarafından tanımlanır.

## <a name="removeat"></a>Vector:: RemoveAt yöntemi

Geçerli vektörden belirtilen dizin tarafından tanımlanan öğeyi siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void RemoveAt(unsigned int index);
```

### <a name="parameters"></a>Parametreler

*indeks*<br/>
Vektör nesnesinde belirli bir öğeyi belirten sıfır tabanlı, işaretsiz bir tamsayı.

## <a name="removeatend"></a>Vector:: RemoveAtEnd yöntemi

Geçerli vektörün sonundaki öğeyi siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void RemoveAtEnd();
```

## <a name="replaceall"></a>Vector:: ReplaceAll yöntemi

Geçerli Vektördeki öğeleri siler ve ardından belirtilen diziden öğeleri ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);
```

### <a name="parameters"></a>Parametreler

*ARR*<br/>
Türü *T* TypeName tarafından tanımlanan bir nesne dizisi.

## <a name="setat"></a>Vector:: SetAt yöntemi

Belirtilen dizin tarafından tanımlanan geçerli vektörde bulunan öğeye belirtilen değeri atar.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void SetAt(unsigned int index, T item);
```

### <a name="parameters"></a>Parametreler

*indeks*<br/>
Vektör nesnesinde belirli bir öğeyi belirten sıfır tabanlı, işaretsiz bir tamsayı.

*maddesinin*<br/>
Belirtilen öğeye atanacak değer. *Öğe* türü *T* TypeName tarafından tanımlanır.

## <a name="size"></a>Vector:: size yöntemi

Geçerli vektör nesnesindeki öğe sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Vektördeki öğe sayısı.

## <a name="ctor"></a>Vector:: vector Oluşturucusu

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

*a*<br/>
Vektörü başlatmak için kullanılacak [std:: Array](../standard-library/array-class-stl.md) .

*ARR*<br/>
Vektörü başlatmak için kullanılacak [Platform:: Array](../cppcx/platform-array-class.md) .

*Dengeleyici*<br/>
Geçerli vektörü başlatmak için kullanılan nesne koleksiyonunun türü.

*Demiryolu*<br/>
Vektör 'yi başlatmak için kullanılacak *T* türünde nesnelerin [std:: initializer_list](../standard-library/initializer-list-class.md) .

*N*<br/>
Geçerli vektörü başlatmak için kullanılan nesne koleksiyonundaki öğe sayısı.

*boyutla*<br/>
Vektördeki öğe sayısı.

*value*<br/>
Geçerli vektörde her öğeyi başlatmak için kullanılan bir değer.

*v*<br/>
Geçerli vektörü başlatmak için kullanılan [std:: vector](../standard-library/vector-class.md) öğesine bir [lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) .

*ptr*<br/>
Geçerli vektörü başlatmak için kullanılan bir `std::vector` işaretçisi.

*first*<br/>
Geçerli vektörü başlatmak için kullanılan nesne dizisindeki ilk öğe. *İlk* türü *kusursuz iletme*yoluyla geçirilir. Daha fazla bilgi için bkz. [rvalue başvuru bildirimci: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

*last*<br/>
Geçerli vektörü başlatmak için kullanılan nesneler dizisindeki son öğe. *Son* türü, *kusursuz iletme*yoluyla geçirilir. Daha fazla bilgi için bkz. [rvalue başvuru bildirimci: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar (C++/CX)](collections-c-cx.md)<br/>
[Platform ad alanı](platform-namespace-c-cx.md)<br/>
[İçinde Windows Çalışma Zamanı bileşenleri oluşturmaC++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
