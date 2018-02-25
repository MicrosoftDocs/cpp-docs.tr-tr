---
title: "fpos sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- iosfwd/std::fpos
- iosfwd/std::fpos::seekpos
- iosfwd/std::fpos::state
- iosfwd/std::fpos::operator streamoff
dev_langs:
- C++
helpviewer_keywords:
- std::fpos [C++]
- std::fpos [C++], seekpos
- std::fpos [C++], state
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d65ede65d1cd1b0d8cadb39ec18af42a007c023c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="fpos-class"></a>fpos Sınıfı
Şablon sınıfı bir rastgele dosya konumu göstergesi akış içinde geri yüklemek için gerekli tüm bilgileri depolayan bir nesne tanımlar. Bir nesne sınıfı fpos\< **St**> en az iki üye nesneleri etkili bir şekilde depolar:  
  
-   Türünde bir bayt uzaklığı [streamoff](../standard-library/ios-typedefs.md#streamoff).  
  
-   Bir dönüştürme, bir nesne sınıfı basic_filebuf tarafından kullanılmak üzere türünün durumunu **St**, genellikle `mbstate_t`.  
  
 Sınıfın bir nesnesi tarafından kullanılmak üzere bir rastgele dosya konumu depolayabilir [basic_filebuf](../standard-library/basic-filebuf-class.md), türü `fpos_t`. Ancak, sınırlı dosya boyutuna sahip bir ortam için `streamoff` ve `fpos_t` bazen birbirinin yerine kullanılabilir. Bir durum bağımlı kodlama sahip hiçbir akışlarla ortamı için `mbstate_t` gerçekte kullanılmayan olabilir. Bu nedenle, depolanan üye nesne sayısı değişebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Statetype>  
class fpos  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Statetype*  
 Durum bilgisi.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[fpos](#fpos)|Bir akış bir konuma (uzaklık) hakkında bilgi içeren bir nesne oluşturun.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[seekpos](#seekpos)|C++ Standart Kitaplığı tarafından yalnızca dahili olarak kullanılır. Bu yöntem kodunuzdan çağırmayın.|  
|[Durumu](#state)|Dönüştürme durumu döndürür veya ayarlar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator!=](#op_neq)|Eşitsizlik için testleri dosya konumunu göstergeleri.|  
|[operator+](#op_add)|Bir dosya konumu göstergesi artırır.|  
|[operator+=](#op_add_eq)|Bir dosya konumu göstergesi artırır.|  
|[operator-](#operator-)|Azaltır dosya konumu göstergesi.|  
|[operator-=](#operator-_eq)|Azaltır dosya konumu göstergesi.|  
|[operator==](#op_eq_eq)|Eşitlik için test dosya konumunu göstergeleri.|  
|[işleç streamoff](#op_streamoff)|Tür atamaları nesne `fpos` nesne türü için `streamoff`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<ios >  
  
 **Namespace:** std  
  
##  <a name="fpos"></a>  fpos::fpos  
 Bir akış bir konuma (uzaklık) hakkında bilgi içeren bir nesne oluşturun.  
  
```  
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Akışa uzaklığı.  
  
 `_State`  
 Başlangıç durumunu `fpos` nesnesi.  
  
 *_Filepos*  
 Akışa uzaklığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Uzaklık ilk Oluşturucusu depolar `_Off`, göreli başına dosyasının ve ilk dönüştürme durumda (, önemli değilse). Varsa `_Off` -1 ' dir sonuç nesnesi geçersiz akış konumu temsil eder.  
  
 İkinci oluşturucu sıfır uzunluk ve nesne depolar `_State`.  
  
##  <a name="op_neq"></a>  fpos::operator!=  
 Eşitsizlik için testleri dosya konumunu göstergeleri.  
  
```  
bool operator!=(const fpos<Statetype>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Dosya konumu göstergesi olan karşılaştırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** dosya konumunu göstergeleri aksi eşit olup olmadığını **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `!(*this == right)`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// fpos_op_neq.cpp  
// compile with: /EHsc  
#include <fstream>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   fpos<int> pos1, pos2;  
   ifstream file;  
   char c;  
  
   // Compare two fpos object  
   if ( pos1 != pos2 )  
      cout << "File position pos1 and pos2 are not equal" << endl;  
   else  
      cout << "File position pos1 and pos2 are equal" << endl;  
  
   file.open( "fpos_op_neq.txt" );  
   file.seekg( 0 );   // Goes to a zero-based position in the file  
   pos1 = file.tellg( );  
   file.get( c);  
   cout << c << endl;  
  
   // Increment pos1  
   pos1 += 1;  
   file.get( c );  
   cout << c << endl;  
  
   pos1 = file.tellg( ) - fpos<int>( 2);  
   file.seekg( pos1 );  
   file.get( c );  
   cout << c << endl;  
  
   // Increment pos1  
   pos1 = pos1 + fpos<int>( 1 );  
   file.get(c);  
   cout << c << endl;  
  
   pos1 -= fpos<int>( 2 );  
   file.seekg( pos1 );  
   file.get( c );  
   cout << c << endl;  
  
   file.close( );  
}  
```  
  
##  <a name="op_add"></a>  fpos::operator+  
 Bir dosya konumu göstergesi artırır.  
  
```  
fpos<Statetype> operator+(streamoff _Off) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Dosya konumu göstergesi artırmak istediğiniz uzaklığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosyanın konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür **fpos (\*bu) +=** `_Off`.  
  
### <a name="example"></a>Örnek  
  Bkz: [işleç! =](#op_neq) kullanmanın bir örneği için `operator+`.  
  
##  <a name="op_add_eq"></a>  fpos::operator+=  
 Bir dosya konumu göstergesi artırır.  
  
```  
fpos<Statetype>& operator+=(streamoff _Off);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Dosya konumu göstergesi artırmak istediğiniz uzaklığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosyanın konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi ekler `_Off` saklı uzaklık üye nesnesi ve ardından döndürür  **\*bu**. Bir dosyanın içinde konumlandırma için sonucu genellikle yalnızca ikili için geçerli bir durum bağımlı kodlama yok akışları.  
  
### <a name="example"></a>Örnek  
  Bkz: [işleç! =](#op_neq) kullanmanın bir örneği için `operator+=`.  
  
##  <a name="fpos__operator-"></a>  fpos::operator-  
 Azaltır dosya konumu göstergesi.  
  
```  
streamoff operator-(const fpos<Statetype>& right) const;
 
fpos<Statetype> operator-(streamoff _Off) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Dosya konumu.  
  
 `_Off`  
 Akış uzaklığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işlevinin döndürdüğü `(streamoff)*this - (streamoff) right`. İkinci üye işlevinin döndürdüğü `fpos(*this) -= _Off`.  
  
### <a name="example"></a>Örnek  
  Bkz: [işleç! =](#op_neq) kullanmanın bir örneği için `operator-`.  
  
##  <a name="fpos__operator-_eq"></a>  fpos::operator-=  
 Azaltır dosya konumu göstergesi.  
  
```  
fpos<Statetype>& operator-=(streamoff _Off);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Akış uzaklığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevi döndürür `fpos(*this) -= _Off`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dosyanın içinde konumlandırma için sonucu genellikle yalnızca ikili için geçerli bir durum bağımlı kodlama yok akışları.  
  
### <a name="example"></a>Örnek  
  Bkz: [işleç! =](#op_neq) kullanmanın bir örneği için `operator-=`.  
  
##  <a name="op_eq_eq"></a>  fpos::operator==  
 Eşitlik için test dosya konumunu göstergeleri.  
  
```  
bool operator==(const fpos<Statetype>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Dosya konumu göstergesi olan karşılaştırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** dosya konumu göstergesi olması durumunda tersi **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `(streamoff)*this == (streamoff)right`.  
  
### <a name="example"></a>Örnek  
  Bkz: [işleç! =](#op_neq) kullanmanın bir örneği için `operator+=`.  
  
##  <a name="op_streamoff"></a>  fpos::operator streamoff  
 Türü nesne `fpos` nesne türü için `streamoff`.  
  
```  
operator streamoff() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi saklı uzaklık üye nesne ve parçası olarak depolanan tüm ek uzaklığı döndürür `fpos_t` üye nesne.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// fpos_op_streampos.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   streamoff s;  
   ofstream file( "rdbuf.txt");  
  
   fpos<mbstate_t> f = file.tellp( );  
   // Is equivalent to ..  
   // streampos f = file.tellp( );  
   s = f;  
   cout << s << endl;  
}  
```  
  
```Output  
0  
```  
  
##  <a name="seekpos"></a>  fpos::seekpos  
 Bu yöntem C++ Standart Kitaplığı tarafından yalnızca dahili olarak kullanılır. Bu yöntem kodunuzdan çağırmayın.  
  
```  
fpos_t seekpos() const;
```  
  
##  <a name="state"></a>  fpos::State  
 Dönüştürme durumu döndürür veya ayarlar.  
  
```  
Statetype state() const;

void state(Statetype _State);
```  
  
### <a name="parameters"></a>Parametreler  
 `_State`  
 Yeni dönüştürme durumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüştürme durumu.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye fonksiyonu içinde depolanan değeri döndürür **St** üye nesne. İkinci üye fonksiyonu depoları `_State` içinde **St** üye nesne.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// fpos_state.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main() {  
   using namespace std;  
   streamoff s;  
   ifstream file( "fpos_state.txt" );  
  
   fpos<mbstate_t> f = file.tellg( );  
   char ch;  
   while ( !file.eof( ) )  
      file.get( ch );  
   s = f;  
   cout << f.state( ) << endl;  
   f.state( 9 );  
   cout << f.state( ) << endl;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams Kuralları](../standard-library/iostreams-conventions.md)

