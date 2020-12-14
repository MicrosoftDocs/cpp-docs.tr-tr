---
description: 'Daha fazla bilgi edinin: vektör &lt; bool &gt; sınıfı'
title: Vector &lt; bool &gt; sınıfı
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
ms.openlocfilehash: ecc7c083825a92aca429f9418d35ff9d4cf7dcca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280514"
---
# <a name="vectorltboolgt-class"></a>Vector &lt; bool &gt; sınıfı

`vector<bool>`Sınıfı, türündeki öğeler için [Vector](../standard-library/vector-class.md) öğesinin kısmi bir özelleştirmesi **`bool`** . Her bit için bir değer depolayarak boşluk iyileştirmesi sağlayan, özelleştirme tarafından kullanılan temel tür için bir ayırıcı vardır **`bool`** .

## <a name="syntax"></a>Syntax

```cpp
template <class Allocator = allocator<bool>>
class vector<bool, Allocator>
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu özelleştirmesi, bu makalede açıklanan farklar dışında vektör gibi davranır.

Türle ilgilenen işlemler, **`bool`** kapsayıcı depolamadaki değerlere karşılık gelir. `allocator_traits::construct` Bu değerleri oluşturmak için kullanılmaz.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[const_pointer](#const_pointer)|Bir ' `const_iterator` nin Boolean öğesine sabit bir işaretçi olarak işlev görmesi için bir typedef `vector<bool>` .|
|[const_reference](#const_reference)|İçin bir typedef **`bool`** . Başlatmanın ardından, özgün değerde güncelleştirmeleri gözlemlemez.|
|[pointer](#pointer)|' A yönelik bir typedef `iterator` , bir Boolean öğesine işaretçi olarak işlev görebilir `vector<bool>` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[yazmayı](#flip)|İçindeki tüm bitleri tersine çevirir `vector<bool>` .|
|[Kur](#swap)|İki öğenin öğelerini değiş tokuş eder `vector<bool>` .|
|[işleç&#91;&#93;](#op_at)|Belirtilen konumdaki öğeye sanal bir başvuru döndürür `vector<bool>` .|
|`at`|Özelleştirilmemiş vector:: [ \<bool> Reference](#reference_class)proxy sınıfını kullanması dışında, özel olmayan [Vector](../standard-library/vector-class.md):: at işleviyle aynı şekilde çalışır. Ayrıca bkz. [operator&#91;&#93;](#op_at).|
|`front`|, Özel olmayan [Vector](../standard-library/vector-class.md):: Front işleviyle aynı şekilde çalışır, ancak [Vector \<bool> :: Reference](#reference_class)proxy sınıfını kullanır. Ayrıca bkz. [operator&#91;&#93;](#op_at).|
|`back`|, Özel olmayan [Vector](../standard-library/vector-class.md):: Back işleviyle aynı şekilde çalışır, ancak [Vector \<bool> :: Reference](#reference_class)proxy sınıfını kullanır. Ayrıca bkz. [operator&#91;&#93;](#op_at).|

### <a name="proxy-class"></a>Proxy Sınıfı

|Ad|Açıklama|
|-|-|
|[vektör \<bool> başvuru sınıfı](#reference_class)|Davranışın benzetimini yapmak için proxy görevi gören `bool&` ve nesneleri bir nesne içindeki öğelere (tek bit) başvuru sağlayabilen bir sınıf `vector<bool>` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<vector>

**Ad alanı:** std

## <a name="vectorboolconst_pointer"></a><a name="const_pointer"></a> vektör \<bool> :: const_pointer

Nesnenin içerdiği dizinin bir Boolean öğesi için sabit bir işaretçi olarak işlev görebilecek bir nesneyi tanımlayan bir tür `vector<bool>` .

```cpp
typedef const_iterator const_pointer;
```

## <a name="vectorboolconst_reference"></a><a name="const_reference"></a> vektör \<bool> :: const_reference

Nesne tarafından içerilen dizinin bir Boolean öğesine sabit başvuru olarak işlev yapabilecek bir nesneyi tanımlayan bir tür `vector<bool>` .

```cpp
typedef bool const_reference;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi ve kod örnekleri için bkz. [Vector &lt; bool &gt; :: Reference:: operator =](#reference_operator_eq).

## <a name="vectorboolflip"></a><a name="flip"></a> Vector \<bool> :: Flip

İçindeki tüm bitleri tersine çevirir `vector<bool>` .

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

## <a name="vectorbooloperator"></a><a name="op_at"></a> Vector \<bool> :: operator []

Belirtilen konumdaki öğeye sanal bir başvuru döndürür `vector<bool>` .

```cpp
vector<bool>::reference operator[](size_type Pos);

vector&<bool&>::const_reference operator[](size_type Pos) const;
```

### <a name="parameters"></a>Parametreler

*'Un*\
`vector<bool>`Öğesinin konumu.

### <a name="return-value"></a>Dönüş Değeri

Bir [Vector \<bool> :: Reference](#reference_class) veya [Vector \<bool> :: const_reference](#const_reference) dizinli öğenin değerini içeren nesne.

Belirtilen konum kapsayıcısının boyutuna eşit veya ondan daha büyük ise, sonuç tanımsızdır.

### <a name="remarks"></a>Açıklamalar

_ITERATOR_DEBUG_LEVEL kümesiyle derlerseniz, vektör sınırları dışında bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

Bu kod örneği `vector<bool>::operator[]` , açıklama eklenen ve iki yaygın kodlama hatalarının doğru kullanımını gösterir. `vector<bool>::reference` Döndürdüğü nesnenin adresi alınamadığından bu hatalar hatalara neden olur `vector<bool>::operator[]` .

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

## <a name="vectorboolpointer"></a><a name="pointer"></a> vektör \<bool> ::p oınter

Nesnenin içerdiği dizinin bir Boolean öğesi için bir işaretçi olarak işlev görebilecek bir nesneyi tanımlayan bir tür `vector<bool>` .

```cpp
typedef iterator pointer;
```

## <a name="vectorboolreference-class"></a><a name="reference_class"></a> Vector \<bool> :: Reference sınıfı

`vector<bool>::reference`Sınıfı, benzetimini yapmak için [vektör \<bool> sınıfı](../standard-library/vector-bool-class.md) tarafından sunulan bir proxy sınıfıdır `bool&` .

### <a name="remarks"></a>Açıklamalar

C++ yerel olarak doğrudan başvuruların bitlere atanmasına izin vermediğinden, benzetimli bir başvuru gereklidir. `vector<bool>` , bu proxy sınıfı kullanılarak başvurulabilen her öğe için yalnızca bir bit kullanır. Bununla birlikte, belirli atamalar geçersiz olduğundan başvuru benzetimi tam değil. Örneğin, `vector<bool>::reference` nesnenin adresi alınamadığından, [Vector \<bool> :: operator&#91;&#93;](#op_at) kullanan şu kod doğru değildir:

```cpp
vector<bool> vb;
//...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

### <a name="vectorboolreferenceflip"></a><a name="reference_flip"></a> Vector \<bool> :: Reference:: Flip

Başvurulan [Vector \<bool> ](../standard-library/vector-bool-class.md) öğesinin Boole değerini tersine çevirir.

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

### <a name="vectorboolreferenceoperator-bool"></a><a name="reference_operator_bool"></a> Vector \<bool> :: Reference:: operator bool

Öğesinden öğesine örtük bir dönüştürme `vector<bool>::reference` sağlar **`bool`** .

```cpp
operator bool() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Vektör nesnesinin öğesinin Boolean değeri \<bool> .

#### <a name="remarks"></a>Açıklamalar

`vector<bool>`Nesne bu işleç tarafından değiştirilemiyor.

### <a name="vectorboolreferenceoperator"></a><a name="reference_operator_eq"></a> Vector \<bool> :: Reference:: operator =

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

## <a name="vectorboolswap"></a><a name="swap"></a> Vector \<bool> :: swap

Bir static `vector<bool>` [vektör \<bool> :: Reference](#reference_class)proxy sınıfını kullanarak Boole vektörlerinin () iki öğesini değiş tokuş eden statik üye işlevi.

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

Bu aşırı yükleme, için özel proxy gereksinimlerini destekler `vector<bool>` . [Vector](../standard-library/vector-class.md):: swap, tek değişkenli aşırı yüklemesiyle aynı işlevselliğe sahiptir `vector<bool>::swap()` .

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
