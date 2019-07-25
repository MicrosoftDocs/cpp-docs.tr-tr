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
ms.openlocfilehash: 60d7d00e6b9426df9b3086d9b82deaf1fdd1463c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454155"
---
# <a name="fpos-class"></a>fpos Sınıfı

Şablon sınıfı, herhangi bir akışta rastgele bir dosya konumu göstergesini geri yüklemek için gereken tüm bilgileri depolayabilen bir nesneyi tanımlar. Fpos\< **St**> sınıfının bir nesnesi, en az iki üye nesnesini etkin bir şekilde depolar:

- [Streamoff](../standard-library/ios-typedefs.md#streamoff)türünde bir bayt kayması.

- `St` Genellikle`mbstate_t`türündeki basic_filebuf sınıfının bir nesnesi tarafından kullanılmak üzere bir dönüştürme durumu.

Ayrıca, türü `fpos_t` [basic_filebuf](../standard-library/basic-filebuf-class.md)sınıfının bir nesnesi tarafından kullanılmak üzere rastgele bir dosya konumunu da saklayabilir. Ancak, `streamoff` sınırlı dosya boyutu olan bir ortam için ve `fpos_t` bazen birbirlerinin yerine kullanılabilir. Duruma bağlı bir kodlamalı `mbstate_t` akış içermeyen bir ortam için gerçekten kullanılmıyor olabilir. Bu nedenle, depolanan üye nesnelerinin sayısı farklılık gösterebilir.

## <a name="syntax"></a>Sözdizimi

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
|[seekpos](#seekpos)|Yalnızca C++ standart kitaplık tarafından dahili olarak kullanılır. Bu yöntemi kodınızdan çağırmayın.|
|[durumunda](#state)|Dönüştürme durumunu ayarlar veya döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Eşitsizlik için dosya konumu göstergelerini sınar.|
|[işleç +](#op_add)|Bir dosya konumu göstergesini arttırır.|
|[operator+=](#op_add_eq)|Bir dosya konumu göstergesini arttırır.|
|[işlecinde](#operator-)|Bir dosya konumu göstergesini azaltır.|
|[işleç-=](#operator-_eq)|Bir dosya konumu göstergesini azaltır.|
|[operator==](#op_eq_eq)|Eşitlik için dosya konumu göstergelerini sınar.|
|[streamoff işleci](#op_streamoff)|Türündeki nesne `fpos` `streamoff`türündeki nesneye yayınlar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<iOS >

**Ad alanı:** std

## <a name="fpos"></a>fpos:: fpos

Akıştaki bir konum (konum) hakkında bilgi içeren bir nesne oluşturun.

```cpp
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
Akışa yönelik konum.

*_Durum*\
`fpos` Nesnenin başlangıç durumu.

*_Filepos*\
Akışa yönelik konum.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, dosyanın başlangıcına ve ilk dönüştürme durumunda (önemli olursa) göreli olarak, *_Off*konumunu depolar. *_Off* -1 ise, elde edilen nesne geçersiz bir akış konumunu temsil eder.

İkinci oluşturucu sıfır sapmasını ve nesne *_Durumunu*depolar.

## <a name="op_neq"></a>fpos:: operator! =

Eşitsizlik için dosya konumu göstergelerini sınar.

```cpp
bool operator!=(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak dosya konumu göstergesi.

### <a name="return-value"></a>Dönüş Değeri

dosya konumu göstergeleri eşitse **true** , aksi takdirde **false**.

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

## <a name="op_add"></a>fpos:: operator +

Bir dosya konumu göstergesini arttırır.

```cpp
fpos<Statetype> operator+(streamoff _Off) const;
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
Dosya konumu göstergesini artırmak istediğiniz fark.

### <a name="return-value"></a>Dönüş Değeri

Dosyadaki konum.

### <a name="remarks"></a>Açıklamalar

Üye işlevi **fpos (\*this) + =** `_Off`döndürür.

### <a name="example"></a>Örnek

Bir örneği `operator+`için bkz. [operator! =](#op_neq) .

## <a name="op_add_eq"></a>fpos:: operator + =

Bir dosya konumu göstergesini arttırır.

```cpp
fpos<Statetype>& operator+=(streamoff _Off);
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
Dosya konumu göstergesini artırmak istediğiniz fark.

### <a name="return-value"></a>Dönüş Değeri

Dosyadaki konum.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı fark üye nesnesine *_Off* ekler ve  **\*bunu**döndürür. Bir dosya içinde konumlandırma için, sonuç genellikle yalnızca durum bağımlı kodlamalı olmayan ikili akışlar için geçerlidir.

### <a name="example"></a>Örnek

Bir örneği `operator+=`için bkz. [operator! =](#op_neq) .

## <a name="operator-"></a>fpos:: operator-

Bir dosya konumu göstergesini azaltır.

```cpp
streamoff operator-(const fpos<Statetype>& right) const;

fpos<Statetype> operator-(streamoff _Off) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Dosya konumu.

*_Kapatma*\
Akış boşluğu.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi döndürür `(streamoff)*this - (streamoff) right`. İkinci üye işlevi döndürür `fpos(*this) -= _Off`.

### <a name="example"></a>Örnek

Bir örneği `operator-`için bkz. [operator! =](#op_neq) .

## <a name="operator-_eq"></a>fpos:: operator-=

Bir dosya konumu göstergesini azaltır.

```cpp
fpos<Statetype>& operator-=(streamoff _Off);
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
Akış boşluğu.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi döndürür `fpos(*this) -= _Off`.

### <a name="remarks"></a>Açıklamalar

Bir dosya içinde konumlandırma için, sonuç genellikle yalnızca durum bağımlı kodlamalı olmayan ikili akışlar için geçerlidir.

### <a name="example"></a>Örnek

Bir örneği `operator-=`için bkz. [operator! =](#op_neq) .

## <a name="op_eq_eq"></a>fpos:: operator = =

Eşitlik için dosya konumu göstergelerini sınar.

```cpp
bool operator==(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak dosya konumu göstergesi.

### <a name="return-value"></a>Dönüş Değeri

dosya konumu göstergeleri eşitse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `(streamoff)*this == (streamoff)right`.

### <a name="example"></a>Örnek

Bir örneği `operator+=`için bkz. [operator! =](#op_neq) .

## <a name="op_streamoff"></a>fpos:: operator streamoff

Türündeki nesne `fpos` türü nesne `streamoff`türüne dönüştürüldü.

```cpp
operator streamoff() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı fark üye nesnesini ve `fpos_t` üye nesnesinin bir parçası olarak depolanan ek sapmayı döndürür.

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

## <a name="seekpos"></a>fpos:: seekpos

Bu yöntem, yalnızca C++ standart kitaplık tarafından dahili olarak kullanılır. Bu yöntemi kodınızdan çağırmayın.

```cpp
fpos_t seekpos() const;
```

## <a name="state"></a>fpos:: State

Dönüştürme durumunu ayarlar veya döndürür.

```cpp
Statetype state() const;

void state(Statetype _State);
```

### <a name="parameters"></a>Parametreler

*_Durum*\
Yeni dönüştürme durumu.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürme durumu.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, `St` üye nesnesinde depolanan değeri döndürür. İkinci üye işlevi, *_State* `St` öğesini üye nesnesinde depolar.

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

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
