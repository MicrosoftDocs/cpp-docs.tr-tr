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
ms.openlocfilehash: 37536443455ca4ddc40568e15951b814982d4ad9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87193308"
---
# <a name="fpos-class"></a>fpos Sınıfı

Sınıf şablonu, herhangi bir akışta rastgele bir dosya konumu göstergesini geri yüklemek için gereken tüm bilgileri depolayabilen bir nesneyi tanımlar. Fpos sınıfının bir nesnesi, \< **St**> en az iki üye nesnesini etkin bir şekilde depolar:

- [Streamoff](../standard-library/ios-typedefs.md#streamoff)türünde bir bayt kayması.

- Genellikle türündeki basic_filebuf sınıfının bir nesnesi tarafından kullanılmak üzere bir dönüştürme durumu `St` `mbstate_t` .

Ayrıca, türü [basic_filebuf](../standard-library/basic-filebuf-class.md)bir nesne tarafından kullanılmak üzere rastgele bir dosya konumunu da depolayabilirler `fpos_t` . Ancak, sınırlı dosya boyutu olan bir ortam için `streamoff` ve `fpos_t` bazen birbirlerinin yerine kullanılabilir. Duruma bağlı bir kodlamalı akış içermeyen bir ortam için `mbstate_t` gerçekten kullanılmıyor olabilir. Bu nedenle, depolanan üye nesnelerinin sayısı farklılık gösterebilir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Statetype>
class fpos
```

### <a name="parameters"></a>Parametreler

*StateType*\
Durum bilgileri.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[fpos](#fpos)|Akıştaki bir konum (konum) hakkında bilgi içeren bir nesne oluşturun.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[seekpos](#seekpos)|Yalnızca C++ standart kitaplığı tarafından dahili olarak kullanılır. Bu yöntemi kodınızdan çağırmayın.|
|[durumunda](#state)|Dönüştürme durumunu ayarlar veya döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç! =](#op_neq)|Eşitsizlik için dosya konumu göstergelerini sınar.|
|[işleç +](#op_add)|Bir dosya konumu göstergesini arttırır.|
|[işleç + =](#op_add_eq)|Bir dosya konumu göstergesini arttırır.|
|[işlecinde](#operator-)|Bir dosya konumu göstergesini azaltır.|
|[işleç-=](#operator-_eq)|Bir dosya konumu göstergesini azaltır.|
|[işleç = =](#op_eq_eq)|Eşitlik için dosya konumu göstergelerini sınar.|
|[streamoff işleci](#op_streamoff)|Türündeki nesne türündeki nesneye yayınlar `fpos` `streamoff` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<ios>

**Ad alanı:** std

## <a name="fposfpos"></a><a name="fpos"></a>fpos:: fpos

Akıştaki bir konum (konum) hakkında bilgi içeren bir nesne oluşturun.

```cpp
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```

### <a name="parameters"></a>Parametreler

*_Off*\
Akışa yönelik konum.

*_State*\
Nesnenin başlangıç durumu `fpos` .

*_Filepos*\
Akışa yönelik konum.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, dosyanın başlangıcına ve ilk dönüştürme durumunda (önemli olursa) göreli *_Off*uzaklıkları depolar. *_Off* -1 ise, elde edilen nesne geçersiz bir akış konumunu temsil eder.

İkinci oluşturucu sıfır bir konum ve nesne *_State*depolar.

## <a name="fposoperator"></a><a name="op_neq"></a>fpos:: operator! =

Eşitsizlik için dosya konumu göstergelerini sınar.

```cpp
bool operator!=(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak dosya konumu göstergesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** dosya konumu göstergeleri eşitse, tersi durumda **`false`** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `!(*this == right)` .

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

## <a name="fposoperator"></a><a name="op_add"></a>fpos:: operator +

Bir dosya konumu göstergesini arttırır.

```cpp
fpos<Statetype> operator+(streamoff _Off) const;
```

### <a name="parameters"></a>Parametreler

*_Off*\
Dosya konumu göstergesini artırmak istediğiniz fark.

### <a name="return-value"></a>Dönüş Değeri

Dosyadaki konum.

### <a name="remarks"></a>Açıklamalar

Üye işlevi **fpos ( \* this) + =** döndürür `_Off` .

### <a name="example"></a>Örnek

Bir örneği için bkz. [operator! =](#op_neq) `operator+` .

## <a name="fposoperator"></a><a name="op_add_eq"></a>fpos:: operator + =

Bir dosya konumu göstergesini arttırır.

```cpp
fpos<Statetype>& operator+=(streamoff _Off);
```

### <a name="parameters"></a>Parametreler

*_Off*\
Dosya konumu göstergesini artırmak istediğiniz fark.

### <a name="return-value"></a>Dönüş Değeri

Dosyadaki konum.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanan fark üye nesnesine *_Off* ekler ve ** \* bunu**döndürür. Bir dosya içinde konumlandırma için, sonuç genellikle yalnızca durum bağımlı kodlamalı olmayan ikili akışlar için geçerlidir.

### <a name="example"></a>Örnek

Bir örneği için bkz. [operator! =](#op_neq) `operator+=` .

## <a name="fposoperator-"></a><a name="operator-"></a>fpos:: operator-

Bir dosya konumu göstergesini azaltır.

```cpp
streamoff operator-(const fpos<Statetype>& right) const;

fpos<Statetype> operator-(streamoff _Off) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Dosya konumu.

*_Off*\
Akış boşluğu.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi döndürür `(streamoff)*this - (streamoff) right` . İkinci üye işlevi döndürür `fpos(*this) -= _Off` .

### <a name="example"></a>Örnek

Bir örneği için bkz. [operator! =](#op_neq) `operator-` .

## <a name="fposoperator-"></a><a name="operator-_eq"></a>fpos:: operator-=

Bir dosya konumu göstergesini azaltır.

```cpp
fpos<Statetype>& operator-=(streamoff _Off);
```

### <a name="parameters"></a>Parametreler

*_Off*\
Akış boşluğu.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi döndürür `fpos(*this) -= _Off` .

### <a name="remarks"></a>Açıklamalar

Bir dosya içinde konumlandırma için, sonuç genellikle yalnızca durum bağımlı kodlamalı olmayan ikili akışlar için geçerlidir.

### <a name="example"></a>Örnek

Bir örneği için bkz. [operator! =](#op_neq) `operator-=` .

## <a name="fposoperator"></a><a name="op_eq_eq"></a>fpos:: operator = =

Eşitlik için dosya konumu göstergelerini sınar.

```cpp
bool operator==(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak dosya konumu göstergesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** dosya konumu göstergeleri eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `(streamoff)*this == (streamoff)right` .

### <a name="example"></a>Örnek

Bir örneği için bkz. [operator! =](#op_neq) `operator+=` .

## <a name="fposoperator-streamoff"></a><a name="op_streamoff"></a>fpos:: operator streamoff

Türündeki nesne türü nesne türüne dönüştürüldü `fpos` `streamoff` .

```cpp
operator streamoff() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı fark üye nesnesini ve üye nesnesinin bir parçası olarak depolanan ek sapmayı döndürür `fpos_t` .

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

## <a name="fposseekpos"></a><a name="seekpos"></a>fpos:: seekpos

Bu yöntem yalnızca C++ standart kitaplığı tarafından dahili olarak kullanılır. Bu yöntemi kodınızdan çağırmayın.

```cpp
fpos_t seekpos() const;
```

## <a name="fposstate"></a><a name="state"></a>fpos:: State

Dönüştürme durumunu ayarlar veya döndürür.

```cpp
Statetype state() const;

void state(Statetype _State);
```

### <a name="parameters"></a>Parametreler

*_State*\
Yeni dönüştürme durumu.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürme durumu.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, üye nesnesinde depolanan değeri döndürür `St` . İkinci üye işlevi üye nesnesinde *_State* depolar `St` .

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

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
