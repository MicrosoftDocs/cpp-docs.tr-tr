---
title: Platform::Collections::VectorView Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
helpviewer_keywords:
- VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
ms.openlocfilehash: 7f12c7b926cd8d3d8fc892cff6f2245e7c216219
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032232"
---
# <a name="platformcollectionsvectorview-class"></a>Platform::Collections::VectorView Sınıfı

Dizin tarafından tek tek erişilebilen sıralı nesne koleksiyonunun salt okunur görünümünü temsil eder. Koleksiyondaki her nesnenin türü şablon parametresi tarafından belirtilir.

## <a name="syntax"></a>Sözdizimi

```
template <typename T, typename E>
   ref class VectorView sealed;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
`VectorView` Nesnede bulunan öğelerin türü.

*E*<br/>
Türü değerleri ile eşitliği test etmek için ikili `T`bir yüklem belirtir. Varsayılan değer: `std::equal_to<T>`.

### <a name="remarks"></a>Açıklamalar

Sınıf `VectorView` [Windows:Foundation::Collections::IVectorView\<T>](/uwp/api/windows.foundation.collections.ivectorview-1) arabirimi ve Standart Şablon Kitaplığı yineleyicileri için destek uygular.

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[VectorView::VectorView](#ctor)|VectorView sınıfının yeni bir örneğini başolarak karşılar.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[VectorView::İlk](#first)|VectorView'daki ilk öğeyi belirten bir yineleyici döndürür.|
|[VectorView::GetAt](#getat)|Belirtilen dizin tarafından belirtilen geçerli VectorView öğesini alır.|
|[VectorView::GetMany](#getmany)|Belirtilen dizinden başlayarak geçerli VectorView'den bir öğe dizisi alır.|
|[VectorView::IndexOf](#indexof)|Geçerli VectorView'de belirtilen öğeyi arar ve bulunursa, öğenin dizinini döndürür.|
|[VectorView::Boyut](#size)|Geçerli VectorView nesnesindeki öğe sayısını döndürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VectorView`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** collection.h

**Ad alanı:** Platform::Koleksiyonlar

## <a name="vectorviewfirst-method"></a><a name="first"></a>VectorView::İlk Yöntem

VectorView'daki ilk öğeyi belirten bir yineleyici döndürür.

### <a name="syntax"></a>Sözdizimi

```

virtual Windows::Foundation::Collections::IIterator<T>^
   First();
```

### <a name="return-value"></a>Dönüş Değeri

VectorView'daki ilk öğeyi belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

First() tarafından döndürülen yineleyiciyi tutmanın kullanışlı bir yolu, otomatik **tür** kesintisi anahtar sözcüğüyle birlikte bildirilen bir değişkene iade değerini atamaktır. Örneğin, `auto x = myVectorView->First();`.

## <a name="vectorviewgetat-method"></a><a name="getat"></a>VectorView::GetAt Yöntemi

Belirtilen dizin tarafından belirtilen geçerli VectorView öğesini alır.

### <a name="syntax"></a>Sözdizimi

```

T GetAt(
   UInt32 index
);
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
VectorView nesnesinde belirli bir öğeyi belirten sıfır tabanlı, imzasız bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri

`index` Parametre tarafından belirtilen öğe. Eleman türü VectorView şablon parametresi, *T*tarafından belirtilir.

## <a name="vectorviewgetmany-method"></a><a name="getmany"></a>VectorView::GetMany Yöntemi

Belirtilen dizinden başlayarak geçerli VectorView'den bir öğe dizisi alır.

### <a name="syntax"></a>Sözdizimi

```

virtual unsigned int GetMany(
   unsigned int startIndex,
   ::Platform::WriteOnlyArray<T>^ dest
);
```

### <a name="parameters"></a>Parametreler

*Startındex*<br/>
Alınacak öğelerin başlangıcının sıfır tabanlı dizin.

*Dest*<br/>
Bu işlem tamamlandığında, VectorView'daki son öğede `startIndex` belirtilen öğeden başlayan ve biten bir dizi öğe.

### <a name="return-value"></a>Dönüş Değeri

Alınan öğe sayısı.

## <a name="vectorviewindexof-method"></a><a name="indexof"></a>VectorView::IndexOf Yöntemi

Geçerli VectorView'de belirtilen öğeyi arar ve bulunursa, öğenin dizinini döndürür.

### <a name="syntax"></a>Sözdizimi

```

virtual bool IndexOf(
   T value,
   unsigned int* index
);
```

### <a name="parameters"></a>Parametreler

*value*<br/>
Bulunması gereken öğe.

*Dizin*<br/>
Parametre `value` bulunursa maddenin sıfır tabanlı dizin; aksi takdirde, 0.

Madde maddenin ilk öğesi yse `VectorView` veya madde bulunamazsa dizin parametresi 0'dır. *index* İade değeri **doğruysa,** öğe bulundu ve ilk öğedir; aksi takdirde, öğe bulunamadı.

### <a name="return-value"></a>Dönüş Değeri

belirtilen öğe bulunursa **geçerlidir;** aksi takdirde, **yanlış**.

## <a name="vectorviewsize-method"></a><a name="size"></a>VectorView::Boyut Yöntemi

Geçerli VectorView nesnesindeki öğe sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```

virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorView'deki öğelerin sayısı.

## <a name="vectorviewvectorview-constructor"></a><a name="ctor"></a>VectorView::VectorView Oluşturucu

VectorView sınıfının yeni bir örneğini başolarak karşılar.

### <a name="syntax"></a>Sözdizimi

```
VectorView();
explicit VectorView(
   UInt32 size
);
VectorView(
   UInt32 size,
   T value
);
explicit VectorView(
   const ::std::vector<T>& v
);
explicit VectorView(
   ::std::vector<T>&& v
);
VectorView(
   const T * ptr,
   UInt32 size
);

template <
   size_t N
>
explicit VectorView(
   const T (&arr)[N]
);

template <
   size_t N
>
explicit VectorView(
   const ::std::array<T,
   N>& a
);

explicit VectorView(
   const ::Platform::Array<T>^ arr
);

template <
   typename InIt
>
VectorView(
   InItfirst,
   InItlast
);

VectorView(
   std::initializer_list<T> il
);
```

### <a name="parameters"></a>Parametreler

*ınit*<br/>
Geçerli VectorView'i başlatmak için kullanılan nesne koleksiyonu nun türü.

*ıl*<br/>
Bir [std::initializer_list](../standard-library/initializer-list-class.md) olan öğeleri VectorView baş harflerini leştirmek için kullanılacaktır.

*N*<br/>
Geçerli VectorView'i başlatmaya kullanılan nesneler koleksiyonundaki öğe sayısı.

*Boyutu*<br/>
VectorView'daki öğelerin sayısı.

*value*<br/>
Geçerli VectorView'deki her öğeyi başlatmak için kullanılan bir değer.

*v*<br/>
Geçerli VectorView'i başlatmada kullanılan [bir std::vektöre](../standard-library/vector-class.md) bir [Lvalues ve Rvalues.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*Ptr*<br/>
Geçerli VectorView'i başlatmak için kullanılan bir `std::vector` işaretçi.

*Arr*<br/>
[Bir Platform::Geçerli](../cppcx/platform-array-class.md) VectorView'i başlatmak için kullanılan dizi nesnesi.

*A*<br/>
Geçerli VectorView'i başlatmak için kullanılan [std::dizi](../standard-library/array-class-stl.md) nesnesi.

*Ilk*<br/>
Geçerli VectorView'i başlatmak için kullanılan nesne dizisinin ilk öğesi. Türü mükemmel `first` *yönlendirme*yoluyla geçirilir. Daha fazla bilgi için [Bkz. Rvalue Başvuru Bildirimcisi: &&. ](../cpp/rvalue-reference-declarator-amp-amp.md)

*Son*<br/>
Geçerli VectorView'i başlatmak için kullanılan nesneler dizisinin son öğesi. Türü mükemmel `last` *yönlendirme*yoluyla geçirilir. Daha fazla bilgi için [Bkz. Rvalue Başvuru Bildirimcisi: &&. ](../cpp/rvalue-reference-declarator-amp-amp.md)

## <a name="see-also"></a>Ayrıca bkz.

[Platform İsim Alanı](platform-namespace-c-cx.md)<br/>
[C++'da Windows Runtime Bileşenleri Oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
