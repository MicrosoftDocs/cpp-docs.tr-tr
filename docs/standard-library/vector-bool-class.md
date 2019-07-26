---
title: Vector&lt;bool&gt; sınıfı
ms.date: 11/04/2016
f1_keywords:
- vector<bool>
- vector/std::vector::const_pointer
- vector/std::vector::const_reference
- vector/std::vector::pointer
- vector/std::vector::flip
- vector/std::vector::swap
helpviewer_keywords:
- std::vector [C++], const_pointer
- std::vector [C++], const_reference
- std::vector [C++], pointer
- std::vector [C++], flip
- std::vector [C++], swap
ms.assetid: 8028c8ed-ac9c-4f06-aba1-5de45c00aafb
ms.openlocfilehash: d4ae53f9a14f04d5656a13c32e75494688c5cdd0
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452264"
---
# <a name="vectorltboolgt-class"></a>Vector&lt;bool&gt; sınıfı

Sınıfı, **bool**türündeki öğeler için Vector öğesinin kısmi bir özelleştirmesi. [](../standard-library/vector-class.md) `vector<bool>` Bir **bool** değeri bit başına depolayarak boşluk iyileştirmesi sağlayan, özelleştirme tarafından kullanılan temel tür için bir ayırıcısı vardır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Allocator = allocator<bool>>
class vector<bool, Allocator>
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu özelleştirmesi, bu makalede açıklanan farklar dışında vektör gibi davranır.

**Bool** türüyle ilgilenen işlemler, kapsayıcı depolamadaki değerlere karşılık gelir. `allocator_traits::construct`Bu değerleri oluşturmak için kullanılmaz.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[const_pointer](#const_pointer)|Bir ' `const_iterator` `vector<bool>`nin Boolean öğesine sabit bir işaretçi olarak işlev görmesi için bir typedef.|
|[const_reference](#const_reference)|**Bool**için bir typedef. Başlatmanın ardından, özgün değerde güncelleştirmeleri gözlemlemez.|
|[çağrısı](#pointer)|' A yönelik `iterator` bir typedef, `vector<bool>`bir Boolean öğesine işaretçi olarak işlev görebilir.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[yazmayı](#flip)|İçindeki tüm bitleri tersine çevirir `vector<bool>`.|
|[Kur](#swap)|İki `vector<bool>`öğenin öğelerini değiş tokuş eder.|
|[işlecinde&#91;&#93;](#op_at)|Belirtilen konumdaki `vector<bool>` öğeye sanal bir başvuru döndürür.|
|`at`|, Özel olmayan [Vector](../standard-library/vector-class.md):: at işleviyle aynı şekilde çalışır, ancak bu, [\<bool >:: Reference](#reference_class)proxy sınıfını kullanır. Ayrıca bkz [.&#91;işleci](#op_at).|
|`front`|, Özel olmayan [Vector](../standard-library/vector-class.md):: Front işleviyle aynı şekilde çalışır, ancak bu, [\<bool >:: Reference](#reference_class)proxy sınıfını kullanır. Ayrıca bkz [.&#91;işleci](#op_at).|
|`back`|, Özel olmayan [Vector](../standard-library/vector-class.md):: Back işleviyle aynı şekilde çalışır, ancak bu, [\<bool >:: Reference](#reference_class)proxy sınıfını kullanır. Ayrıca bkz [.&#91;işleci](#op_at).|

### <a name="proxy-class"></a>Proxy Sınıfı

|||
|-|-|
|[Vector\<bool > başvuru sınıfı](#reference_class)|Davranışın benzetimini `bool&` yapmak için proxy görevi gören ve nesneleri bir `vector<bool>` nesne içindeki öğelere (tek bit) başvuru sağlayabilen bir sınıf.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: \<vektör >

**Ad alanı:** std

## <a name="const_pointer"></a>vektör\<bool >:: const_pointer

`vector<bool>` Nesnenin içerdiği dizinin bir Boolean öğesi için sabit bir işaretçi olarak işlev görebilecek bir nesneyi tanımlayan bir tür.

```cpp
typedef const_iterator const_pointer;
```

## <a name="const_reference"></a>vektör\<bool >:: const_reference

`vector<bool>` Nesne tarafından içerilen dizinin bir Boolean öğesine sabit başvuru olarak işlev yapabilecek bir nesneyi tanımlayan bir tür.

```cpp
typedef bool const_reference;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi ve kod örnekleri için bkz [.&lt;vector&gt;bool:: Reference:: operator =](#reference_operator_eq).

## <a name="flip"></a>vektör\<bool >:: çevir

İçindeki tüm bitleri tersine çevirir `vector<bool>`.

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

## <a name="op_at"></a>Vector\<bool >:: operator []

Belirtilen konumdaki `vector<bool>` öğeye sanal bir başvuru döndürür.

```cpp
vector<bool>::reference operator[](size_type Pos);

vector&<bool&>::const_reference operator[](size_type Pos) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*'Un*|`vector<bool>` Öğesinin konumu.|

### <a name="return-value"></a>Dönüş Değeri

Bir [Vector\<bool >:: Reference](#reference_class) veya [Vector\<bool >:: const_reference](#const_reference) nesnesi, dizinli öğenin değerini içerir.

Belirtilen konum kapsayıcısının boyutuna eşit veya ondan daha büyük ise, sonuç tanımsızdır.

### <a name="remarks"></a>Açıklamalar

_ITERATOR_DEBUG_LEVEL kümesiyle derlerseniz, vektör sınırları dışında bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

Bu kod örneği, açıklama eklenen `vector<bool>::operator[]` ve iki yaygın kodlama hatalarının doğru kullanımını gösterir. `vector<bool>::reference` Döndürdüğü nesnenin adresi alınamadığından bu hatalar hatalara neden olur. `vector<bool>::operator[]`

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

## <a name="pointer"></a>vektör\<bool >::p oınter

`vector<bool>` Nesnenin içerdiği dizinin bir Boolean öğesi için bir işaretçi olarak işlev görebilecek bir nesneyi tanımlayan bir tür.

```cpp
typedef iterator pointer;
```

## <a name="reference_class"></a>Vector\<bool >:: Reference sınıfı

Sınıfı, benzetimi`bool&`yapılacak [vektör\<bool > sınıfı](../standard-library/vector-bool-class.md) tarafından sunulan bir ara sunucu sınıfıdır. `vector<bool>::reference`

### <a name="remarks"></a>Açıklamalar

C++ yerel olarak doğrudan başvuruların bitlere atanmasına izin vermediğinden, benzetimli bir başvuru gereklidir. `vector<bool>`, bu proxy sınıfı kullanılarak başvurulabilen her öğe için yalnızca bir bit kullanır. Bununla birlikte, belirli atamalar geçersiz olduğundan başvuru benzetimi tam değil. Örneğin, `vector<bool>::reference` nesnenin adresi alınamadığından, [vektör\<bool >:: işlecini&#91; ](#op_at) kullanan aşağıdaki kod doğru değildir:

```cpp
vector<bool> vb;
//...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

###  <a name="reference_flip"></a>Vector\<bool >:: Reference:: Flip

Başvurulan [\<vector bool >](../standard-library/vector-bool-class.md) öğesinin Boole değerini tersine çevirir.

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

###  <a name="reference_operator_bool"></a>Vector\<bool >:: Reference:: operator bool

Kaynağından `vector<bool>::reference` **bool**'a örtük bir dönüştürme sağlar.

```cpp
operator bool() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Vektör\<bool > nesnesinin öğesinin Boolean değeri.

#### <a name="remarks"></a>Açıklamalar

`vector<bool>` Nesne bu işleç tarafından değiştirilemiyor.

###  <a name="reference_operator_eq"></a>  vector\<bool>::reference::operator=

Bir bite bir Boolean değeri, veya başvurulan bir öğenin tuttuğu değeri atar.

```cpp
reference& operator=(const reference& Right);
reference& operator=(bool Val);
```

### <a name="parameters"></a>Parametreler

*Right*\
Değerinin bite atanacağı öğe başvurusu.

*Acil*\
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

## <a name="swap"></a>vektör\<bool >:: takas

Bool > `vector<bool>` [:: Reference proxy sınıfını kullanarak Boole vektörlerinin () iki öğesini değiş tokuş eden\<](#reference_class)statik üye işlevi.

```cpp
static void swap(
    reference Left,
    reference Right);
```

### <a name="parameters"></a>Parametreler

*Tarafta*\
*Sağ* öğesiyle değiştirilecek öğe.

*Right*\
*Sol* öğesiyle değiştirilecek öğe.

### <a name="remarks"></a>Açıklamalar

Bu aşırı yükleme, için özel proxy gereksinimlerini `vector<bool>`destekler. [Vector](../standard-library/vector-class.md):: swap, tek değişkenli aşırı yüklemesiyle `vector<bool>::swap()`aynı işlevselliğe sahiptir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
