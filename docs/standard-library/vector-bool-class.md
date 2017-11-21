---
title: "vektör&lt;bool&gt; sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vector<bool>
- vector/std::vector::const_pointer
- vector/std::vector::const_reference
- vector/std::vector::pointer
- vector/std::vector::flip
- vector/std::vector::swap
dev_langs: C++
helpviewer_keywords:
- std::vector [C++], const_pointer
- std::vector [C++], const_reference
- std::vector [C++], pointer
- std::vector [C++], flip
- std::vector [C++], swap
ms.assetid: 8028c8ed-ac9c-4f06-aba1-5de45c00aafb
caps.latest.revision: "29"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 718cb52bbc06645ec40fe5e35ba0a8cc55ff1778
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vectorltboolgt-class"></a>vektör&lt;bool&gt; sınıfı
`vector<bool>` Sınıftır kısmi uzmanlığı [vektör](../standard-library/vector-class.md) türündeki öğeler için `bool`. Bir depolama alanı iyileştirme sağlar uzmanlık tarafından kullanılan temel alınan türü için bir ayırıcı sahip `bool` bit başına değer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Allocator = allocator<bool>>  
class vector<bool, Allocator>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf şablonu uzmanlık vektör, bu makalede açıklanan farklar dışında gibi davranır.  
  
 Uğraşmanız işlemleri `bool` türü değerleri için kapsayıcı depolama karşılık gelir. `allocator_traits::construct`Bu değerleri oluşturmak için kullanılmaz.  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[const_pointer](#const_pointer)|Bir typedef bir `const_iterator` , hizmet verebilir sabit bir Boole öğesi işaretçisi olarak `vector<bool>`.|  
|[const_reference](#const_reference)|Typedef için `bool`. Başlatmanın ardından, özgün değerde güncelleştirmeleri gözlemlemez.|  
|[İşaretçi](#pointer)|Bir typedef bir `iterator` , hizmet verebilir bir Boolean öğesi işaretçisi olarak `vector<bool>`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[ters çevirin](#flip)|Tüm bit cinsinden tersine çevirir `vector<bool>`.|  
|[değiştirme](#swap)|İki öğelerini alış verişleri `vector<bool>`s.|  
|[operator &#91; &#93;](#op_at)|Sanal bir başvuru döndürür `vector<bool>` belirtilen konumda öğesi.|  
|`at`|Aynı unspecialized işlevleri [vektör](../standard-library/vector-class.md):: olan proxy sınıfını kullanan dışında işlevi, en [vektör\<bool >:: başvuru](#reference_class). Ayrıca bkz. [işleci &#91; &#93;](#op_at).|  
|`front`|Aynı unspecialized işlevleri [vektör](../standard-library/vector-class.md):: proxy sınıfını kullanır ancak bu işlev, ön [vektör\<bool >:: başvuru](#reference_class). Ayrıca bkz. [işleci &#91; &#93;](#op_at).|  
|`back`|Aynı unspecialized işlevleri [vektör](../standard-library/vector-class.md):: proxy sınıfını kullanır ancak bu işlev, geri [vektör\<bool >:: başvuru](#reference_class). Ayrıca bkz. [işleci &#91; &#93;](#op_at).|  
  
### <a name="proxy-class"></a>Proxy Sınıfı  
  
|||  
|-|-|  
|[vektör\<bool > sınıfı başvurusu](#reference_class)|Benzetimini yapmak için bir proxy gibi davranır bir sınıf `bool&` davranışı ve nesneleri içinde öğelere (tek BITS) başvurular sağlayabilir bir `vector<bool>` nesnesi.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: \<vektör >  
  
 **Namespace:** std  
  
##  <a name="const_pointer"></a>vektör\<bool >:: const_pointer  
 Bir Boole öğesi tarafından bulunan dizisi için sabit bir işaretçi olarak hizmet verebilir bir nesneyi tanımlayan bir tür `vector<bool>` nesnesi.  
  
```  
typedef const_iterator const_pointer;  
```  
  
##  <a name="const_reference"></a>vektör\<bool >:: const_reference  
 Bir Boole öğesi tarafından bulunan dizisinin sabit bir başvuru olarak hizmet verebilir bir nesneyi tanımlayan bir tür `vector<bool>` nesnesi.  
  
```  
typedef bool const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi ve kod örnekleri için bkz: [vektör&lt;bool&gt;:: reference::operator =](#reference_operator_eq).  
  
##  <a name="flip"></a>vektör\<bool >:: ters çevirin  
 Tüm bit cinsinden tersine çevirir bir `vector<bool>`.  
  
```  
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
  
##  <a name="op_at"></a>vektör\<bool >:: [] işleci  
 Sanal bir başvuru döndürür `vector<bool>` belirtilen konumda öğesi.  
  
```  
vector<bool>::reference operator[](size_type Pos);

vector&<bool&>::const_reference operator[](size_type Pos) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Pos`|Konumunu `vector<bool>` öğesi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [vektör\<bool >:: başvuru](#reference_class) veya [vektör\<bool >:: const_reference](#const_reference) dizinli öğenin değerini içeren nesne.  
  
 Belirtilen konum kapsayıcısının boyutuna eşit veya ondan daha büyük ise, sonuç tanımsızdır.  
  
### <a name="remarks"></a>Açıklamalar  
 İle derleme yaparsanız `_ITERATOR_DEBUG_LEVEL` vektör sınırları dışındaki bir öğe erişmeye ayarlayın, bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  Bu kod örneği doğru kullanımı gösterilmiştir `vector<bool>::operator[]` ve iki ortak kodlama dışı bırakılır hatalar. Bu hataları için hataları neden adresini `vector<bool>::reference` nesnesinin `vector<bool>::operator[]` döndürür olamaz alınabilir.  
  
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
  
##  <a name="pointer"></a>vektör\<bool >:: işaretçi  
 Bir Boole öğesi tarafından bulunan dizisi için bir işaretçi olarak hizmet verebilir bir nesneyi tanımlayan bir tür `vector<bool>` nesnesi.  
  
```  
typedef iterator pointer;  
```  
  
##  <a name="reference_class"></a>vektör\<bool >:: sınıfı başvurusu  
 `vector<bool>::reference` Sınıftır tarafından sağlanan bir proxy [vektör\<bool > sınıfı](../standard-library/vector-bool-class.md) benzetimini yapmak için `bool&`.  
  
### <a name="remarks"></a>Açıklamalar  
 C++ yerel olarak doğrudan başvuruların bitlere atanmasına izin vermediğinden, benzetimli bir başvuru gereklidir. `vector<bool>`Bu proxy sınıfını kullanarak başvurulabilir öğesi başına yalnızca bir bit kullanır. Bununla birlikte, belirli atamalar geçersiz olduğundan başvuru benzetimi tam değil. Örneğin, çünkü adresini `vector<bool>::reference` nesne olamaz alınması, kullandığı aşağıdaki kodu [vektör\<bool >:: işleci &#91; &#93;](#op_at) doğru değil:  
  
```cpp  
vector<bool> vb;  
//...  
bool* pb = &vb[1]; // conversion error - do not use  
bool& refb = vb[1];   // conversion error - do not use  
```  
  
###  <a name="reference_flip"></a>vektör\<bool >:: reference::flip  
 Başvurulan bir Boolean değerini tersine çevirir [vektör\<bool >](../standard-library/vector-bool-class.md) öğesi.  
  
```  
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
  
###  <a name="reference_operator_bool"></a>vektör\<bool >:: reference::operator bool  
 Örtük bir dönüştürme sağlar `vector<bool>::reference` için `bool`.  
  
```  
operator bool() const;
```  
  
#### <a name="return-value"></a>Dönüş Değeri  
 Vektör öğesinin Boole değeri\<bool > nesne.  
  
#### <a name="remarks"></a>Açıklamalar  
 `vector<bool>` Nesne bu operatör tarafından değiştirilemez.  
  
###  <a name="reference_operator_eq"></a>vektör\<bool >:: reference::operator =  
 Bir bite bir Boolean değeri, veya başvurulan bir öğenin tuttuğu değeri atar.  
  
```  
reference& operator=(const reference& Right);
reference& operator=(bool Val);
```  
  
#### <a name="parameters"></a>Parametreler  
 `Right`  
 Değerinin bite atanacağı öğe başvurusu.  
  
 `Val`  
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
  
##  <a name="swap"></a>vektör\<bool >:: değiştirme  
 İki öğeden Boolean vektörlerinin alış verişleri statik üye işlevi ( `vector<bool>`) proxy sınıfını kullanarak [vektör\<bool >:: başvuru](#reference_class).  
  
```  
static void swap(
    reference Left,  
    reference Right);
```  
  
### <a name="parameters"></a>Parametreler  
 `Left`  
 İle değiştirilmek üzere öğesi `Right` öğesi.  
  
 `Right`  
 İle değiştirilmek üzere öğesi `Left` öğesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu aşırı özel proxy gereksinimlerini destekler `vector<bool>`. [vektör](../standard-library/vector-class.md):: takas tek bağımsız değişkenli aşırı yüklemesini aynı işlevselliğe sahip `vector<bool>::swap()`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

