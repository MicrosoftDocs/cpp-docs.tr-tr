---
description: ': Platform:: Collections:: VectorView sınıfı hakkında daha fazla bilgi'
title: 'Platform:: Collections:: VectorView sınıfı'
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
ms.openlocfilehash: f0d1244ed5331fa9732bdfef1f1b7e2133f99442
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250042"
---
# <a name="platformcollectionsvectorview-class"></a>Platform:: Collections:: VectorView sınıfı

Dizin tarafından tek tek erişilebilen bir nesne koleksiyonunun salt okunurdur görünümünü temsil eder. Koleksiyondaki her nesnenin türü, şablon parametresi tarafından belirtilir.

## <a name="syntax"></a>Sözdizimi

```
template <typename T, typename E>
   ref class VectorView sealed;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Nesnede bulunan öğelerin türü `VectorView` .

*E*<br/>
Tür değerleriyle eşitlik testi için bir ikili koşul belirtir `T` . `std::equal_to<T>` varsayılan değerdir.

### <a name="remarks"></a>Açıklamalar

`VectorView`Sınıfı [Windows:: Foundation:: Collections:: ıvectorview \<T> ](/uwp/api/windows.foundation.collections.ivectorview-1) arabirimini ve standart Şablon kitaplığı yineleyiciler desteğini uygular.

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[VectorView:: VectorView](#ctor)|VectorView sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[VectorView:: First](#first)|VectorView içindeki ilk öğeyi belirten bir yineleyici döndürür.|
|[VectorView:: GetAt](#getat)|Belirtilen dizin tarafından belirtilen geçerli VectorView öğesini alır.|
|[VectorView:: GetMany](#getmany)|Belirtilen dizinden başlayarak, geçerli Vektörtorview öğesinden bir öğe dizisi alır.|
|[VectorView:: IndexOf](#indexof)|Geçerli vektör görünümünde belirtilen öğeyi arar ve bulunursa öğenin dizinini döndürür.|
|[VectorView:: size](#size)|Geçerli VectorView nesnesindeki öğe sayısını döndürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VectorView`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="vectorviewfirst-method"></a><a name="first"></a> VectorView:: First yöntemi

VectorView içindeki ilk öğeyi belirten bir yineleyici döndürür.

### <a name="syntax"></a>Syntax

```

virtual Windows::Foundation::Collections::IIterator<T>^
   First();
```

### <a name="return-value"></a>Dönüş Değeri

VectorView içindeki ilk öğeyi belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Ilk () tarafından döndürülen yineleyiciyi tutmanın uygun bir yolu, dönüş değerini **`auto`** tür kesintisi anahtar sözcüğüyle belirtilen bir değişkene atamaktır. Örneğin, `auto x = myVectorView->First();`.

## <a name="vectorviewgetat-method"></a><a name="getat"></a> VectorView:: GetAt yöntemi

Belirtilen dizin tarafından belirtilen geçerli VectorView öğesini alır.

### <a name="syntax"></a>Sözdizimi

```

T GetAt(
   UInt32 index
);
```

### <a name="parameters"></a>Parametreler

*indeks*<br/>
VectorView nesnesinde belirli bir öğeyi belirten sıfır tabanlı, işaretsiz bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri

Parametresi tarafından belirtilen öğe `index` . Öğe türü, VectorView şablon parametresi, *T* ile belirtilir.

## <a name="vectorviewgetmany-method"></a><a name="getmany"></a> VectorView:: GetMany yöntemi

Belirtilen dizinden başlayarak, geçerli Vektörtorview öğesinden bir öğe dizisi alır.

### <a name="syntax"></a>Sözdizimi

```

virtual unsigned int GetMany(
   unsigned int startIndex,
   ::Platform::WriteOnlyArray<T>^ dest
);
```

### <a name="parameters"></a>Parametreler

*startIndex*<br/>
Alınacak öğelerin başlangıcına ait sıfır tabanlı dizin.

*HD*<br/>
Bu işlem tamamlandığında, `startIndex` vektör görünümündeki son öğe tarafından belirtilen ve biten öğe ile başlayan bir öğe dizisi.

### <a name="return-value"></a>Dönüş Değeri

Alınan öğe sayısı.

## <a name="vectorviewindexof-method"></a><a name="indexof"></a> VectorView:: IndexOf yöntemi

Geçerli vektör görünümünde belirtilen öğeyi arar ve bulunursa öğenin dizinini döndürür.

### <a name="syntax"></a>Sözdizimi

```

virtual bool IndexOf(
   T value,
   unsigned int* index
);
```

### <a name="parameters"></a>Parametreler

*değer*<br/>
Bulunacak öğe.

*indeks*<br/>
Parametre bulunursa öğenin sıfır tabanlı dizini `value` ; Aksi durumda 0.

Öğe öğesinin ilk öğesi ise veya öğe bulunmazsa *Dizin* parametresi 0 ' dır `VectorView` . Dönüş değeri ise **`true`** , öğe bulunursa ve ilk öğedir; Aksi takdirde, öğe bulunamadı.

### <a name="return-value"></a>Dönüş Değeri

**`true`** Belirtilen öğe bulunursa; Aksi takdirde, **`false`** .

## <a name="vectorviewsize-method"></a><a name="size"></a> VectorView:: size yöntemi

Geçerli VectorView nesnesindeki öğe sayısını döndürür.

### <a name="syntax"></a>Syntax

```

virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Vektörtorview içindeki öğe sayısı.

## <a name="vectorviewvectorview-constructor"></a><a name="ctor"></a> VectorView:: VectorView Oluşturucusu

VectorView sınıfının yeni bir örneğini başlatır.

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

*Dengeleyici*<br/>
Geçerli vektörleştirme görünümünü başlatmak için kullanılan nesne koleksiyonunun türü.

*Demiryolu*<br/>
Vektörtorview 'ı başlatmak için öğeleri kullanılacak [std:: initializer_list](../standard-library/initializer-list-class.md) .

*N*<br/>
Geçerli vektör görünümünü başlatmak için kullanılan nesne koleksiyonundaki öğe sayısı.

*boyutla*<br/>
Vektörtorview içindeki öğe sayısı.

*değer*<br/>
Geçerli Vektörtorview içindeki her öğeyi başlatmak için kullanılan bir değer.

*Yönetim*<br/>
Bir [lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) , geçerli Vektörtorview 'u başlatmak için kullanılan bir [std:: vector](../standard-library/vector-class.md) öğesine.

*ptr*<br/>
`std::vector`Geçerli Vektörtorview 'ı başlatmak için kullanılan bir işaretçisi.

*ARR*<br/>
Geçerli Vektörtorview 'ı başlatmak için kullanılan bir [Platform:: Array](../cppcx/platform-array-class.md) nesnesi.

*a*<br/>
Geçerli Vektörtorview 'ı başlatmak için kullanılan bir [std:: Array](../standard-library/array-class-stl.md) nesnesi.

*adı*<br/>
Geçerli vektörleştirme görünümünü başlatmak için kullanılan nesne dizisindeki ilk öğe. Türü, `first` *kusursuz iletme* yoluyla geçirilir. Daha fazla bilgi için bkz. [rvalue başvuru bildirimci:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

*soyadına*<br/>
Geçerli vektör görünümünü başlatmak için kullanılan nesneler dizisindeki son öğe. Türü, `last` *kusursuz iletme* yoluyla geçirilir. Daha fazla bilgi için bkz. [rvalue başvuru bildirimci:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)<br/>
[C++ ' ta Windows Çalışma Zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
