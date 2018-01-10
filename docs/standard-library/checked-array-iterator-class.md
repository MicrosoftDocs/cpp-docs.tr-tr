---
title: "checked_array_iterator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/checked_array_iterator
- iterator/stdext::checked_array_iterator::difference_type
- iterator/stdext::checked_array_iterator::pointer
- iterator/stdext::checked_array_iterator::reference
- iterator/stdext::checked_array_iterator::base
dev_langs: C++
helpviewer_keywords:
- stdext::checked_array_iterator [C++], difference_type
- stdext::checked_array_iterator [C++], pointer
- stdext::checked_array_iterator [C++], reference
- stdext::checked_array_iterator [C++], base
ms.assetid: 7f07185e-d588-4ae3-9c4f-84ec4aa25a28
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97e0a5f9276d6ae9f4c5b4dea289227e59437525
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="checkedarrayiterator-class"></a>checked_array_iterator Sınıfı
`checked_array_iterator` Sınıfı bir dizi veya işaretçi denetlenen yineleyici dönüştürmenizi sağlar. Bu sınıf kapsayıcı olarak kullanın (kullanarak [make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator) işlevi) ham işaretçileri veya denetimi sağlamak için ve genel olarak bu uyarılar silencing yerine denetlenmeyen işaretçi Uyarıları yönetmek için hedeflenen bir yöntem olarak diziler için. Gerekirse, bu sınıfın denetlenmeyen sürümü kullanabilirsiniz, [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md).  
  
> [!NOTE]
>  Bu sınıf, C++ Standart Kitaplığı, bir Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir. Örneğin, bu sınıfın kullanımını gerektirmeyen kodun nasıl yazılacağını gösteren bir örnek için, aşağıdaki ikinci örneğe bakın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class _Iterator>  
class checked_array_iterator;
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf tanımlanan [stdext](../standard-library/stdext-namespace.md) ad alanı.  
  
 Daha fazla bilgi ve örnek kod denetlenen yineleyici özelliği için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek denetlenen bir dizi yineleyicisinin nasıl tanımlanacağını ve kullanılacağını göstermektedir.  
  
 Hedef kopyalanan öğeleri tutmak için yeterince büyük değilse, satırı değiştirdiyseniz duruma göre şöyle olur:  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 5));
```  
  
 to  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 4));
```  
  
 Bir çalışma zamanı hatası oluşur.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[]={0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
  
   // constructor example  
   checked_array_iterator<int*> checked_out_iter(b, 5);  
   copy(a, a + 5, checked_out_iter);  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
}  
\* Output:   
( 0 1 2 3 4 )  
( 0 1 2 3 4 )  
*\  
```  
  
## <a name="example"></a>Örnek  
 Gereksinimini önlemek için `checked_array_iterator` Sınıf C++ Standart Kitaplığı algoritmaları kullanırken, kullanmayı bir `vector` dinamik olarak ayrılan bir dizi yerine. Aşağıdaki örnek bunun nasıl yapılacağını göstermektedir.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main()  
{  
    std::vector<int> v(10);  
    int *arr = new int[10];  
    for (int i = 0; i < 10; ++i)  
    {  
        v[i] = i;  
        arr[i] = i;  
    }  
  
    // std::copy(v.begin(), v.end(), arr); will result in  
    // warning C4996. To avoid this warning while using int *,  
    // use the Microsoft extension checked_array_iterator.  
    std::copy(v.begin(), v.end(),  
              stdext::checked_array_iterator<int *>(arr, 10));  
  
    // Instead of using stdext::checked_array_iterator and int *,  
    // consider using std::vector to encapsulate the array. This will  
    // result in no warnings, and the code will be portable.  
    std::vector<int> arr2(10);    // Similar to int *arr = new int[10];  
    std::copy(v.begin(), v.end(), arr2.begin());  
  
    for (int j = 0; j < arr2.size(); ++j)  
    {  
        cout << " " << arr2[j];  
    }  
    cout << endl;  
  
    return 0;  
}  
\* Output:   
 0 1 2 3 4 5 6 7 8 9  
*\  
```  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[checked_array_iterator](#checked_array_iterator)|Varsayılan yapıları `checked_array_iterator` veya `checked_array_iterator` temel yineleyici gelen.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[difference_type](#difference_type)|İkisi arasındaki farkı sağlayan bir türü `checked_array_iterator`aynı kapsayıcı içindeki öğelerine başvuran s.|  
|[İşaretçi](#pointer)|Tarafından gönderilen bir öğe için bir işaretçi sağlayan bir türü bir `checked_array_iterator`.|  
|[başvuru](#reference)|Bir öğe tarafından ele başvuru sağlayan bir türü bir `checked_array_iterator`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[base](#base)|Temel alınan yineleyici gelen kurtarır kendi `checked_array_iterator`.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator ==](#op_eq_eq)|İki testleri `checked_array_iterator`eşitliği s.|  
|[operator!=](#op_neq)|İki testleri `checked_array_iterator`eşitsizlik açısından s.|  
|[operator <](#op_lt)|Varsa testleri `checked_array_iterator` işlecinin sol tarafında küçük `checked_array_iterator` sağ tarafında.|  
|[operator >](#op_gt)|Varsa testleri `checked_array_iterator` işlecinin sol tarafında değerinden daha büyük `checked_array_iterator` sağ tarafında.|  
|[operator < =](#op_lt_eq)|Varsa testleri `checked_array_iterator` işlecinin sol tarafında küçük veya buna eşit olduğundan `checked_array_iterator` sağ tarafında.|  
|[operator>=](#op_gt_eq)|Varsa testleri `checked_array_iterator` işlecinin sol tarafında büyüktür veya şuna eşittir: `checked_array_iterator` sağ tarafında.|  
|[işleç *](#op_star)|Öğesini döndüren bir `checked_array_iterator` adresleri.|  
|[-> işleci](#operator-_gt)|Tarafından ele öğesine bir işaretçi döndüren `checked_array_iterator`.|  
|[operator ++](#op_add_add)|Artışlarla `checked_array_iterator` sonraki öğeye.|  
|[--işleci](#operator--)|Azaltır `checked_array_iterator` önceki öğesi.|  
|[+= işleci](#op_add_eq)|Belirtilen uzaklık ekler bir `checked_array_iterator`.|  
|[operator +](#op_add)|Yineleyici için uzaklık ekler ve yeni döndürür `checked_array_iterator` yeni uzaklık konumunda eklenen öğesi adresleme.|  
|[-= işleci](#operator-_eq)|Azaltır belirtilen uzaklığı bir `checked_array_iterator`.|  
|[operator-](#operator-)|Yineleyici uzaklığı bir azaltır ve yeni döndürür `checked_array_iterator` yeni uzaklık konumunda eklenen öğesi adresleme.|  
|[operator &#91; &#93;](#op_at)|Bir öğe uzaklık başvuru tarafından ele öğeden döndürür bir `checked_array_iterator` konumlar belirtilen sayısı.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yineleyici >  
  
 **Namespace:** stdext  
  
##  <a name="base"></a>checked_array_iterator::Base  
 Temel alınan yineleyici gelen kurtarır kendi `checked_array_iterator`.  
  
```
_Iterator base() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_base.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace std;  
  
   int V1[10];  
  
   for (int i = 0; i < 10 ; i++)  
      V1[i] = i;  
  
   int* bpos;  
  
   stdext::checked_array_iterator<int*> rpos(V1, 10);  
   rpos++;  
  
   bpos = rpos.base ( );  
   cout << "The iterator underlying rpos is bpos & it points to: "   
        << *bpos << "." << endl;  
}  
\* Output:   
The iterator underlying rpos is bpos & it points to: 1.  
*\  
```  
  
##  <a name="checked_array_iterator"></a>checked_array_iterator::checked_array_iterator  
 Varsayılan yapıları `checked_array_iterator` veya `checked_array _iterator` temel yineleyici gelen.  
  
```
checked_array_iterator();

checked_array_iterator(
    ITerator ptr,
    size_t size,
    size_t index = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptr`  
 Dizi için bir işaretçi.  
  
 `size`  
 Dizinin boyutu.  
  
 `index`  
 (İsteğe bağlı) Yineleyici başlatmak için bu dizide öğe.  Varsayılan olarak, yineleyici dizinin ilk öğe için başlatılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_ctor.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   for (int i = 0 ; i < 5 ; i++)  
      cout << b[i] << " ";  
   cout << endl;  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   copy (a, a + 5, checked_output_iterator);  
   for (int i = 0 ; i < 5 ; i++)  
      cout << b[i] << " ";  
   cout << endl;  
  
   checked_array_iterator<int*> checked_output_iterator2(b,5,3);  
   cout << *checked_output_iterator2 << endl;  
}  
\* Output:   
0 1 2 3 4   
0 1 2 3 4   
3  
*\  
```  
  
##  <a name="difference_type"></a>checked_array_iterator::difference_type  
 İkisi arasındaki farkı sağlayan bir türü `checked_array_iterator`aynı kapsayıcı içindeki öğelerine başvuran s.  
  
```
typedef typename iterator_traits<_Iterator>::difference_type difference_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `checked_array_iterator` Fark türüdür yineleyici fark türü ile aynı.  
  
 Bkz: [checked_array_iterator::operator []](#op_at) bir kod örneği için.  
  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
##  <a name="op_eq_eq"></a>checked_array_iterator::operator ==  
 İki testleri `checked_array_iterator`eşitliği s.  
  
```
bool operator==(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 `checked_array_iterator` Olan eşitlik için denetleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_opeq.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 == checked_output_iterator)  
      cout << "checked_array_iterators are equal" << endl;  
   else  
      cout << "checked_array_iterators are not equal" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 == checked_output_iterator)  
      cout << "checked_array_iterators are equal" << endl;  
   else  
      cout << "checked_array_iterators are not equal" << endl;  
}  
\* Output:   
checked_array_iterators are equal  
checked_array_iterators are not equal  
*\  
```  
  
##  <a name="op_neq"></a>checked_array_iterator::operator! =  
 İki testleri `checked_array_iterator`eşitsizlik açısından s.  
  
```
bool operator!=(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 `checked_array_iterator` Olan eşitsizlik için denetleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_opneq.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 != checked_output_iterator)  
      cout << "checked_array_iterators are not equal" << endl;  
   else  
      cout << "checked_array_iterators are equal" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 != checked_output_iterator)  
      cout << "checked_array_iterators are not equal" << endl;  
   else  
      cout << "checked_array_iterators are equal" << endl;  
}  
\* Output:   
checked_array_iterators are equal  
checked_array_iterators are not equal  
*\  
```  
  
##  <a name="op_lt"></a>checked_array_iterator::operator&lt;  
 Varsa testleri `checked_array_iterator` işlecinin sol tarafında küçük `checked_array_iterator` sağ tarafında.  
  
```
bool operator<(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 `checked_array_iterator` Olan eşitsizlik için denetleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_oplt.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 < checked_output_iterator)  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is not less than checked_output_iterator" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 < checked_output_iterator)  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is not less than checked_output_iterator" << endl;  
}  
\* Output:   
checked_output_iterator2 is not less than checked_output_iterator  
checked_output_iterator2 is less than checked_output_iterator  
*\  
```  
  
##  <a name="op_gt"></a>checked_array_iterator::operator&gt;  
 Varsa testleri `checked_array_iterator` işlecinin sol tarafında değerinden daha büyük `checked_array_iterator` sağ tarafında.  
  
```
bool operator>(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 `checked_array_iterator` Karşılaştırılacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [checked_array_iterator::operator&lt; ](#op_lt) bir kod örneği için.  
  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
##  <a name="lt_eq"></a>checked_array_iterator::operator&lt;=  
 Varsa testleri `checked_array_iterator` işlecinin sol tarafında küçük veya buna eşit olduğundan `checked_array_iterator` sağ tarafında.  
  
```
bool operator<=(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 `checked_array_iterator` Karşılaştırılacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [checked_array_iterator::operator&gt; = ](#op_gt_eq) bir kod örneği için.  
  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
##  <a name="gt_eq"></a>checked_array_iterator::operator&gt;=  
 Varsa testleri `checked_array_iterator` işlecinin sol tarafında büyüktür veya şuna eşittir: `checked_array_iterator` sağ tarafında.  
  
```
bool operator>=(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 `checked_array_iterator` Karşılaştırılacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_opgteq.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 >= checked_output_iterator)  
      cout << "checked_output_iterator2 is greater than or equal to checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 >= checked_output_iterator)  
      cout << "checked_output_iterator2 is greater than or equal to checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
}  
\* Output:   
checked_output_iterator2 is greater than or equal to checked_output_iterator  
checked_output_iterator2 is less than checked_output_iterator  
*\  
```  
  
##  <a name="op_star"></a>checked_array_iterator::operator *  
 Öğesini döndüren bir `checked_array_iterator` adresleri.  
  
```
reference operator*() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından açıklanan öğenin değerini `checked_array_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterator_pointer.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <utility>  
#include <iostream>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   pair<int, int> c[1];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   for (int i = 0 ; i < 5 ; i++)  
      cout << b[i] << endl;  
  
    c[0].first = 10;  
    c[0].second = 20;  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*>::pointer p = &(*checked_output_iterator);  
   checked_array_iterator<pair<int, int>*> chk_c(c, 1);  
   checked_array_iterator<pair<int, int>*>::pointer p_c = &(*chk_c);  
  
   cout << "b[0] = " << *p << endl;  
   cout << "c[0].first = " << p_c->first << endl;  
}  
\* Output:   
0  
1  
2  
3  
4  
b[0] = 0  
c[0].first = 10  
*\  
```  
  
##  <a name="checked_array_iterator__operator-_gt"></a>checked_array_iterator::operator-&gt;  
 Tarafından ele öğesine bir işaretçi döndüren `checked_array_iterator`.  
  
```
pointer operator->() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından ele öğesi için bir işaretçi `checked_array_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [checked_array_iterator::pointer](#pointer) bir kod örneği için.  
  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
##  <a name="op_add_add"></a>checked_array_iterator::operator ++  
 Artışlarla `checked_array_iterator` sonraki öğeye.  
  
```
checked_array_iterator& operator++();

checked_array_iterator<_Iterator> operator++(int);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk işleci preincremented döndürür `checked_array_iterator` ve postincrement işleci ikinci bir kopyası artırılır döndürür `checked_array_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_op_plus_plus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   ++checked_output_iterator;  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator++;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
3  
77  
*\  
```  
  
##  <a name="checked_array_iterator__operator--"></a>checked_array_iterator::operator--  
 Azaltır `checked_array_iterator` önceki öğesi.  
  
```
checked_array_iterator<_Iterator>& operator--();

checked_array_iterator<_Iterator> operator--(int);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk işleci predecremented döndürür `checked_array_iterator` ve postdecrement işleci ikinci bir kopyası indirildiği döndürür `checked_array_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_op_minus_minus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator++;  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator--;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
3  
6  
*\  
```  
  
##  <a name="op_add_eq"></a>checked_array_iterator::operator +=  
 Belirtilen uzaklık ekler bir `checked_array_iterator`.  
  
```
checked_array_iterator<_Iterator>& operator+=(difference_type _Off);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Yineleyici artırmak üzere uzaklığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru tarafından ele öğesine `checked_array_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_op_plus_eq.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator += 3;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
199  
*\  
```  
  
##  <a name="op_add"></a>checked_array_iterator::operator +  
 Yineleyici için uzaklık ekler ve yeni döndürür `checked_array_iterator` yeni uzaklık konumunda eklenen öğesi adresleme.  
  
```
checked_array_iterator<_Iterator> operator+(difference_type _Off) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Eklenecek uzaklık `checked_array_iterator`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `checked_array_iterator` uzaklık öğesi adresleme.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_op_plus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator = checked_output_iterator + 3;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
199  
*\  
```  
  
##  <a name="checked_array_iterator__operator-_eq"></a>checked_array_iterator::operator-=  
 Azaltır belirtilen uzaklığı bir `checked_array_iterator`.  
  
```
checked_array_iterator<_Iterator>& operator-=(difference_type _Off);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Yineleyici artırmak üzere uzaklığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru tarafından ele öğesine `checked_array_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_op_minus_eq.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   checked_output_iterator += 3;  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator -= 2;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
199  
3  
*\  
```  
  
##  <a name="checked_array_iterator__operator-"></a>checked_array_iterator::operator-  
 Yineleyici uzaklığı bir azaltır ve yeni döndürür `checked_array_iterator` yeni uzaklık konumunda eklenen öğesi adresleme.  
  
```
checked_array_iterator<_Iterator> operator-(difference_type _Off) const;

difference_type operator-(const checked_array_iterator& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Uzaklık gelen azaltılır `checked_array_iterator`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `checked_array_iterator` uzaklık öğesi adresleme.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [checked_array_iterator::operator -](#operator-) bir kod örneği için.  
  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
##  <a name="op_at"></a>checked_array_iterator::operator]  
 Bir öğe uzaklık başvuru tarafından ele öğeden döndürür bir `checked_array_iterator` konumlar belirtilen sayısı.  
  
```
reference operator[](difference_type _Off) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Uzaklık `checked_array_iterator` adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe uzaklık referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// checked_array_iterators_op_diff.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace std;     
   int V1[10];  
  
   for (int i = 0; i < 10 ; i++)  
      V1[i] = i;  
  
   // Declare a difference type for a parameter  
   stdext::checked_array_iterator<int*>::difference_type diff = 2;  
  
   stdext::checked_array_iterator<int*> VChkIter(V1, 10);  
  
   stdext::checked_array_iterator<int*>::reference refrpos = VChkIter [diff];  
  
   cout << refrpos + 1 << endl;  
}  
\* Output:   
3  
*\  
```  
  
##  <a name="pointer"></a>checked_array_iterator::pointer  
 Tarafından gönderilen bir öğe için bir işaretçi sağlayan bir türü bir `checked_array_iterator`.  
  
```
typedef typename iterator_traits<_Iterator>::pointer pointer;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [checked_array_iterator::operator *](#op_star) bir kod örneği için.  
  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
##  <a name="reference"></a>checked_array_iterator::Reference  
 Bir öğe tarafından ele başvuru sağlayan bir türü bir `checked_array_iterator`.  
  
```
typedef typename iterator_traits<_Iterator>::reference reference;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [checked_array_iterator::operator []](#op_at) bir kod örneği için.  
  
 Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Yineleyici >](../standard-library/iterator.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



