---
title: "Allocator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::allocator
- memory/std::allocator::const_pointer
- memory/std::allocator::const_reference
- memory/std::allocator::difference_type
- memory/std::allocator::pointer
- memory/std::allocator::reference
- memory/std::allocator::size_type
- memory/std::allocator::value_type
- memory/std::allocator::address
- memory/std::allocator::allocate
- memory/std::allocator::construct
- memory/std::allocator::deallocate
- memory/std::allocator::destroy
- memory/std::allocator::max_size
- memory/std::allocator::rebind
dev_langs: C++
helpviewer_keywords:
- std::allocator [C++]
- std::allocator [C++], const_pointer
- std::allocator [C++], const_reference
- std::allocator [C++], difference_type
- std::allocator [C++], pointer
- std::allocator [C++], reference
- std::allocator [C++], size_type
- std::allocator [C++], value_type
- std::allocator [C++], address
- std::allocator [C++], allocate
- std::allocator [C++], construct
- std::allocator [C++], deallocate
- std::allocator [C++], destroy
- std::allocator [C++], max_size
- std::allocator [C++], rebind
ms.assetid: 3fd58076-56cc-43bb-ad58-b4b7c9c6b410
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32e63292ffcb02fa41ea5b8d9e95f7b4cd3f776b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="allocator-class"></a>allocator Sınıfı
Depolama ayırma ve nesne türü diziler için boşaltma yöneten bir nesne şablonu sınıf tanımlar **türü**. Sınıfın bir nesnesi **ayırıcısı** oluşturucuları C++ Standart Kitaplığı'nda birkaç kapsayıcı şablon sınıfları için belirtilen varsayılan ayırıcısı nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Type>  
class allocator  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Türü*  
 İçin depolama birimi olan nesnenin türü ayrıldı veya serbest bırakıldı.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak bir şablon parametresini tüm C++ Standart Kitaplığı kapsayıcıları sahip **ayırıcısı**. Özel bir ayırıcı ile bir kapsayıcı oluşturma ayırma ve bu kapsayıcının öğeleri boşaltma üzerinde denetim sağlar.  
  
 Örneğin, bir ayırıcı nesne depolama özel bir yığın veya paylaşılan bellek ayırabilir veya küçük veya büyük nesne boyutları için optimize. Bu ayrıca, bu kaynakları, tür tanımları öğeleri paylaşılan bellek yönetmek ya da otomatik çöp toplama gerçekleştirmek özel erişimcisi nesneleri erişilebilir olduğunu belirtebilir. Bu nedenle, ayırıcısı nesneyi kullanarak depolama ayıran bir sınıf işaretçi bildirmek için bu türü kullanın ve bu nesneler, C++ Standart Kitaplığı kapsayıcılarında gibi başvuru gerekir.  
  
 **(C_ ++ 98/03 yalnızca)** Sağlamak zorunda ayırıcısı sınıfından türetilen, bir [rebind](#rebind) yapısı, olan `_Other` typedef yeni türetilmiş sınıf başvuruyor.  
  
 Bu nedenle, bir ayırıcı aşağıdaki türlerini tanımlar:  
  
- [İşaretçi](#pointer) gösteren bir işaretçi gibi davranır **türü**.  
  
- [const_pointer](#const_pointer) const işaretçi gibi davranır **türü**.  
  
- [başvuru](#reference) başvuru gibi davranır **türü**.  
  
- [const_reference](#const_reference) const başvuru gibi davranır **türü**.  
  
 Bunlar **türü**s işaretçiler ve başvurular için ayrılmış öğeleri almalıdır biçiminde belirtin. ( [allocator::pointer](#pointer) mutlaka aynı değil **türü** \* tüm ayırıcı nesneleri için bile, bu belirgin tanıma sahip sınıfı için **ayırıcısı**.)  
  
 **C ++ 11 ve sonraki sürümleri:** , ayırıcı taşıma işlemleri etkinleştirmek için en az ayırıcısı arabirimini kullanın ve kopya Oluşturucu uygulamak, == ve! = işleç, ayırma ve serbest bırakma. Daha fazla bilgi ve bir örnek için bkz: [Allocators](../standard-library/allocators.md)  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[ayırıcısı](#allocator)|Oluşturucular oluşturmak için kullanılan `allocator` nesneleri.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[const_pointer](#const_pointer)|Ayırıcı tarafından yönetilen nesne türü için sabit bir işaretçi sağlayan türü.|  
|[const_reference](#const_reference)|Ayırıcı tarafından yönetilen nesne türü için sabit bir başvuru sağlar türü.|  
|[difference_type](#difference_type)|Ayırıcı tarafından yönetilen nesne türü işaretçileri değerler arasındaki farkın gösterebilir imzalı tam sayı türü.|  
|[İşaretçi](#pointer)|Ayırıcı tarafından yönetilen nesne türü için bir işaretçi sağlayan türü.|  
|[başvuru](#reference)|Ayırıcı tarafından yönetilen nesne türü için bir başvuru sağlar türü.|  
|[size_type](#size_type)|Herhangi bir uzunluğunu temsil edebilen imzasız tamsayı türü sıra şablon sınıfın bir nesnesi `allocator` ayırabilirsiniz.|  
|[value_type](#value_type)|Ayırıcı tarafından yönetilen türü.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Adres](#address)|Değeri belirtilen bir nesne adresini bulur.|  
|[allocate](#allocate)|Bir en az bazı belirtilen sayıda öğeyi depolamak için büyük bellek bloğu ayırır.|  
|[Yapı](#construct)|Belirli bir nesne belirli bir değerle başlatılır belirtilen adresteki türünü oluşturur.|  
|[serbest bırakma](#deallocate)|Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.|  
|[yok](#destroy)|Nesneleri yok Edicisi bellek ayırmayı kaldırma olmadan nesne saklandığı çağırır.|  
|[max_size](#max_size)|Türündeki öğe sayısını döndürür `Type` , ayrılan sınıfın bir nesnesi tarafından `allocator` boş bellek kullanılmadan önce.|  
|[yeniden bağlayın](#rebind)|Başka bir türündeki nesneler için depolama alanı ayırmak bir ayırıcı bir türündeki nesneler için etkinleştirir yapısı.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](#op_eq)|Atar `allocator` başka bir nesneye `allocator` nesnesi.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<bellek >  
  
 **Namespace:** std  
  
##  <a name="address"></a>Allocator::Address  
 Değeri belirtilen bir nesne adresini bulur.  
  
```  
pointer address(reference val) const;
const_pointer address(const_reference val) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `val`  
 Adresini aranır nesnenin const veya nonconst değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const veya nesnesine nonconst işaretçi sırasıyla const veya nonconst değeri, bulundu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri adresini dönmek `val`, işaretçileri almalıdır için form öğeleri ayrılmış.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_address.cpp  
// compile with: /EHsc  
#include <memory>  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 2 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 8;  
   v1Ptr = v1Alloc.address( *find(v1.begin( ), v1.end( ), k) );  
   // v1Ptr = v1Alloc.address( k );  
   cout << "The integer addressed by v1Ptr has a value of: "  
        << "*v1Ptr = " << *v1Ptr << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The integer addressed by v1Ptr has a value of: *v1Ptr = 8.  
```  
  
##  <a name="allocate"></a>Allocator::allocate  
 Bir en az bazı belirtilen sayıda öğeyi depolamak için büyük bellek bloğu ayırır.  
  
```  
pointer allocate(size_type count, const void* _Hint);
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 İçin yeterli depolama alanı ayrılacak olan öğe sayısı.  
  
 *_Hint*  
 Ayırıcı nesne yardımcı olabilir const bir işaretçi önce isteği ayrılmış bir nesne adresini bularak depolama talebi karşılamak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi ayrılmış nesneye veya bellek ayrılmamış yoksa null.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini depolama türündeki sayısı öğeler için bir dizi ayırır **türü**, yeni arama işleci ( `count`). Bu ayrılmış nesnesine bir işaretçi döndürür. İpucu bağımsız değişken başvuru yere göre artırma içinde bazı allocators yardımcı olur; Geçerli bir seçim bir nesne daha önce aynı ayırıcısı nesnesi tarafından ayrılmış ve henüz serbest adresidir. Hiçbir ipucu temin etmek için bir null işaretçinin bağımsız değişkeni kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_allocate.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<int> v1Alloc;    
   allocator<int>::pointer v1aPtr;    
   v1aPtr = v1Alloc.allocate ( 10 );  
  
   int i;  
   for ( i = 0 ; i < 10 ; i++ )  
   {  
      v1aPtr[ i ] = i;  
   }  
  
   for ( i = 0 ; i < 10 ; i++ )  
   {  
      cout << v1aPtr[ i ] << " ";  
   }  
   cout << endl;    
   v1Alloc.deallocate( v1aPtr, 10 );  
}  
```  
  
```Output  
0 1 2 3 4 5 6 7 8 9   
```  
  
##  <a name="allocator"></a>Allocator::Allocator  
 Ayırıcı nesneleri oluşturmak için kullanılan Oluşturucu.  
  
```  
allocator();
allocator(const allocator<Type>& right);
template <class Other>  
allocator(const allocator<Other>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Kopyalanacak ayırıcısı nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucusu hiçbir şey yapmaz. Genel olarak, ancak ayırıcısı nesneyi başka bir ayırıcı nesnesinden oluşturulan ona eşit karşılaştırın ve nesne ayrılması intermixing ve arasında iki ayırıcı nesneleri serbest bırakma izin verecek.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_allocator.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int {  
public:  
   Int( int i )   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
int main( )   
{  
   allocator<double> Alloc;  
   vector <Int>:: allocator_type v1Alloc;  
  
   allocator<double> cAlloc(Alloc);   
   allocator<Int> cv1Alloc(v1Alloc);  
  
   if ( cv1Alloc == v1Alloc )  
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."  
           << endl;  
  
   if ( cAlloc == Alloc )  
      cout << "The allocator objects cAlloc & Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cAlloc & Alloc are not equal."  
           << endl;  
}  
```  
  
```Output  
The allocator objects cv1Alloc & v1Alloc are equal.  
The allocator objects cAlloc & Alloc are equal.  
```  
  
##  <a name="const_pointer"></a>Allocator::const_pointer  
 Ayırıcı tarafından yönetilen nesne türü için sabit bir işaretçi sağlayan türü.  
  
```  
typedef const value_type *const_pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretçi türünün bir nesneyi tanımlayan **ptr** , belirleyebilirler, ifade yoluyla  **\*ptr**, bir nesne şablonu sınıfı ayırıcısı ayırabilirsiniz herhangi bir const nesnesi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_const_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i * 2 );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 10;  
   v1Ptr = v1Alloc.address( k );  
  
   cout << "The integer's address found has a value of: "  
        << *v1Ptr << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The integer's address found has a value of: 10.  
```  
  
##  <a name="const_reference"></a>Allocator::const_reference  
 Ayırıcı tarafından yönetilen nesne türü için sabit bir başvuru sağlar türü.  
  
```  
typedef const value_type& const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başvuru türü bir nesne şablonu sınıfı ayırıcısı ayırabilirsiniz herhangi bir const nesnesi belirleyebileceğiniz bir nesne açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_const_ref.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::const_reference vcref =*vfIter;  
   cout << "The value of the element referred to by vref is: "  
        << vcref << ",\n the first element in the vector." << endl;  
  
   // const references can have their elements modified,  
   // so the following would generate an error:  
   // vcref = 150;  
   // but the value of the first element could be modified through  
   // its nonconst iterator and the const reference would remain valid  
 *vfIter = 175;  
   cout << "The value of the element referred to by vcref,"  
        <<"\n after nofication through its nonconst iterator, is: "  
        << vcref << "." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element referred to by vref is: 100,  
 the first element in the vector.  
The value of the element referred to by vcref,  
 after nofication through its nonconst iterator, is: 175.  
```  
  
##  <a name="construct"></a>Allocator::Construct  
 Belirli bir nesne belirli bir değerle başlatılır belirtilen adresteki türünü oluşturur.  
  
```  
void construct(pointer ptr, const Type& val);
void construct(pointer ptr, Type&& val);
template <class _Other>  
void construct(pointer ptr, _Other&&...   val);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptr`  
 Nesne oluşturulması bulunduğu konuma bir işaretçi.  
  
 `val`  
 Yapılandırılan bir nesne başlatılması olduğu değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi eşdeğerdir **yeni** (( `void` \*) `ptr` ) **türü** ( `val` ).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_construct.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 3 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::pointer v1PtrA;  
   int kA = 6, kB = 7;  
   v1PtrA = v1Alloc.address( *find( v1.begin( ), v1.end( ), kA ) );  
   v1Alloc.destroy ( v1PtrA );  
   v1Alloc.construct ( v1PtrA , kB );  
  
   cout << "The modified vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 3 6 9 12 15 18 21 ).  
The modified vector v1 is:  
 ( 3 7 9 12 15 18 21 ).  
```  
  
##  <a name="deallocate"></a>Allocator::deallocate  
 Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.  
  
```  
void deallocate(pointer ptr, size_type count);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptr`  
 Depolama biriminden bırakılmasına ilk nesne için bir işaretçi.  
  
 `count`  
 Depolama biriminden bırakılmasına nesnelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Depolama dizisi sayısı nesne türü için üye fonksiyonu boşaltır **türü** başlangıç `ptr`, çağırarak `operator delete(ptr)`. İşaretçinin `ptr` daha önce bir çağrı tarafından verilinceye gerekir [tahsis](#allocate) eşit karşılaştırır ayırıcısı nesnenin  **\*bu**, bir dizi nesnesi aynı boyutta ayırma ve yazın. `deallocate`hiçbir zaman bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
  Üye işlevini kullanarak bir örnek için bkz: [allocator::allocate](#allocate).  
  
##  <a name="destroy"></a>Allocator::Destroy  
 Nesneleri yok Edicisi bellek ayırmayı kaldırma olmadan nesne saklandığı çağırır.  
  
```  
void destroy(pointer ptr);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptr`  
 Bir işaretçi yok edilmesi nesnesine adresini belirleme.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu tarafından belirlenen nesnesini yok eder `ptr`, yıkıcı çağırarak `ptr->` **türü**::**~ türü**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_destroy.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 2 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::pointer v1PtrA;  
   int kA = 12, kB = -99;  
   v1PtrA = v1Alloc.address( *find(v1.begin( ), v1.end( ), kA) );  
   v1Alloc.destroy ( v1PtrA );  
   v1Alloc.construct ( v1PtrA , kB );  
  
   cout << "The modified vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The modified vector v1 is:  
 ( 2 4 6 8 10 -99 14 ).  
```  
  
##  <a name="difference_type"></a>Allocator::difference_type  
 Ayırıcı tarafından yönetilen nesne türü işaretçileri değerler arasındaki farkın gösterebilir imzalı tam sayı türü.  
  
```  
typedef ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İmzalı tamsayı türü herhangi bir nesne şablonu sınıfı ayırıcısı ayırabileceğiniz sırayla iki öğe adreslerini arasındaki farkı temsil eden bir nesne açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_diff_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 0 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i * 2 );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1PtrA, v1PtrB;  
   const int kA = 4, kB =12;  
   v1PtrA = v1Alloc.address( kA );  
   v1PtrB = v1Alloc.address( kB );  
   allocator<int>::difference_type v1diff = *v1PtrB - *v1PtrA;  
  
   cout << "Pointer v1PtrA addresses " << *v1PtrA << "." << endl;  
   cout << "Pointer v1PtrB addresses " << *v1PtrB <<  "." << endl;  
   cout << "The difference between the integer's addresses is: "  
        << v1diff << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 0 2 4 6 8 10 12 14 ).  
Pointer v1PtrA addresses 4.  
Pointer v1PtrB addresses 12.  
The difference between the integer's addresses is: 8.  
```  
  
##  <a name="max_size"></a>Allocator::max_size  
 Türündeki öğe sayısını döndürür **türü** , ayrılan bir sınıf ayırıcısı nesnesiyle boş bellek kullanılmadan önce.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılamadı öğe sayısı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_max_size.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   vector <double> v2;  
   vector <double> ::iterator v2Iter;  
   vector <double> :: allocator_type v2Alloc;  
   allocator<int>::size_type v1size;  
   v1size = v1Alloc.max_size( );  
  
   cout << "The number of integers that can be allocated before\n"  
        << " the free memory in the vector v1 is used up is: "  
        << v1size << "." << endl;  
  
   int ii;  
   for ( ii = 1 ; ii <= 7 ; ii++ )  
   {  
      v2.push_back( ii * 10.0 );  
   }  
  
   cout << "The original vector v2 is:\n ( " ;  
   for ( v2Iter = v2.begin( ) ; v2Iter != v2.end( ) ; v2Iter++ )  
      cout << *v2Iter << " ";  
   cout << ")." << endl;  
   allocator<double>::size_type v2size;  
   v2size = v2Alloc.max_size( );  
  
   cout << "The number of doubles that can be allocated before\n"  
        << " the free memory in the vector v2 is used up is: "  
        << v2size << "." << endl;  
}  
```  
  
##  <a name="op_eq"></a>Allocator::operator =  
 Bir ayırıcı nesne başka bir ayırıcı nesneye atar.  
  
```  
template <class Other>  
allocator<Type>& operator=(const allocator<Other>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Başka bir tür nesneyi atanacak ayırıcısı nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayırıcı nesneye bir başvurusu  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon atama işleci hiçbir şey yapmaz. Genel olarak, ancak ayırıcısı nesneyi başka bir ayırıcı nesnesine atanmış ona eşit karşılaştırın ve nesne ayrılması intermixing ve arasında iki ayırıcı nesneleri serbest bırakma izin verecek.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_op_assign.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int {  
public:  
   Int(int i)   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( ) {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
int main( )   
{  
   allocator<Int> Alloc;  
   allocator<Int> cAlloc ;  
   cAlloc = Alloc;      
}  
```  
  
##  <a name="pointer"></a>Allocator::pointer  
 Ayırıcı tarafından yönetilen nesne türü için bir işaretçi sağlayan türü.  
  
```  
typedef value_type *pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretçi türünün bir nesneyi tanımlayan **ptr** , belirleyebilirler, ifade yoluyla  **\*ptr**, bir nesne şablonu sınıfı ayırıcısı ayırabilirsiniz herhangi bir nesne.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 3 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 12;  
   v1Ptr = v1Alloc.address( k );  
  
   cout << "The integer addressed by v1Ptr has a value of: "  
        << "*v1Ptr = " << *v1Ptr << "." << endl;     
}  
```  
  
```Output  
The original vector v1 is:  
 ( 3 6 9 12 15 18 21 ).  
The integer addressed by v1Ptr has a value of: *v1Ptr = 12.  
```  
  
##  <a name="rebind"></a>Allocator::rebind  
 Başka bir türündeki nesneler için depolama alanı ayırmak bir ayırıcı bir türündeki nesneler için etkinleştirir yapısı.  
```  
struct rebind {    typedef allocator<_Other> other ;    };  
```  
### <a name="parameters"></a>Parametreler  
 *diğer*  
 Bellek kendisi için ayrılan öğe türü.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapı, uygulanan kapsayıcı öğesi türünden farklı türü için bellek ayırma için yararlıdır.  
  
 Üye Şablon sınıfı diğer türü tanımlar. Tek amacı tür adı sağlamaktır **ayırıcısı**\<_ **diğer**>, tür adı verilen **ayırıcısı** \< **türü** >.  
  
 Örneğin, bir ayırıcı nesne verilen **al** türü **A**, bir nesne türü ayırabilirsiniz **_Other** ifade ile:  
  
```  
A::rebind<Other>::other(al).allocate(1, (Other *)0)  
```  
  
 Veya türü yazarak işaretçi türü adı verebilirsiniz:  
  
```  
A::rebind<Other>::other::pointer  
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_rebind.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
typedef vector<int>::allocator_type IntAlloc;  
int main( )   
{  
   IntAlloc v1Iter;  
   vector<int> v1;  
  
   IntAlloc::rebind<char>::other::pointer pszC =  
      IntAlloc::rebind<char>::other(v1.get_allocator()).allocate(1, (void *)0);  
  
   int * pInt = v1Iter.allocate(10);  
}  
```  
  
##  <a name="reference"></a>Allocator::Reference  
 Ayırıcı tarafından yönetilen nesne türü için bir başvuru sağlar türü.  
  
```  
typedef value_type& reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başvuru türü bir nesne şablonu sınıfı ayırıcısı ayırabilirsiniz herhangi bir nesne belirleyebileceğiniz bir nesne açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_reference.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::reference vref =*vfIter;  
   cout << "The value of the element referred to by vref is: "  
        << vref << ",\n the first element in the vector." << endl;  
  
   // nonconst references can have their elements modified  
   vref = 150;  
   cout << "The element referred to by vref after being modified is: "  
        << vref << "." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element referred to by vref is: 100,  
 the first element in the vector.  
The element referred to by vref after being modified is: 150.  
```  
  
##  <a name="size_type"></a>Allocator::size_type  
 Şablon sınıfı ayırıcısı nesnenin ayırabilirsiniz sırası uzunluğu temsil eden bir imzasız tam sayı türü.  
  
```  
typedef size_t size_type;  
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_size_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )  
{  
   vector <double> v;  
   vector <double> ::iterator vIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   allocator<double>::size_type vsize;  
   vsize = vAlloc.max_size( );  
  
   cout << "The number of doubles that can be allocated before\n"  
        << " the free memory in the vector v is used up is: "  
        << vsize << "." << endl;  
}  
```  
  
##  <a name="value_type"></a>Allocator::value_type  
 Ayırıcı tarafından yönetilen türü.  
  
```  
typedef Type value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **türü**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// allocator_value_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::value_type vecVal = 150.0;  
 *vfIter = vecVal;  
   cout << "The value of the element addressed by vfIter is: "  
        << *vfIter << ",\n the first element in the vector." << endl;  
  
   cout << "The modified vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element addressed by vfIter is: 150,  
 the first element in the vector.  
The modified vector v is:  
 ( 150 200 300 400 500 600 700 ).  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

