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
ms.openlocfilehash: 78b136d72067fa5fff58e8a7acc044fb4e1a409e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159463"
---
# <a name="fpos-class"></a>fpos Sınıfı

Şablon sınıfı, yükün herhangi bir rastgele dosya konumu göstergesi geri yüklemek için gerekli tüm bilgileri depolayan nesneyi tanımlar. Fpos sınıfı bir nesnenin\< **St**> en az iki üye nesneleri etkili bir şekilde depolar:

- Türü bir bayt uzaklığı [streamoff](../standard-library/ios-typedefs.md#streamoff).

- Bir dönüştürme, bir nesne sınıfı basic_filebuf tarafından kullanılmak üzere türünün durumunu `St`, genellikle `mbstate_t`.

Sınıfın bir nesnesi tarafından kullanılmak üzere bir rastgele dosya konumu depolayabilirsiniz [basic_filebuf](../standard-library/basic-filebuf-class.md), türü `fpos_t`. Ancak, sınırlı dosya boyutuna sahip bir ortam için `streamoff` ve `fpos_t` bazen birbirlerinin yerine kullanılabilir. Bir duruma bağlı kodlamayı sahip yoktur akışları sahip bir ortam için `mbstate_t` gerçekten kullanılmayan olabilir. Bu nedenle, depolanan üye nesne sayısı değişebilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Statetype>
class fpos
```

### <a name="parameters"></a>Parametreler

*Statetype*<br/>
Durum bilgileri.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[fpos](#fpos)|Bir akışta bir konum (kaydırma) hakkında bilgi içeren bir nesne oluşturun.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[seekpos](#seekpos)|C++ Standart Kitaplığı tarafından yalnızca dahili olarak kullanılır. Bu yöntem kodunuzdan çağırmayın.|
|[durumu](#state)|Dönüştürme durumunu döndürür veya ayarlar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Eşitsizlik için test dosya konumu göstergesi.|
|[operator +](#op_add)|Bir dosya konumu göstergesi artırır.|
|[operator+=](#op_add_eq)|Bir dosya konumu göstergesi artırır.|
|[operator-](#operator-)|Azaltır dosya konumu göstergesi.|
|[-= işleci](#operator-_eq)|Azaltır dosya konumu göstergesi.|
|[operator==](#op_eq_eq)|Eşitlik için testleri dosya konumu göstergesi.|
|[işleç streamoff](#op_streamoff)|Tür atamaları nesne `fpos` türündeki nesneye `streamoff`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ios >

**Namespace:** std

## <a name="fpos"></a>  fpos::fpos

Bir akışta bir konum (kaydırma) hakkında bilgi içeren bir nesne oluşturun.

```cpp
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```

### <a name="parameters"></a>Parametreler

*_Off*<br/>
Akış olan uzaklık.

*Duru_m*<br/>
Başlangıç durumunu `fpos` nesne.

*_Filepos*<br/>
Akış olan uzaklık.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu uzaklık depolar *_Off*, göreli başına dosyasının ve ilk dönüştürme durumunda (Bu önemli değilse). Varsa *_Off* -1, elde edilen nesnenin geçersiz akış konumu temsil eder.

İkinci oluşturucu sıfır uzunluk ve nesne depolar *duru_m*.

## <a name="op_neq"></a>  fpos::operator! =

Eşitsizlik için test dosya konumu göstergesi.

```cpp
bool operator!=(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Dosya konumu göstergesi olan karşılaştırmak.

### <a name="return-value"></a>Dönüş Değeri

**doğru** dosya konumu göstergesi Aksi takdirde eşit olup olmadığını **false**.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `!(*this == right)`.

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

## <a name="op_add"></a>  fpos::operator +

Bir dosya konumu göstergesi artırır.

```cpp
fpos<Statetype> operator+(streamoff _Off) const;
```

### <a name="parameters"></a>Parametreler

*_Off*<br/>
Dosya konumu göstergesi artırmak istediğiniz uzaklığı.

### <a name="return-value"></a>Dönüş Değeri

Dosyanın konumu.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü **fpos (\*bu) +=** `_Off`.

### <a name="example"></a>Örnek

Bkz: [işleç! =](#op_neq) kullanımının bir örneği için `operator+`.

## <a name="op_add_eq"></a>  fpos::operator +=

Bir dosya konumu göstergesi artırır.

```cpp
fpos<Statetype>& operator+=(streamoff _Off);
```

### <a name="parameters"></a>Parametreler

*_Off*<br/>
Dosya konumu göstergesi artırmak istediğiniz uzaklığı.

### <a name="return-value"></a>Dönüş Değeri

Dosyanın konumu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi ekler *_Off* saklı uzaklığında üye nesnesi ve ardından döndürür  **\*bu**. Bir dosya içinde konumlandırma için sonucu genellikle yalnızca ikili için geçerli bir duruma bağlı kodlamayı yoktur akışları.

### <a name="example"></a>Örnek

Bkz: [işleç! =](#op_neq) kullanımının bir örneği için `operator+=`.

## <a name="operator-"></a>  fpos::operator-

Azaltır dosya konumu göstergesi.

```cpp
streamoff operator-(const fpos<Statetype>& right) const;

fpos<Statetype> operator-(streamoff _Off) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Dosya konumu.

*_Off*<br/>
Stream uzaklığı.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi döndürür `(streamoff)*this - (streamoff) right`. İkinci üye işlevi döndürür `fpos(*this) -= _Off`.

### <a name="example"></a>Örnek

Bkz: [işleç! =](#op_neq) kullanımının bir örneği için `operator-`.

## <a name="operator-_eq"></a>  fpos::operator-=

Azaltır dosya konumu göstergesi.

```cpp
fpos<Statetype>& operator-=(streamoff _Off);
```

### <a name="parameters"></a>Parametreler

*_Off*<br/>
Stream uzaklığı.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevinin döndürdüğü `fpos(*this) -= _Off`.

### <a name="remarks"></a>Açıklamalar

Bir dosya içinde konumlandırma için sonucu genellikle yalnızca ikili için geçerli bir duruma bağlı kodlamayı yoktur akışları.

### <a name="example"></a>Örnek

Bkz: [işleç! =](#op_neq) kullanımının bir örneği için `operator-=`.

## <a name="op_eq_eq"></a>  fpos::operator ==

Eşitlik için testleri dosya konumu göstergesi.

```cpp
bool operator==(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Dosya konumu göstergesi olan karşılaştırmak.

### <a name="return-value"></a>Dönüş Değeri

**doğru** dosya konumu göstergesi, aksi takdirde eşit **false**.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `(streamoff)*this == (streamoff)right`.

### <a name="example"></a>Örnek

Bkz: [işleç! =](#op_neq) kullanımının bir örneği için `operator+=`.

## <a name="op_streamoff"></a>  fpos::operator streamoff

Tür atama nesne `fpos` türündeki nesneye `streamoff`.

```cpp
operator streamoff() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi saklı uzaklığında üye nesnesi ve bir parçası olarak depolanan tüm ek uzaklığı döndürür `fpos_t` üye nesnesi.

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

## <a name="seekpos"></a>  fpos::seekpos

Bu yöntem, C++ Standart Kitaplığı tarafından yalnızca dahili olarak kullanılır. Bu yöntem kodunuzdan çağırmayın.

```cpp
fpos_t seekpos() const;
```

## <a name="state"></a>  fpos::State

Dönüştürme durumunu döndürür veya ayarlar.

```cpp
Statetype state() const;

void state(Statetype _State);
```

### <a name="parameters"></a>Parametreler

*Duru_m*<br/>
Yeni dönüştürme durumu.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürme durumu.

### <a name="remarks"></a>Açıklamalar

İçinde depolanan değeri ilk üye işlevi döndürür `St` üye nesnesi. İkinci üye işlevi depoları *duru_m* içinde `St` üye nesnesi.

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
