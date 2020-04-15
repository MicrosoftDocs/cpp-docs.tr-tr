---
title: vektör&lt;bool&gt; Sınıfı
ms.date: 11/04/2016
f1_keywords:
- vector<bool>
- vector/std::vector::flip
helpviewer_keywords:
- std::vector [C++], const_pointer
- std::vector [C++], const_reference
- std::vector [C++], pointer
- std::vector [C++], flip
- std::vector [C++], swap
ms.assetid: 8028c8ed-ac9c-4f06-aba1-5de45c00aafb
ms.openlocfilehash: 6c67e3d9ba1b33cb99a7d3afb2522f443003fa38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376092"
---
# <a name="vectorltboolgt-class"></a>vektör&lt;bool&gt; Sınıfı

Sınıf `vector<bool>` tip **bool**elemanları için [vektör](../standard-library/vector-class.md) kısmi bir uzmanlaşma . Bu bit başına bir **bool** değeri depolayarak alan optimizasyonu sağlayan uzmanlık tarafından kullanılan temel türü için bir ayırıcı vardır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Allocator = allocator<bool>>
class vector<bool, Allocator>
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu uzmanlık vektör gibi, bu makalede açıklanan farklılıklar dışında gibi olur.

**Bool** türüyle ilgili işlemler, konteyner depolamasındaki değerlere karşılık gelir. `allocator_traits::construct`bu değerleri oluşturmak için kullanılmaz.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Const_pointer](#const_pointer)|Boolean öğesine `const_iterator` sabit bir işaretçi olarak hizmet verebilen bir typedef'e `vector<bool>`bir typedef|
|[const_reference](#const_reference)|**Bool**için bir typedef . Başlatmanın ardından, özgün değerde güncelleştirmeleri gözlemlemez.|
|[pointer](#pointer)|Bir Boolean `iterator` öğesiiçin bir işaretçi olarak hizmet verebilir `vector<bool>`bir typedef .|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Flip](#flip)|`vector<bool>`Tüm bitleri tersine çevirir.|
|[Takas](#swap)|İki `vector<bool>`s'nin öğelerini değiştirir.|
|[operatör&#91;&#93;](#op_at)|Belirli bir konumda `vector<bool>` öğeye benzetilmiş bir başvuru verir.|
|`at`|Özelleştirilmiş vektörle aynı [vector](../standard-library/vector-class.md)işlev ::at function, proxy sınıfı [vektör\<bool> kullanması dışında::başvuru .](#reference_class) Ayrıca [bkz. işleç&#91;&#93;. ](#op_at)|
|`front`|Özelleştirilmiş vektörle aynı [vector](../standard-library/vector-class.md)işlev ::ön işlev, proxy sınıfı [vektör\<bool> kullanması dışında::başvuru .](#reference_class) Ayrıca [bkz. işleç&#91;&#93;. ](#op_at)|
|`back`|Özelleştirilmiş olmayan [vektör](../standard-library/vector-class.md)le aynı işlev ::back fonksiyonu, proxy sınıfı vektör [\<bool> kullanması dışında::başvuru .](#reference_class) Ayrıca [bkz. işleç&#91;&#93;. ](#op_at)|

### <a name="proxy-class"></a>Proxy Sınıfı

|||
|-|-|
|[vektör\<bool> referans Sınıfı](#reference_class)|Davranışı simüle `bool&` etmek için proxy görevi gören ve nesneleri nesne içindeki öğelere (tek bit) başvurular sağlayan bir `vector<bool>` sınıf.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi** \<: vektör>

**Ad alanı:** std

## <a name="vectorboolconst_pointer"></a><a name="const_pointer"></a>vektör\<bool>::const_pointer

Nesne tarafından bulunan dizinin Boolean öğesine sabit işaretçi olarak hizmet verebilen bir nesneyi `vector<bool>` açıklayan bir tür.

```cpp
typedef const_iterator const_pointer;
```

## <a name="vectorboolconst_reference"></a><a name="const_reference"></a>vektör\<bool>::const_reference

Nesne tarafından bulunan dizinin Boolean öğesine sabit bir başvuru olarak hizmet `vector<bool>` verebilecek bir nesneyi açıklayan bir tür.

```cpp
typedef bool const_reference;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi ve kod örnekleri için [&lt;vektör bool&gt;::reference::operator=](#reference_operator_eq).

## <a name="vectorboolflip"></a><a name="flip"></a>vektör\<bool>::flip

Tüm bitleri tersine `vector<bool>`çevirir.

```cpp
void flip();
```

### <a name="example"></a>Örnek

```cpp
// vector_bool_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha; // format output for subsequent code

    vector<bool> vb = { true, false, false, true, true };
    cout << "The vector is:" << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vb.flip();

    cout << "The flipped vector is:" << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}
```

## <a name="vectorbooloperator"></a><a name="op_at"></a>vektör\<bool>::operatör[]

Belirli bir konumda `vector<bool>` öğeye benzetilmiş bir başvuru verir.

```cpp
vector<bool>::reference operator[](size_type Pos);

vector&<bool&>::const_reference operator[](size_type Pos) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*Pos*|Öğenin `vector<bool>` konumu.|

### <a name="return-value"></a>Dönüş Değeri

[Bir\<vektör bool>::referans](#reference_class) veya [vektör\<bool>::const_reference](#const_reference) nesne dizine öğenin değerini içerir.

Belirtilen konum kapsayıcısının boyutuna eşit veya ondan daha büyük ise, sonuç tanımsızdır.

### <a name="remarks"></a>Açıklamalar

_ITERATOR_DEBUG_LEVEL kümeyle derlerseniz, vektörün sınırları dışındaki bir öğeye erişmeye çalışırsanız çalışma zamanı hatası oluşur.  Daha fazla bilgi için [bkz.](../standard-library/checked-iterators.md)

### <a name="example"></a>Örnek

Bu kod örneği, doğru `vector<bool>::operator[]` kullanımı ve yorumlanan iki yaygın kodlama hatasını gösterir. Bu hatalar hatalara neden `vector<bool>::reference` olur, `vector<bool>::operator[]` çünkü döndüren nesnenin adresi alınamaz.

```cpp
// cl.exe /EHsc /nologo /W4 /MTd
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;
    vector<bool> vb;

    vb.push_back(true);
    vb.push_back(false);

    //    bool* pb = &vb[1]; // conversion error - do not use
    //    bool& refb = vb[1];   // conversion error - do not use
    bool hold = vb[1];
    cout << "The second element of vb is " << vb[1] << endl;
    cout << "The held value from the second element of vb is " << hold << endl;

    // Note this doesn't modify hold.
    vb[1] = true;
    cout << "The second element of vb is " << vb[1] << endl;
    cout << "The held value from the second element of vb is " << hold << endl;
}
```

## <a name="vectorboolpointer"></a><a name="pointer"></a>vektör\<bool>::pointer

Nesne tarafından bulunan dizinin Boolean öğesine işaretçi olarak hizmet verebilen bir nesneyi `vector<bool>` açıklayan bir tür.

```cpp
typedef iterator pointer;
```

## <a name="vectorboolreference-class"></a><a name="reference_class"></a>vektör\<bool>::referans Sınıf

`vector<bool>::reference` Sınıf, [vektör\<bool> Sınıfı](../standard-library/vector-bool-class.md) tarafından simüle `bool&`etmek için sağlanan bir proxy sınıfıdır.

### <a name="remarks"></a>Açıklamalar

C++ yerel olarak doğrudan başvuruların bitlere atanmasına izin vermediğinden, benzetimli bir başvuru gereklidir. `vector<bool>`öğe başına yalnızca bir bit kullanır, bu proxy sınıf kullanılarak başvurulabilir. Bununla birlikte, belirli atamalar geçersiz olduğundan başvuru benzetimi tam değil. Örneğin, nesnenin `vector<bool>::reference` adresi alınamadığından, vektör [\<bool> kullanan aşağıdaki kod::işleç&#91;&#93;](#op_at) doğru değildir:

```cpp
vector<bool> vb;
//...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

### <a name="vectorboolreferenceflip"></a><a name="reference_flip"></a>vektör\<bool>::referans::flip

Başvurulan [vektör\<bool>](../standard-library/vector-bool-class.md) elemanının Boolean değerini tersine çevirir.

```cpp
void flip();
```

#### <a name="example"></a>Örnek

```cpp
// vector_bool_ref_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    cout << "The vector is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vector<bool>::reference vbref = vb.front();
    vbref.flip();

    cout << "The vector with first element flipped is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}
```

```Output
The vector is:
    true false false true true
The vector with first element flipped is:
    false false false true true
```

### <a name="vectorboolreferenceoperator-bool"></a><a name="reference_operator_bool"></a>vektör\<bool>::referans::operatör bool

`vector<bool>::reference` **Bool'a**örtülü dönüştürme sağlar.

```cpp
operator bool() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Vektör\<bool> nesnenin elemanının Boolean değeri.

#### <a name="remarks"></a>Açıklamalar

Nesne `vector<bool>` bu işleç tarafından değiştirilemez.

### <a name="vectorboolreferenceoperator"></a><a name="reference_operator_eq"></a>vektör\<bool>::referans::operator=

Bir bite bir Boolean değeri, veya başvurulan bir öğenin tuttuğu değeri atar.

```cpp
reference& operator=(const reference& Right);
reference& operator=(bool Val);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Değerinin bite atanacağı öğe başvurusu.

*Val*\
Bite atanacak Boolean değeri.

#### <a name="example"></a>Örnek

```cpp
// vector_bool_ref_op_assign.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
#include <string>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    print("The vector is: ", vb);

    // Invoke vector<bool>::reference::operator=()
    vector<bool>::reference refelem1 = vb[0];
    vector<bool>::reference refelem2 = vb[1];
    vector<bool>::reference refelem3 = vb[2];

    bool b1 = refelem1;
    bool b2 = refelem2;
    bool b3 = refelem3;
    cout << "The original value of the 1st element stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element stored in a bool: " << b3 << endl;
    cout << endl;

    refelem2 = refelem1;

    print("The vector after assigning refelem1 to refelem2 is now: ", vb);

    refelem3 = true;

    print("The vector after assigning false to refelem1 is now: ", vb);

    // The initial values are still stored in the bool variables and remained unchanged
    cout << "The original value of the 1st element still stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element still stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element still stored in a bool: " << b3 << endl;
    cout << endl;
}
```

```Output
The vector is: true false false true true
The original value of the 1st element stored in a bool: true
The original value of the 2nd element stored in a bool: false
The original value of the 3rd element stored in a bool: false

The vector after assigning refelem1 to refelem2 is now: true true false true true
The vector after assigning false to refelem1 is now: true true true true true
The original value of the 1st element still stored in a bool: true
The original value of the 2nd element still stored in a bool: false
The original value of the 3rd element still stored in a bool: false
```

## <a name="vectorboolswap"></a><a name="swap"></a>vektör\<bool>::takas

Boolean vektörlerinin iki öğesini değiştiren statik `vector<bool>`üye işlev ( ) proxy sınıfı vektör [\<bool> kullanarak::reference](#reference_class).

```cpp
static void swap(
    reference Left,
    reference Right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
*Sağ* öğe ile değiştirilecek öğe.

*Doğru*\
*Sol* öğeile değiştirilecek öğe.

### <a name="remarks"></a>Açıklamalar

Bu aşırı `vector<bool>`yük, özel proxy gereksinimlerini destekler. [vektör](../standard-library/vector-class.md)::swap tek bağımsız lık yükü ile `vector<bool>::swap()`aynı işlevsellik vardır.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
