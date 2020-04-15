---
title: fpos Sınıfı
ms.date: 03/27/2019
f1_keywords:
- iosfwd/std::fpos
- iosfwd/std::fpos::seekpos
- iosfwd/std::fpos::state
- iosfwd/std::fpos::operator streamoff
helpviewer_keywords:
- std::fpos [C++]
- std::fpos [C++], seekpos
- std::fpos [C++], state
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
ms.openlocfilehash: 7d60a31e69e8a1ad82086f715cac6dde064d1fac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359195"
---
# <a name="fpos-class"></a>fpos Sınıfı

Sınıf şablonu, herhangi bir akış içinde rasgele bir dosya konumu göstergesi geri yüklemek için gereken tüm bilgileri depolayabilir bir nesne açıklar. Sınıf fpos\< **St**> bir nesne etkili en az iki üye nesneleri depolar:

- Bir bayt ofset, türü [streamoff.](../standard-library/ios-typedefs.md#streamoff)

- Sınıf basic_filebuf bir nesne tarafından kullanılmak üzere bir `St`dönüşüm `mbstate_t`durumu, türü , genellikle .

Ayrıca, sınıf [basic_filebuf](../standard-library/basic-filebuf-class.md)bir nesne tarafından kullanılmak üzere rasgele bir `fpos_t`dosya konumu depolayabilir. Ancak, dosya boyutu sınırlı olan `streamoff` `fpos_t` bir ortam için ve bazen birbirinin yerine kullanılabilir. Devlete bağımlı kodlaması olmayan akışları olmayan bir `mbstate_t` ortam için gerçekte kullanılmamış olabilir. Bu nedenle, depolanan üye nesnelerin sayısı değişebilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Statetype>
class fpos
```

### <a name="parameters"></a>Parametreler

*Statetype*\
Eyalet bilgileri.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[fpos](#fpos)|Akıştaki konum (ofset) hakkında bilgi içeren bir nesne oluşturun.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[seekpos](#seekpos)|Yalnızca C++ Standart Kitaplığı tarafından dahili olarak kullanılır. Bu yöntemi kodunuzdan aramayın.|
|[durum](#state)|Dönüşüm durumunu ayarlar veya döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç!=](#op_neq)|Eşitsizlik için dosya konum göstergelerini sınar.|
|[işleç+](#op_add)|Dosya konumu göstergesini açar.|
|[işleç+=](#op_add_eq)|Dosya konumu göstergesini açar.|
|[işleç-](#operator-)|Dosya konumu göstergesini karara erdirin.|
|[işleç-=](#operator-_eq)|Dosya konumu göstergesini karara erdirin.|
|[işleç==](#op_eq_eq)|Eşitlik için dosya konum göstergelerini sınar.|
|[operatör streamoff](#op_streamoff)|Türünün nesnesine `fpos` türünün `streamoff`nesnesini atar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<ios>

**Ad alanı:** std

## <a name="fposfpos"></a><a name="fpos"></a>fpos::fpos

Akıştaki konum (ofset) hakkında bilgi içeren bir nesne oluşturun.

```cpp
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```

### <a name="parameters"></a>Parametreler

*_off*\
Akışa mahsup.

*_state*\
Nesnenin `fpos` başlangıç durumu.

*_Filepos*\
Akışa mahsup.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, dosyanın başına ve ilk dönüşüm durumuna göre (önemliyse) ofset *_Off*depolar. *_Off* -1 ise, ortaya çıkan nesne geçersiz bir akış konumunu temsil eder.

İkinci oluşturucu sıfır ofset depolar ve nesne *_State.*

## <a name="fposoperator"></a><a name="op_neq"></a>fpos::operatör!=

Eşitsizlik için dosya konum göstergelerini sınar.

```cpp
bool operator!=(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Karşılaştırılabilen dosya konumu göstergesi.

### <a name="return-value"></a>Dönüş Değeri

dosya konumu göstergeleri eşit değilse **doğru,** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Üye işlev `!(*this == right)`döndürür.

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

## <a name="fposoperator"></a><a name="op_add"></a>fpos::operatör+

Dosya konumu göstergesini açar.

```cpp
fpos<Statetype> operator+(streamoff _Off) const;
```

### <a name="parameters"></a>Parametreler

*_off*\
Dosya konumu göstergesini artımlı olarak çıkarmak istediğiniz ofset.

### <a name="return-value"></a>Dönüş Değeri

Dosyadaki konum.

### <a name="remarks"></a>Açıklamalar

Üye işlev **fpos\*(bu) +=** `_Off`döndürür.

### <a name="example"></a>Örnek

Bkz. [işleç!=](#op_neq) kullanma `operator+`örneği için.

## <a name="fposoperator"></a><a name="op_add_eq"></a>fpos::operator+=

Dosya konumu göstergesini açar.

```cpp
fpos<Statetype>& operator+=(streamoff _Off);
```

### <a name="parameters"></a>Parametreler

*_off*\
Dosya konumu göstergesini artımlı olarak çıkarmak istediğiniz ofset.

### <a name="return-value"></a>Dönüş Değeri

Dosyadaki konum.

### <a name="remarks"></a>Açıklamalar

Üye işlev, depolanan ofset üye nesnesine *_Off* ekler ve bunu ** \*** döndürür. Bir dosya içinde konumlandırma için, sonuç genellikle yalnızca duruma bağlı kodlaması olmayan ikili akışlar için geçerlidir.

### <a name="example"></a>Örnek

Bkz. [işleç!=](#op_neq) kullanma `operator+=`örneği için.

## <a name="fposoperator-"></a><a name="operator-"></a>fpos::operatör-

Dosya konumu göstergesini karara erdirin.

```cpp
streamoff operator-(const fpos<Statetype>& right) const;

fpos<Statetype> operator-(streamoff _Off) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Dosya konumu.

*_off*\
Akış ofset.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlev `(streamoff)*this - (streamoff) right`döndürür. İkinci üye işlev `fpos(*this) -= _Off`döndürür.

### <a name="example"></a>Örnek

Bkz. [işleç!=](#op_neq) kullanma `operator-`örneği için.

## <a name="fposoperator-"></a><a name="operator-_eq"></a>fpos::operatör-=

Dosya konumu göstergesini karara erdirin.

```cpp
fpos<Statetype>& operator-=(streamoff _Off);
```

### <a name="parameters"></a>Parametreler

*_off*\
Akış ofset.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev `fpos(*this) -= _Off`döndürür.

### <a name="remarks"></a>Açıklamalar

Bir dosya içinde konumlandırma için, sonuç genellikle yalnızca duruma bağlı kodlaması olmayan ikili akışlar için geçerlidir.

### <a name="example"></a>Örnek

Bkz. [işleç!=](#op_neq) kullanma `operator-=`örneği için.

## <a name="fposoperator"></a><a name="op_eq_eq"></a>fpos::operator==

Eşitlik için dosya konum göstergelerini sınar.

```cpp
bool operator==(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Karşılaştırılabilen dosya konumu göstergesi.

### <a name="return-value"></a>Dönüş Değeri

dosya konum göstergeleri eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Üye işlev `(streamoff)*this == (streamoff)right`döndürür.

### <a name="example"></a>Örnek

Bkz. [işleç!=](#op_neq) kullanma `operator+=`örneği için.

## <a name="fposoperator-streamoff"></a><a name="op_streamoff"></a>fpos::operatör streamoff

Türünün nesnesine `fpos` türün `streamoff`döküm nesnesi.

```cpp
operator streamoff() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, depolanan ofset üye nesnesini ve `fpos_t` üye nesnenin bir parçası olarak depolanan ek mahsupları döndürür.

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

## <a name="fposseekpos"></a><a name="seekpos"></a>fpos::seekpos

Bu yöntem yalnızca C++ Standart Kitaplığı tarafından dahili olarak kullanılır. Bu yöntemi kodunuzdan aramayın.

```cpp
fpos_t seekpos() const;
```

## <a name="fposstate"></a><a name="state"></a>fpos::durum

Dönüşüm durumunu ayarlar veya döndürür.

```cpp
Statetype state() const;

void state(Statetype _State);
```

### <a name="parameters"></a>Parametreler

*_state*\
Yeni dönüşüm durumu.

### <a name="return-value"></a>Dönüş Değeri

Dönüşüm durumu.

### <a name="remarks"></a>Açıklamalar

İlk üye `St` işlev, üye nesnede depolanan değeri döndürür. İkinci üye `St` *işlev, üye* nesnede _State depolar.

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

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
