---
title: "raw_storage_iterator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::raw_storage_iterator
- memory/std::raw_storage_iterator::element_type
- memory/std::raw_storage_iterator::iter_type
dev_langs: C++
helpviewer_keywords:
- std::raw_storage_iterator [C++]
- std::raw_storage_iterator [C++], element_type
- std::raw_storage_iterator [C++], iter_type
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fd68bfc788231ddc954b1f6e8a70d63dbcf02592
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="rawstorageiterator-class"></a>raw_storage_iterator Sınıfı
Algoritmaların başlatılmamış belleğe sonuçları depolamasını sağlamak üzere oluşturulmuş bağdaştırıcı sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class OutputIterator, class Type>  
class raw_storage_iterator
```  
  
#### <a name="parameters"></a>Parametreler  
 `OutputIterator`  
 Depolanmakta nesnesi için çıktı yineleyici belirtir.  
  
 *Türü*  
 Depolama ayrılan nesnenin türü.  
  
## <a name="remarks"></a>Açıklamalar  
 Türündeki nesneleri oluşturan bir çıktı yineleyici sınıf tanımlar **türü** ürettiği sıralı. Sınıfın bir nesnesi `raw_storage_iterator` \< **ForwardIterator**, **türü**> depolama sınıfın iletme yineleyici nesnesi erişen **ForwardIterator**, nesneyi oluşturmak zaman belirtin. Bir nesne için ilk sınıfının **ForwardIterator**, ifade  **& \*ilk** unconstructed depolama sonraki nesne için atamanız gerekir (tür **türü** ) oluşturulan sıralı.  
  
 Bellek ayırma ve nesne oluşturması ayırmak gerekli olduğunda bu bağdaştırıcı sınıf kullanılır. `raw_storage_iterator` Kullanılarak ayrılmış bellek gibi başlatılmamış depolama alanına nesneleri kopyalamak için kullanılan `malloc` işlevi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[raw_storage_iterator](#raw_storage_iterator)|Belirtilen temel alınan bir çıkış yineleyici ile ham depolama yineleyici oluşturur.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[ELEMENT_TYPE](#element_type)|Ham depolama yineleyici olarak bir öğeyi açıklayan türü depolanan sağlar.|  
|[iter_type](#iter_type)|Ham depolama yineleyici altını çizen yineleyici açıklayan türü sağlar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç *](#op_star)|Çıktı yineleyici ifade uygulamak için kullanılan bilgileri başvuru kaldırma işleci * `ii`  =  `x`.|  
|[işleç =](#op_eq)|Ham depolama yineleyici ifade uygulamak için kullanılan bir atama işleci * `i`  =  `x` bellekte depolamak için.|  
|[operator ++](#op_add_add)|Ham depolama yineleyiciler preincrement ve postincrement işleçler.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<bellek >  
  
 **Namespace:** std  
  
##  <a name="element_type"></a>raw_storage_iterator::ELEMENT_TYPE  
 Ham depolama yineleyici olarak bir öğeyi açıklayan türü depolanan sağlar.  
  
```
typedef Type element_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Raw_storage_iterator sınıfı şablon parametresi için bir eş anlamlı türüdür **türü**.  
  
##  <a name="iter_type"></a>raw_storage_iterator::iter_type  
 Ham depolama yineleyici altını çizen yineleyici açıklayan türü sağlar.  
  
```
typedef ForwardIterator iter_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **ForwardIterator**.  
  
##  <a name="op_star"></a>raw_storage_iterator::operator *  
 Ham depolama yineleyici ifade uygulamak için kullanılan bilgileri başvuru kaldırma işleci \* *II* = *x*.  
  
```
raw_storage_iterator<ForwardIterator, Type>& operator*();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ham depolama yineleyici referansı  
  
### <a name="remarks"></a>Açıklamalar  
 Gereksinimleri bir **ForwardIterator** ham olan depolama yineleyici gerekir karşılamak gerektiren yalnızca ifade \* *II* = *t* olabilir Geçerli ve onu bir şey hakkında yazıp yazmadığını **işleci** veya `operator=` kendi başlarına. Bu uygulamada üye işleçleri döndürür  **\*bu**, böylece [işleç =](#op_eq)( **constType**&) gerçek deponun bir ifadede gerçekleştirebilirsiniz gibi \* *ptr* = `val`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// raw_storage_iterator_op_deref.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iterator>  
#include <memory>  
#include <list>  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
   {  
      cout << "Constructing " << i << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
  
   Int &operator=(int i)   
   {  
      if (!bIsConstructed)  
         cout << "Not constructed.\n";  
      cout << "Copying " << i << endl;    
      x = i;   
      return *this;  
   };  
  
   int x;  
  
private:  
   bool bIsConstructed;  
};  
  
int main( void)   
{  
   Int *pInt = ( Int* ) malloc( sizeof( Int ) );  
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;  
 *pInt = 5;  
   raw_storage_iterator< Int*, Int > it( pInt );  
 *it = 5;  
}  
\* Output:   
Not constructed.  
Copying 5  
Constructing 5  
*\  
```  
  
##  <a name="op_eq"></a>raw_storage_iterator::operator =  
 Ham depolama yineleyici ifade uygulamak için kullanılan atama işleci \* *ı* = *x* bellekte depolamak için.  
  
```
raw_storage_iterator<ForwardIterator, Type>& operator=(
    const Type& val);
```  
  
### <a name="parameters"></a>Parametreler  
 `val`  
 Nesne türü değeri **türü** belleğe eklenecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleç ekler `val` , belleğe ve ham depolama yineleyici bir başvuru döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Gereksinimleri bir **ForwardIterator** ham depolama yineleyici getirmelidir durumu gerektirecek yalnızca ifade \* *II* = *t* olabilir Geçerli ve onu bir şey hakkında yazıp yazmadığını **işleci** veya `operator=` kendi başlarına. Bu üye işleçleri dönmek  **\*bu**.  
  
 Atama işleci saklı yineleyici değerin ilk olarak, yerleştirme yeni ifadesinin hesaplanmasıyla kullanılarak çıkış sırası sonraki nesne yapıları **yeni** (( `void` \*) &\* **ilk**) **türü**( `val`).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// raw_storage_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iterator>  
#include <memory>  
#include <list>  
using namespace std;  
  
class Int   
{  
public:  
   Int( int i )   
   {  
      cout << "Constructing " << i << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   Int &operator=( int i )   
   {  
      if ( !bIsConstructed )  
         cout << "Not constructed.\n";  
      cout << "Copying " << i << endl; x = i;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
int main( void )  
{  
   Int *pInt = ( Int* )malloc( sizeof( Int ) );  
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;  
  
 *pInt = 5;  
  
   raw_storage_iterator<Int*, Int> it( pInt );  
 *it = 5;  
}  
\* Output:   
Not constructed.  
Copying 5  
Constructing 5  
*\  
```  
  
##  <a name="op_add_add"></a>raw_storage_iterator::operator ++  
 Ham depolama yineleyiciler preincrement ve postincrement işleçler.  
  
```
raw_storage_iterator<ForwardIterator, Type>& operator++();

raw_storage_iterator<ForwardIterator, Type> operator++(int);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ham depolama yineleyici veya ham depolama yineleyici başvurusu.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk işleci sonunda ayıklayın ve türünde bir nesne depolamak girişiminde **CharType** ilişkili giriş akışından. İkinci işleci nesne bir kopyasını oluşturur, nesne artırır ve kopyayı döndürür.  
  
 İlk preincrement işleci depolanan çıktı yineleyici nesne artırır ve ardından döndürür  **\*bu**.  
  
 İkinci postincrement işleci bir kopyasını oluşturur  **\*bu**depolanan çıktı yineleyici nesne artırır ve kopyayı döndürür.  
  
 Oluşturucu depoları **ilk** çıktı yineleyici nesne.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// raw_storage_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iterator>  
#include <memory>  
#include <list>  
using namespace std;  
  
int main( void )  
{  
   int *pInt = new int[5];  
   std::raw_storage_iterator<int*,int> it( pInt );  
   for ( int i = 0; i < 5; i++, it++ ) {  
 *it = 2 * i;  
};  
  
   for ( int i = 0; i < 5; i++ ) cout << "array " << i << " = " << pInt[i] << endl;;  
  
   delete[] pInt;  
}  
\* Output:   
array 0 = 0  
array 1 = 2  
array 2 = 4  
array 3 = 6  
array 4 = 8  
*\  
```  
  
##  <a name="raw_storage_iterator"></a>raw_storage_iterator::raw_storage_iterator  
 Belirtilen temel alınan bir çıkış yineleyici ile ham depolama yineleyici oluşturur.  
  
```
explicit raw_storage_iterator(ForwardIterator first);
```  
  
### <a name="parameters"></a>Parametreler  
 `first`  
 Temelini oluşturan için ileriye doğru yineleyici `raw_storage_iterator` yapılandırılan bir nesne.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// raw_storage_iterator_ctor.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
#include <iterator>  
#include <memory>  
#include <list>  
using namespace std;  
  
class Int  
{  
public:  
   Int(int i)  
   {  
      cout << "Constructing " << i << endl;  
      x = i;  
      bIsConstructed = true;  
   };  
   Int &operator=( int i )  
   {  
      if (!bIsConstructed)  
         cout << "Error! I'm not constructed!\n";  
      cout << "Copying " << i << endl;  x = i; return *this;  
   };  
   int x;  
   bool bIsConstructed;  
};  
  
int main( void )  
{  
   std::list<int> l;  
   l.push_back( 1 );  
   l.push_back( 2 );  
   l.push_back( 3 );  
   l.push_back( 4 );  
  
   Int *pInt = (Int*)malloc(sizeof(Int)*l.size( ));  
   memset (pInt, 0, sizeof(Int)*l.size( ));  
   // Hack: make sure bIsConstructed is false  
  
   std::copy( l.begin( ), l.end( ), pInt );  // C4996  
   for (unsigned int i = 0; i < l.size( ); i++)  
      cout << "array " << i << " = " << pInt[i].x << endl;;  
  
   memset (pInt, 0, sizeof(Int)*l.size( ));  
   // hack: make sure bIsConstructed is false  
  
   std::copy( l.begin( ), l.end( ),  
      std::raw_storage_iterator<Int*,Int>(pInt));  // C4996  
   for (unsigned int i = 0; i < l.size( ); i++ )  
      cout << "array " << i << " = " << pInt[i].x << endl;  
  
   free(pInt);  
}  
\* Output:   
Error! I'm not constructed!  
Copying 1  
Error! I'm not constructed!  
Copying 2  
Error! I'm not constructed!  
Copying 3  
Error! I'm not constructed!  
Copying 4  
array 0 = 1  
array 1 = 2  
array 2 = 3  
array 3 = 4  
Constructing 1  
Constructing 2  
Constructing 3  
Constructing 4  
array 0 = 1  
array 1 = 2  
array 2 = 3  
array 3 = 4  
*\  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



