---
title: priority_queue (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue
- cliext::priority_queue::assign
- cliext::priority_queue::const_reference
- cliext::priority_queue::container_type
- cliext::priority_queue::difference_type
- cliext::priority_queue::empty
- cliext::priority_queue::generic_container
- cliext::priority_queue::generic_value
- cliext::priority_queue::get_container
- cliext::priority_queue::operator=
- cliext::priority_queue::pop
- cliext::priority_queue::priority_queue
- cliext::priority_queue::push
- cliext::priority_queue::reference
- cliext::priority_queue::size
- cliext::priority_queue::size_type
- cliext::priority_queue::to_array
- cliext::priority_queue::top
- cliext::priority_queue::top_item
- cliext::priority_queue::value_comp
- cliext::priority_queue::value_compare
- cliext::priority_queue::value_type
dev_langs:
- C++
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
- assign member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- priority_queue member [STL/CLR]
- push member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- to_array member [STL/CLR]
- top member [STL/CLR]
- top_item member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 573b365e0ca0d1c5b607144b1d143796e1ce927c
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42465272"
---
# <a name="priorityqueue-stlclr"></a>priority_queue (STL/CLR)
Şablon sınıfı bir değişen sınırlı erişimi öğe dizisi sıralı uzunluktaki denetleyen bir nesneyi tanımlar. Kapsayıcı bağdaştırıcısı kullandığınız `priority_queue` temel alınan bir kapsayıcı öncelikli bir kuyruk olarak yönetilecek.  
  
 Aşağıdaki açıklamada `GValue` aynı *değer* ikinci bir başvuru türü olmadığı sürece olduğu durumda `Value^`. Benzer şekilde, `GContainer` aynı *kapsayıcı* ikinci bir başvuru türü olmadığı sürece olduğu durumda `Container^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Value,  
    typename Container>  
    ref class priority_queue  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>  
    { ..... };  
```  
  
### <a name="parameters"></a>Parametreler  
 *Değer*  
 Denetlenen sıradaki öğenin türü.  
  
 *Kapsayıcı*  
 Temel alınan kapsayıcı türü.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  

## <a name="declarations"></a>Bildirimler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[priority_queue::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|  
|[priority_queue::container_type (STL/CLR)](#container_type)|Temel alınan kapsayıcı türü.|  
|[priority_queue::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|  
|[priority_queue::generic_container (STL/CLR)](#generic_container)|Kapsayıcı bağdaştırıcısı için genel arabirim türü.|  
|[priority_queue::generic_value (STL/CLR)](#generic_value)|Kapsayıcı bağdaştırıcısı için genel arabirimi için bir öğe türü.|  
|[priority_queue::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|  
|[priority_queue::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|  
|[priority_queue::value_compare (STL/CLR)](#value_compare)|İki öğe sipariş temsilcisi.|  
|[priority_queue::value_type (STL/CLR)](#value_type)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[priority_queue::assign (STL/CLR)](#assign)|Tüm öğeleri değiştirir.|  
|[priority_queue::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|  
|[priority_queue::get_container (STL/CLR)](#get_container)|Temel alınan kapsayıcı erişir.|  
|[priority_queue::pop (STL/CLR)](#pop)|Hghest öncelikli öğeyi kaldırır.|  
|[priority_queue::priority_queue (STL/CLR)](#priority_queue)|Bir kapsayıcı nesnesi oluşturur.|  
|[priority_queue::push (STL/CLR)](#push)|Yeni bir öğe ekler.|  
|[priority_queue::size (STL/CLR)](#size)|Öğe sayısını sayar.|  
|[priority_queue::top (STL/CLR)](#top)|En yüksek öncelikli öğenin erişir.|  
|[priority_queue::to_array (STL/CLR)](#to_array)|Denetlenen dizideki, yeni bir diziye kopyalar.|  
|[priority_queue::value_comp (STL/CLR)](#value_comp)|İki öğe sipariş temsilcisi kopyalar.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[priority_queue::top_item (STL/CLR)](#top_item)|En yüksek öncelikli öğenin erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[priority_queue::operator= (STL/CLR)](#op_as)|Denetlenen dizi değiştirir.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Bir nesne çoğaltın.|  
|IPriorityQueue\<değeri, kapsayıcı >|Genel bir kapsayıcı bağdaştırıcısı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesneyi ayırır ve serbest bırakma türü temel alınan bir kapsayıcının denetlediği dizi için depolama `Container`, depolayan `Value` öğeleri ve istek üzerine büyür. En yüksek öncelikli öğe (üst öğe) kolayca erişilebilir ve taşınabilir bir yığın olarak sıralı sürdürür. Yeni öğeler gönderme ve yalnızca en yüksek öncelikli öğesi, öncelikli bir kuyruk uygulama pencerelerinin, nesne erişimi kısıtlar.  
  
 Nesne türünde bir saklı temsilci nesnesi çağırarak denetlediği diziyi sıralar [priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md). Priority_queue oluştururken saklı temsilci nesnesi belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, karşılaştırma varsayılandır `operator<(value_type, value_type)`. Üye işlevini çağırarak depolanan bu nesne erişim [priority_queue::value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)`()`.  
  
 Bu tür bir temsilci nesnesinin katı bir zayıf türünün değerleri üzerinde sıralama dayatır gerekir [priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md). Anlamına gelir, için iki anahtar `X` ve `Y`:  
  
 `value_comp()(X, Y)` Her çağrıda aynı Boolean sonucu döndürür.  
  
 Varsa `value_comp()(X, Y)` true ise `value_comp()(Y, X)` false olmalıdır.  
  
 Varsa `value_comp()(X, Y)` true ise `X` önce sıralanmalıdır söylenir `Y`.  
  
 Varsa `!value_comp()(X, Y) && !value_comp()(Y, X)` true ise `X` ve `Y` eşdeğer sıralamaya olduğu söylenir.  
  
 Herhangi bir öğe için `X` metninden önce `Y` denetlenen dizideki `key_comp()(Y, X)` false'tur. (Varsayılan temsilci nesne için anahtarları asla değerini azaltın.)  
  
 En yüksek öncelikli öğenin bu nedenle, diğer bir öğesinden önce sıralanır değil öğeleri biridir.  
  
 Bu yana temel alınan kapsayıcı öğeler bir yığın olarak sıralı tutar:  
  
 Kapsayıcı, rasgele erişim yineleyicileri desteklemesi gerekir.  
  
 Gönderildi olandan farklı bir sırada eşdeğer sıralamaya sahip öğelerin POP. (Sıralaması sağlam değil.)  
  
 Bu nedenle, temel alınan kapsayıcı için aday dahil [deque (STL/CLR)](../dotnet/deque-stl-clr.md) ve [vektör (STL/CLR)](../dotnet/vector-stl-clr.md).  
  
## <a name="members"></a>Üyeler
  
## <a name="assign"></a> priority_queue::Assign (STL/CLR)
Tüm öğeleri değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void assign(priority_queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *sağ*  
 Eklenecek kapsayıcı Bağdaştırıcısı'nı tıklatın.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi atar `right.get_container()` temel alınan kapsayıcısı. Sıranın tüm içeriğini değiştirmek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_assign.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign a repetition of values   
    Mypriority_queue c2;   
    c2.assign(c1);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c a b  
c a b  
```  

## <a name="const_reference"></a> priority_queue::const_reference (STL/CLR)
Bir öğe için sabit bir başvuru türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe için sabit bir başvuru türü açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_const_reference.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " c b a"   
    for (; !c1.empty(); c1.pop())   
        {   // get a const reference to an element   
        Mypriority_queue::const_reference cref = c1.top();   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c b a  
```  

## <a name="container_type"></a> priority_queue::container_type (STL/CLR)
Temel alınan kapsayıcı türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef Container value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eşanlamlı türüdür `Container`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_container_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Mypriority_queue::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c a b  
```  

## <a name="difference_type"></a> priority_queue::difference_type (STL/CLR)
İki öğe arasındaki işaretli mesafenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Büyük olasılıkla negatif öğe sayısını tanımlayan bir tür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_difference_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute negative difference   
    Mypriority_queue::difference_type diff = c1.size();   
    c1.push(L'd');   
    c1.push(L'e');   
    diff -= c1.size();   
    System::Console::WriteLine("pushing 2 = {0}", diff);   
  
// compute positive difference   
    diff = c1.size();   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    diff -= c1.size();   
    System::Console::WriteLine("popping 3 = {0}", diff);   
    return (0);   
    }  
```  
  
```Output  
 c a b  
pushing 2 = -2  
popping 3 = 3  
```  

## <a name="empty"></a> priority_queue::Empty (STL/CLR)
Bir öğe olup olmadığını sınar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
bool empty();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş bir denetlenmiş dizi için true değerini döndürür. Eşdeğerdir [priority_queue::size (STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)`() == 0`. Priority_queue boş olup olmadığını sınamak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_empty.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
```  
  
```Output  
 c a b  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  

## <a name="generic_container"></a> priority_queue::generic_container (STL/CLR)
Kapsayıcı için genel arabirim türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef Microsoft::VisualC::StlClr::IPriorityQueue<Value>  
    generic_container;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon kapsayıcı bağdaştırıcısı sınıfın genel arabirim tanımlayan bir tür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_generic_container.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mypriority_queue::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->push(L'd');   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.push(L'e');   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c a b  
c a b  
d c b a  
e d b a c  
```  

## <a name="generic_value"></a> priority_queue::generic_value (STL/CLR)
Kapsayıcı için genel arabirimi ile kullanmak için bir öğe türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türünde bir nesneyi tanımlayan bir tür `GValue` açıklayan yönelik genel arabirimi için bu şablonu kapsayıcı sınıfı ile kullanmak için depolanan öğenin değeri. (`GValue` ya da `value_type` veya `value_type^` varsa `value_type` bir başvuru türüdür.)  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_generic_value.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get interface to container   
    Mypriority_queue::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display in priority order using generic_value   
    for (; !gc1->empty(); gc1->pop())   
        {   
        Mypriority_queue::generic_value elem = gc1->top();   
  
        System::Console::Write(" {0}", elem);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c a b  
c a b  
c b a  
```  

## <a name="get_container"></a> priority_queue::get_container (STL/CLR)
Temel alınan kapsayıcı erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
container_type get_container();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, temel alınan kapsayıcı döndürür. Kapsayıcı sarmalayıcı tarafından uygulanan kısıtlamalar atlamak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_get_container.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c a b  
```  

## <a name="op_as"></a> priority_queue::operator (STL/CLR) =
Denetlenen dizi değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
priority_queue <Value, Container>% operator=(priority_queue <Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *sağ*  
 Kopyalanacak kapsayıcı Bağdaştırıcısı'nı tıklatın.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci kopyaları *doğru* ardından nesneye döndürür `*this`. Denetlenen dizi denetlenen dizide bir kopyasını değiştirmek için kullandığınız *doğru*.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_operator_as.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mypriority_queue c2;   
    c2 = c1;   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
c a b  
c a b  
```  

## <a name="pop"></a> priority_queue::POP (STL/CLR)
En yüksek proirity öğeyi kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void pop();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizinin boş olması gereken en yüksek öncelikli öğeyi kaldırır. Arkasından bir öğe tarafından sıraya kısaltmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_pop.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop();   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c a b  
b a  
```  

## <a name="priority_queue"></a> priority_queue::priority_queue (STL/CLR)
Bir kapsayıcı bağdaştırıcısı nesnesi oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
priority_queue();  
priority_queue(priority_queue<Value, Container> right);  
priority_queue(priority_queue<Value, Container> right);  
explicit priority_queue(value_compare^ pred);  
priority_queue(value_compare^ pred, container_type% cont);  
template<typename InIt>  
    priority_queue(InIt first, InIt last);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred, container_type% cont);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *devamı*  
 Kopyalanacak kapsayıcı.  
  
 *ilk*  
 Eklenecek Aralık başlangıcı.  
  
 *Son*  
 Eklenecek aralık sonu.  
  
 *Pred*  
 Denetlenen dizi için koşul sıralaması.  
  
 *sağ*  
 Nesne veya eklenecek aralık.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu:  
  
 `priority_queue();`  
  
 Varsayılan karşılaştırma sıralama ile boş bir Sarmalanan kapsayıcı oluşturur. Koşul sıralama varsayılan bir boş ilk denetlenen sıra belirtmek için kullanın.  
  
 Oluşturucu:  
  
 `priority_queue(priority_queue<Value, Container>% right);`  
  
 kopyası olan bir sarmalanmış bir kapsayıcı oluşturur `right.get_container()`, sıralama koşul ile `right.value_comp()`. Kuyruk nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız *doğru*, aynı sıralama koşul ile.  
  
 Oluşturucu:  
  
 `priority_queue(priority_queue<Value, Container>^ right);`  
  
 kopyası olan bir sarmalanmış bir kapsayıcı oluşturur `right->get_container()`, sıralama koşul ile `right->value_comp()`. Kuyruk nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız `*right`, aynı sıralama koşul ile.  
  
 Oluşturucu:  
  
 `explicit priority_queue(value_compare^ pred);`  
  
 Sıralama koşul ile boş bir Sarmalanan kapsayıcı oluşturur *pred*. Bir boş ilk denetlenen sıra ile belirtilen sıralama koşulu belirtmek için kullanın.  
  
 Oluşturucu:  
  
 `priority_queue(value_compare^ pred, container_type cont);`  
  
 Sıralama koşul ile boş bir Sarmalanan kapsayıcı oluşturur *pred*, ardından tüm öğelerini gönderim *devamı* denetimli dizisinden ilk var olan bir kapsayıcıyı belirtmek için kullanın belirtilen sıralama koşul.  
  
 Oluşturucu:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last);`  
  
 Varsayılan sıralama koşul ile boş bir Sarmalanan kapsayıcı oluşturur, ardından dizisi iter [`first`, `last`). Belirtilen sıralama koşul ile belirtilen bir eqeuence ilk denetimli dizisinden belirtmek için kullanın.  
  
 Oluşturucu:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`  
  
 Sıralama koşul ile boş bir Sarmalanan kapsayıcı oluşturur *pred*, ardından dizisi iter [`first`, `last`). Belirtilen sıralama koşul ile belirtilen bir seqeuence ilk denetimli dizisinden belirtmek için kullanın.  
  
 Oluşturucu:  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`  
  
 Sıralama koşul ile boş bir Sarmalanan kapsayıcı oluşturur *pred*, ardından tüm öğelerini gönderim *devamı* dizisi artı [`first`, `last`). Var olan bir kapsayıcı ve belirtilen bir seqeuence ilk denetimli dizisi ile belirtilen sıralama koşulu belirtmek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/deque>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
typedef cliext::deque<wchar_t> Mydeque;   
int main()   
    {   
// construct an empty container   
    Mypriority_queue c1;   
    Mypriority_queue::container_type^ wc1 = c1.get_container();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    for each (wchar_t elem in wc1)   
        c2.push(elem);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule by copying an underlying container   
    Mypriority_queue c2x =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
   for each (wchar_t elem in c2x.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mypriority_queue c3(wc1->begin(), wc1->end());   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mypriority_queue c4(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>());   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range, another container, and an ordering rule   
    Mypriority_queue c5(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c5.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mypriority_queue c6(c3);   
    for each (wchar_t elem in c6.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mypriority_queue c7(%c3);   
    for each (wchar_t elem in c7.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule, by copying an underlying container   
    Mypriority_queue c8 =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c8.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
```  
  
```Output  
size() = 0  
 c a b  
size() = 0  
 a c b  
 a c b  
 c a b  
 a c b  
 a a b c c b  
 c a b  
 c a b  
 a c b  
```  
  
## <a name="push"></a> priority_queue::push (STL/CLR)
Yeni bir öğe ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void push(value_type val);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi değere sahip bir öğe ekler `val` denetlenen bir dizi içine ve yığın uzmanlık alanı korumak için denetlenen dizideki yeniden sıralar. Kuyruğa başka bir öğe eklemek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_push.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c a b  
```  
  
## <a name="reference"></a> priority_queue::Reference (STL/CLR)
Bir öğe için bir başvuru türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğeye bir başvuru türü açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_reference.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify top of priority_queue and redisplay   
    Mypriority_queue::reference ref = c1.top();   
    ref = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c a b  
x a b  
```  

## <a name="size"></a> priority_queue::size (STL/CLR)
Öğe sayısını sayar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
size_type size();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizinin uzunluğunu döndürür. Şu anda denetlenen dizideki öğelerin sayısını belirlemek için kullanın. Tümü, önem verdiğiniz ise dizisi bakın, sıfır olmayan boyutu olup [priority_queue::empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)`()`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_size.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// pop an item and reinspect   
    c1.pop();   
    System::Console::WriteLine("size() = {0} after popping", c1.size());   
  
// add two elements and reinspect   
    c1.push(L'a');   
    c1.push(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
```  
  
```Output  
 c a b  
size() = 3 starting with 3  
size() = 2 after popping  
size() = 4 after adding 2  
```  

## <a name="size_type"></a> priority_queue::size_type (STL/CLR)
İki öğe arasındaki işaretli mesafenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir negatif olmayan öğe sayısını tanımlayan bir tür.  
  
### <a name="example"></a>Örnek  
  
```cpp 
// cliext_priority_queue_size_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mypriority_queue::size_type diff = c1.size();   
    c1.pop();   
    c1.pop();   
    diff -= c1.size();   
    System::Console::WriteLine("size difference = {0}", diff);   
    return (0);   
    }  
```  
  
```Output  
 c a b  
size difference = 2  
```  
  
## <a name="to_array"></a> priority_queue::to_array (STL/CLR)
Denetlenen dizideki, yeni bir diziye kopyalar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen bir dizi içeren bir dizi döndürür. Dizi formunda denetlenen dizinin bir kopyasını almak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_to_array.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push(L'd');   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
d c b a  
c a b  
```  

## <a name="top"></a> priority_queue::Top (STL/CLR)
En yüksek öncelikli öğenin erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
reference top();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizinin boş olması gereken üst (en yüksek öncelik) öğesine bir başvuru döndürür. Mevcut bildiğinizde, en yüksek öncelikli öğenin erişmek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_top.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top() = {0}", c1.top());   
  
// alter last item and reinspect   
    c1.top() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  

## <a name="top_item"></a> priority_queue::top_item (STL/CLR)
En yüksek öncelikli öğenin erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
property value_type back_item;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliği üst (en yüksek öncelik) öğe boş olmalıdır denetlenen dizinin erişir. Okumak veya mevcut bildiğinizde, en yüksek öncelikli öğenin yazmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_top_item.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top_item = {0}", c1.top_item);   
  
// alter last item and reinspect   
    c1.top_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 c a b  
top_item = c  
 x a b  
```  

## <a name="value_comp"></a> priority_queue::value_comp (STL/CLR)
İki öğe sipariş temsilcisi kopyalar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
value_compare^ value_comp();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi denetlenen diziyi sıralamak için kullanılan sıralama temsilci döndürür. İki değeri karşılaştırmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_value_comp.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        vcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        vcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        vcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    vcomp = c2.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        vcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        vcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        vcomp(L'b', L'a'));   
    return (0);   
    }  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  

## <a name="value_compare"></a> priority_queue::value_compare (STL/CLR)
İki değer sıralama temsilcisi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
binary_delegate<value_type, value_type, int> value_compare;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türü, saniyenin ilk bağımsız değişken sıralı olup olmadığını belirleyen bir temsilci eşanlamlıdır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_value_compare.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        vcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        vcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        vcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    vcomp = c2.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        vcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        vcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        vcomp(L'b', L'a'));   
    return (0);   
    }  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  

## <a name="value_type"></a> priority_queue::value_type (STL/CLR)
Öğenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eşanlamlı türüdür *değer*.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_priority_queue_value_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " a b c" using value_type   
    for (; !c1.empty(); c1.pop())   
        {   // store element in value_type object   
        Mypriority_queue::value_type val = c1.top();   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c b a  
```  