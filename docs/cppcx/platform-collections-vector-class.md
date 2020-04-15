---
title: Platform::Collections::Vector Sınıfı
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
ms.openlocfilehash: b2d08461b4ab57ed8479549c18c35c872d0eb9f1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354379"
---
# <a name="platformcollectionsvector-class"></a>Platform::Collections::Vector Sınıfı

Dizin tarafından tek tek erişilebilen sıralı bir nesne koleksiyonunu temsil eder. Windows [uygular::Foundation::Collections::IObservableVector](/uwp/api/Windows.Foundation.Collections.IObservableVector_T_) XAML [veri bağlama](/windows/uwp/data-binding/data-binding-in-depth)ile yardımcı olmak için .

## <a name="syntax"></a>Sözdizimi

```
template <typename T, typename E>
   ref class Vector sealed;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Vektör nesnesinde bulunan öğelerin türü.

*E*<br/>
*T*türü değerleri ile eşitliği sınalamak için ikili bir yüklem belirtir. Varsayılan `std::equal_to<T>`değer.

### <a name="remarks"></a>Açıklamalar

İzin verilen türleri şunlardır:

1. tamsayılar

1. arayüz sınıfı^

1. kamu ref sınıfı^

1. değer struct

1. public enum sınıfı

**Vektör** [sınıfı, Windows::Foundation::Collections::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_) arabiriminin C++ somut uygulamasıdır.

Genel getiri değeri veya parametrede **vektör** türü kullanmaya çalışırsanız, derleyici hatası C3986 yükseltilir. Parametreyi veya döndürme değer türünü Windows olarak değiştirerek hatayı [düzeltebilirsiniz::Temel::Koleksiyonlar::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_). Daha fazla bilgi için [Bkz. Koleksiyonlar (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Vektör::Vektör](#ctor)|Vektör sınıfının yeni bir örneğini başolarak karşılar.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Vektör::Ek](#append)|Geçerli Vektör'deki son maddeden sonra belirtilen öğeyi ekler.|
|[Vektör::Net](#clear)|Geçerli Vektör'deki tüm öğeleri siler.|
|[Vektör::İlk](#first)|Vektör'deki ilk öğeyi belirten bir yineleyici döndürür.|
|[Vektör::GetAt](#getat)|Belirtilen dizin tarafından tanımlanan geçerli Vektör öğesini alır.|
|[Vektör::GetMany](#getmany)|Belirtilen dizinden başlayarak geçerli Vektör'den bir madde dizisi alır.|
|[Vektör::GetView](#getview)|Bir Vektörün salt okunur görünümünü döndürür; yani, bir [Platform::Koleksiyonlar::VectorView](../cppcx/platform-collections-vectorview-class.md).|
|[Vektör::IndexOf](#indexof)|Geçerli Vektör'de belirtilen öğeyi arar ve bulunursa, maddenin dizinini döndürür.|
|[Vektör::InsertAt](#insertat)|Belirtilen maddeyi belirtilen dizin tarafından tanımlanan öğede geçerli Vektöre ekler.|
|[Vektör::ReplaceAll](#replaceall)|Geçerli Vektör'deki öğeleri siler ve sonra belirtilen diziden öğeleri ekler.|
|[Vektör::Removeat](#removeat)|Belirtilen dizin tarafından tanımlanan öğeyi geçerli Vektör'den siler.|
|[Vektör::Removeatend](#removeatend)|Geçerli Vektör'ün sonundaki öğeyi siler.|
|[Vektör::Setat](#setat)|Belirtilen dizin tarafından tanımlanan geçerli Vektör'deki öğeye belirtilen değeri atar.|
|[Vektör::Boyut](#size)|Geçerli Vektör nesnesindeki öğe sayısını döndürür.|

### <a name="events"></a>Olaylar

|||
|-|-|
|Adı|Açıklama|
|olay [Windows::Foundation::Koleksiyon::VectorChangedEventHandler\<T>^ VectorChanged](/uwp/api/windows.foundation.collections.vectorchangedeventhandler)|Vektör değiştiğinde oluşur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Vector`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** collection.h

**Ad alanı:** Platform::Koleksiyonlar

## <a name="vectorappend-method"></a><a name="append"></a>Vektör::Ek Yöntemi

Geçerli Vektör'deki son maddeden sonra belirtilen öğeyi ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Append(T item);
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Vektör'e eklenecek öğe. *Öğenin* türü *T* türü adı ile tanımlanır.

## <a name="vectorclear-method"></a><a name="clear"></a>Vektör::Net Yöntem

Geçerli Vektör'deki tüm öğeleri siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Clear();
```

## <a name="vectorfirst-method"></a><a name="first"></a>Vektör::İlk Yöntem

Vektör'deki ilk öğeyi işaret eden bir yineleyici döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator <T>^ First();
```

### <a name="return-value"></a>Dönüş Değeri

Vektör'deki ilk öğeyi işaret eden bir yineleyici.

### <a name="remarks"></a>Açıklamalar

First() tarafından döndürülen yineleyiciyi tutmanın kullanışlı bir yolu, otomatik **tür** kesintisi anahtar sözcüğüyle birlikte bildirilen bir değişkene iade değerini atamaktır. Örneğin, `auto x = myVector->First();`. Bu yineleyici koleksiyonun uzunluğunu bilir.

Bir STL işlevine geçmek için bir çift yineleyiciye ihtiyacınız olduğunda, [Windows::Foundation::Collections::Begin](../cppcx/begin-function.md) ve [Windows::Foundation::Collections::end](../cppcx/end-function.md)

## <a name="vectorgetat-method"></a><a name="getat"></a>Vektör::GetAt Yöntemi

Belirtilen dizin tarafından tanımlanan geçerli Vektör öğesini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual T GetAt(unsigned int index);
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Vektör nesnesinde belirli bir öğeyi belirten sıfır tabanlı, imzasız bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri

*Dizin parametresi* tarafından belirtilen öğe. Öğe türü *T* türü ile tanımlanır.

## <a name="vectorgetmany-method"></a><a name="getmany"></a>Vektör::GetMany Yöntemi

Belirtilen diziden başlayarak geçerli Vektör'den bir öğe dizisi alır ve bunları arayan tarafından ayrılan diziye kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual unsigned int GetMany(
    unsigned int startIndex,
    Platform::WriteOnlyArray<T>^ dest);
```

### <a name="parameters"></a>Parametreler

*Startındex*<br/>
Alınacak öğelerin başlangıcının sıfır tabanlı dizin.

*Dest*<br/>
*StartIndex* tarafından belirtilen öğeden başlayan ve Vektör'deki son öğede sona eren bir araya getiren öğe dizisi.

### <a name="return-value"></a>Dönüş Değeri

Alınan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, doğrudan istemci kodu tarafından kullanılmak üzere tasarlanmamıştır. Platform::Vektör intances std::vektör örnekleri verimli dönüştürme sağlamak için [to_vector Fonksiyonu](../cppcx/to-vector-function.md) dahili olarak kullanılır.

## <a name="vectorgetview-method"></a><a name="getview"></a>Vektör::GetView Yöntemi

Bir Vektörün salt okunur görünümünü döndürür; diğer bir iVectorView.

### <a name="syntax"></a>Sözdizimi

```cpp
Windows::Foundation::Collections::IVectorView<T>^ GetView();
```

### <a name="return-value"></a>Dönüş Değeri

Bir IVectorView nesnesi.

## <a name="vectorindexof-method"></a><a name="indexof"></a>Vektör::IndexOf Yöntemi

Geçerli Vektör'de belirtilen öğeyi arar ve bulunursa, maddenin dizinini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual bool IndexOf(T value, unsigned int* index);
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Bulunması gereken öğe.

*Dizin*<br/>
Parametre *değeri* bulunursa maddenin sıfır tabanlı dizini; aksi takdirde, 0.

Madde Vektör'ün ilk öğesiyse veya madde bulunamazsa *dizin parametresi* 0'dır. İade değeri **doğruysa,** öğe bulundu ve ilk öğedir; aksi takdirde, öğe bulunamadı.

### <a name="return-value"></a>Dönüş Değeri

belirtilen öğe bulunursa **geçerlidir;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

IndexOf öğeyi bulmak için std kullanır::find_if. Bu nedenle özel eleman türleri, find_if gerektirdiği eşitlik karşılaştırmalarını etkinleştirmek için == ve != işlecinin aşırı yüklenmesi gerekir.

## <a name="vectorinsertat-method"></a><a name="insertat"></a>Vektör::InsertAt Yöntemi

Belirtilen maddeyi belirtilen dizin tarafından tanımlanan öğede geçerli Vektöre ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void InsertAt(unsigned int index, T item)
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Vektör nesnesinde belirli bir öğeyi belirten sıfır tabanlı, imzasız bir tamsayı.

*Öğe*<br/>
*Dizin*tarafından belirtilen öğede Vektör'e eklenecek bir öğe. *Öğenin* türü *T* türü adı ile tanımlanır.

## <a name="vectorremoveat-method"></a><a name="removeat"></a>Vektör::RemoveAt Yöntemi

Belirtilen dizin tarafından tanımlanan öğeyi geçerli Vektör'den siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void RemoveAt(unsigned int index);
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Vektör nesnesinde belirli bir öğeyi belirten sıfır tabanlı, imzasız bir tamsayı.

## <a name="vectorremoveatend-method"></a><a name="removeatend"></a>Vektör::Removeatend Yöntemi

Geçerli Vektör'ün sonundaki öğeyi siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void RemoveAtEnd();
```

## <a name="vectorreplaceall-method"></a><a name="replaceall"></a>Vektör::ReplaceAll Yöntemi

Geçerli Vektör'deki öğeleri siler ve sonra belirtilen diziden öğeleri ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);
```

### <a name="parameters"></a>Parametreler

*Arr*<br/>
Türü *T* türü adı ile tanımlanan bir nesne dizisi.

## <a name="vectorsetat-method"></a><a name="setat"></a>Vektör::Setat Yöntemi

Belirtilen dizin tarafından tanımlanan geçerli Vektör'deki öğeye belirtilen değeri atar.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void SetAt(unsigned int index, T item);
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Vektör nesnesinde belirli bir öğeyi belirten sıfır tabanlı, imzasız bir tamsayı.

*Öğe*<br/>
Belirtilen öğeye atanacak değer. *Öğenin* türü *T* türü adı ile tanımlanır.

## <a name="vectorsize-method"></a><a name="size"></a>Vektör::Boyut Yöntemi

Geçerli Vektör nesnesindeki öğe sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Vektördeki eleman sayısı.

## <a name="vectorvector-constructor"></a><a name="ctor"></a>Vektör::Vektör Oluşturucu

Vektör sınıfının yeni bir örneğini başolarak karşılar.

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

*A*<br/>
Vektör'ü başharfe getirmek için kullanılacak [bir std::dizi.](../standard-library/array-class-stl.md)

*Arr*<br/>
[Bir Platform::Vektör'ü](../cppcx/platform-array-class.md) başlatmada kullanılacak dizi.

*ınit*<br/>
Geçerli Vektör'ü başlatmak için kullanılan nesne koleksiyonu nun türü.

*ıl*<br/>
Vektörü başlatmada kullanılacak *T* tipi nesnelerin [std::initializer_list.](../standard-library/initializer-list-class.md)

*N*<br/>
Geçerli Vektör'ü başlatmaya kullanılan nesneler koleksiyonundaki öğe sayısı.

*Boyutu*<br/>
Vektördeki eleman sayısı.

*Değer*<br/>
Geçerli Vektör'deki her öğeyi başlatmak için kullanılan bir değer.

*v*<br/>
Geçerli Vektörü başlatmada kullanılan [bir std::vektöre](../standard-library/vector-class.md) bir [Lvalues ve Rvalues.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*Ptr*<br/>
Geçerli Vektör'ü başlatmak için kullanılan bir `std::vector` işaretçi.

*Ilk*<br/>
Geçerli Vektör'ü başlatmak için kullanılan nesneler dizisinin ilk öğesi. *İlk* türü *mükemmel yönlendirme*yoluyla geçirilir. Daha fazla bilgi için [Bkz. Rvalue Başvuru Bildirimcisi: &&. ](../cpp/rvalue-reference-declarator-amp-amp.md)

*Son*<br/>
Geçerli Vektör'ü başlatmada kullanılan nesneler dizisinin son öğesi. *Son* tür *mükemmel yönlendirme*yoluyla geçirilir. Daha fazla bilgi için [Bkz. Rvalue Başvuru Bildirimcisi: &&. ](../cpp/rvalue-reference-declarator-amp-amp.md)

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar (C++/CX)](collections-c-cx.md)<br/>
[Platform İsim Alanı](platform-namespace-c-cx.md)<br/>
[C++'da Windows Runtime Bileşenleri Oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
