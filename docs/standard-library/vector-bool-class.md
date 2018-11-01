---
title: vektör&lt;bool&gt; sınıfı
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
ms.openlocfilehash: 79b2231882f65715f47c774119c0e6e0608f1676
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455490"
---
# <a name="vectorltboolgt-class"></a>vektör&lt;bool&gt; sınıfı

`vector<bool>` Sınıfı, bir kısmi alt uzmanlaşması [vektör](../standard-library/vector-class.md) türü öğeler için **bool**. Depolama yaparak alan iyileştirmesi sağlayan uzmanlık tarafından kullanılan temel alınan türü için bir ayırıcısı vardır **bool** başına bit değeri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Allocator = allocator<bool>>
class vector<bool, Allocator>
```

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu uzmanlığı, vektör, bu makalede açıklanan farklılıklar dışında gibi davranır.

İlgilenen işlemler **bool** türü kapsayıcı deposundaki değerlere karşılık gelir. `allocator_traits::construct` Bu değerleri oluşturmak için kullanılmaz.

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[const_pointer](#const_pointer)|Tür tanımı bir `const_iterator` bir Boolean öğesi için sabit bir işaretçi olarak verebilen `vector<bool>`.|
|[const_reference](#const_reference)|İçin bir typedef **bool**. Başlatmanın ardından, özgün değerde güncelleştirmeleri gözlemlemez.|
|[İşaretçi](#pointer)|Tür tanımı bir `iterator` bir Boolean öğesi için bir işaretçi olarak verebilen `vector<bool>`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Çevir](#flip)|İçindeki tüm bitleri tersine çevirir `vector<bool>`.|
|[değiştirme](#swap)|İki öğeleri birbiriyle değiştirir `vector<bool>`s.|
|[işleci&#91;&#93;](#op_at)|Sanal bir başvuru döndürür `vector<bool>` öğesine belirtilen konumda.|
|`at`|Aynı şekilde işler uzmanlaşmamış [vektör](../standard-library/vector-class.md):: BT'nin proxy sınıfını kullananlar hariç işlevi [vektör\<bool >:: reference](#reference_class). Ayrıca bkz: [işleci&#91;&#93;](#op_at).|
|`front`|Aynı şekilde işler uzmanlaşmamış [vektör](../standard-library/vector-class.md):: proxy sınıfını kullananlar hariç, işlev, ön [vektör\<bool >:: reference](#reference_class). Ayrıca bkz: [işleci&#91;&#93;](#op_at).|
|`back`|Aynı şekilde işler uzmanlaşmamış [vektör](../standard-library/vector-class.md):: proxy sınıfını kullananlar hariç, işlev, yedekleme [vektör\<bool >:: reference](#reference_class). Ayrıca bkz: [işleci&#91;&#93;](#op_at).|

### <a name="proxy-class"></a>Proxy Sınıfı

|||
|-|-|
|[vektör\<bool > başvuru sınıfı](#reference_class)|Benzetimini yapmak için bir proxy olarak davranan bir sınıf `bool&` davranışı ve öğelere (tek bit) başvurular içinde sağlayabilir, nesneleri bir `vector<bool>` nesne.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<vektör >

**Namespace:** std

## <a name="const_pointer"></a>  vektör\<bool >:: const_pointer

Tarafından içerilen dizinin bir Boolean öğesi için sabit bir işaretçi olarak hizmet verebilen bir nesneyi açıklayan tür `vector<bool>` nesne.

```cpp
typedef const_iterator const_pointer;
```

## <a name="const_reference"></a>  vektör\<bool >:: const_reference

Tarafından içerilen dizinin bir Boolean öğesi için sabit bir başvuru olarak hizmet verebilen bir nesneyi açıklayan tür `vector<bool>` nesne.

```cpp
typedef bool const_reference;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi ve kod örnekleri için bkz. [vektör&lt;bool&gt;:: reference::operator =](#reference_operator_eq).

## <a name="flip"></a>  vektör\<bool >:: Çevir

İçindeki tüm bitleri tersine çevirir bir `vector<bool>`.

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

## <a name="op_at"></a>  vektör\<bool >:: operator]

Sanal bir başvuru döndürür `vector<bool>` öğesine belirtilen konumda.

```cpp
vector<bool>::reference operator[](size_type Pos);

vector&<bool&>::const_reference operator[](size_type Pos) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|-|-|
|*POS*|Konumunu `vector<bool>` öğesi.|

### <a name="return-value"></a>Dönüş Değeri

A [vektör\<bool >:: reference](#reference_class) veya [vektör\<bool >:: const_reference](#const_reference) dizinlenmiş öğenin değerini içeren nesne.

Belirtilen konum kapsayıcısının boyutuna eşit veya ondan daha büyük ise, sonuç tanımsızdır.

### <a name="remarks"></a>Açıklamalar

_Iterator_debug_level kümesiyle derleme yaparsanız, vektör sınırları dışında bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

Bu kod örneği doğru kullanımını gösterir `vector<bool>::operator[]` ve yaygın iki kodlama hatalar, derleme dışı bırakılır. Bu hatalar nedeniyle hatalara neden adresini `vector<bool>::reference` nesnesinin `vector<bool>::operator[]` döndüren.

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

## <a name="pointer"></a>  vektör\<bool >:: işaretçi

Tarafından içerilen dizinin bir Boolean öğesi için bir işaretçi olarak hizmet verebilen bir nesneyi açıklayan tür `vector<bool>` nesne.

```cpp
typedef iterator pointer;
```

## <a name="reference_class"></a>  vektör\<bool >:: reference sınıfı

`vector<bool>::reference` Tarafından sağlanan bir proxy sınıfı [vektör\<bool > sınıfı](../standard-library/vector-bool-class.md) benzetimini yapmak için `bool&`.

### <a name="remarks"></a>Açıklamalar

C++ yerel olarak doğrudan başvuruların bitlere atanmasına izin vermediğinden, benzetimli bir başvuru gereklidir. `vector<bool>` Bu proxy sınıfı kullanılarak başvurulabilen öğesi başına yalnızca bir bit kullanır. Bununla birlikte, belirli atamalar geçersiz olduğundan başvuru benzetimi tam değil. Örneğin, çünkü adresini `vector<bool>::reference` nesne olamaz alınamadığından, kullandığı aşağıdaki kodu [vektör\<bool >:: operator&#91; &#93; ](#op_at) doğru değil:

```cpp
vector<bool> vb;
//...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

###  <a name="reference_flip"></a>  vektör\<bool >:: reference::flip

Başvurulan bir Boolean değerini tersine çevirir [vektör\<bool >](../standard-library/vector-bool-class.md) öğesi.

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

###  <a name="reference_operator_bool"></a>  vektör\<bool >:: reference::operator bool

Örtük bir dönüştürme sağlar `vector<bool>::reference` için **bool**.

```cpp
operator bool() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Vektör öğesinin Boolean değerini\<bool > nesne.

#### <a name="remarks"></a>Açıklamalar

`vector<bool>` Nesnesi bu işleç tarafından değiştirilemez.

###  <a name="reference_operator_eq"></a>  vector\<bool>::reference::operator=

Bir bite bir Boolean değeri, veya başvurulan bir öğenin tuttuğu değeri atar.

```cpp
reference& operator=(const reference& Right);
reference& operator=(bool Val);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Değerinin bite atanacağı öğe başvurusu.

*VAL*<br/>
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

## <a name="swap"></a>  vektör\<bool >:: swap

Değiştiren Boolean vektörlerinin iki öğeleri birbiriyle değiştirir statik üye işlevini ( `vector<bool>`) proxy sınıfı kullanılarak [vektör\<bool >:: reference](#reference_class).

```cpp
static void swap(
    reference Left,
    reference Right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Öğesiyle değiştirilecek öğe *sağ* öğesi.

*sağ*<br/>
Öğesiyle değiştirilecek öğe *sol* öğesi.

### <a name="remarks"></a>Açıklamalar

Bu aşırı yükleme özel proxy gereksinimlerini destekler `vector<bool>`. [vektör](../standard-library/vector-class.md):: swap tek bağımsız değişkenli aşırı yüklemesi ile aynı işlevlere sahip `vector<bool>::swap()`.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
