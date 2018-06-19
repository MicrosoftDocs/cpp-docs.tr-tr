---
title: basic_stringbuf sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- sstream/std::basic_stringbuf
- sstream/std::basic_stringbuf::allocator_type
- sstream/std::basic_stringbuf::char_type
- sstream/std::basic_stringbuf::int_type
- sstream/std::basic_stringbuf::off_type
- sstream/std::basic_stringbuf::pos_type
- sstream/std::basic_stringbuf::traits_type
- sstream/std::basic_stringbuf::overflow
- sstream/std::basic_stringbuf::pbackfail
- sstream/std::basic_stringbuf::seekoff
- sstream/std::basic_stringbuf::seekpos
- sstream/std::basic_stringbuf::str
- sstream/std::basic_stringbuf::underflow
dev_langs:
- C++
helpviewer_keywords:
- std::basic_stringbuf [C++]
- std::basic_stringbuf [C++], allocator_type
- std::basic_stringbuf [C++], char_type
- std::basic_stringbuf [C++], int_type
- std::basic_stringbuf [C++], off_type
- std::basic_stringbuf [C++], pos_type
- std::basic_stringbuf [C++], traits_type
- std::basic_stringbuf [C++], overflow
- std::basic_stringbuf [C++], pbackfail
- std::basic_stringbuf [C++], seekoff
- std::basic_stringbuf [C++], seekpos
- std::basic_stringbuf [C++], str
- std::basic_stringbuf [C++], underflow
ms.assetid: 40c85f9e-42a5-4a65-af5c-23c8e3bf8113
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e7ec812ffeb50e83d59df764224ed9dcdaf07d8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33848547"
---
# <a name="basicstringbuf-class"></a>basic_stringbuf Sınıfı

Türündeki öğeler iletimini denetleyen bir Akış Arabellek açıklar `Elem`, olan karakter nitelikler sınıfı tarafından belirlenir `Tr`, gelen ve giden bir dizi nesnesi içinde depolanan öğeleri dizisi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>,
    class Alloc = allocator<Elem>>
class basic_stringbuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

`Alloc` Allocator sınıfı.

`Elem` Dizenin temel öğe türü.

`Tr` Karakter nitelikler dize temel öğede özelleştirilmiş.

## <a name="remarks"></a>Açıklamalar

Nesne ayrılmış, genişletilmiş ve değişiklikleri sırada uyum için gereken serbest.

Bir nesne sınıfı basic_stringbuf < `Elem`, `Tr`, `Alloc`> bir kopyasını depolar `ios_base::` [AçmaModu](../standard-library/ios-base-class.md#openmode) bağımsız kendi oluşturucusundan kendi `stringbuf` modu **modu** :

- Varsa `mode & ios_base::in` olduğu sıfır olmayan, giriş arabelleği erişilebilir. Daha fazla bilgi için bkz: [basic_streambuf sınıfı](../standard-library/basic-streambuf-class.md).

- Varsa `mode & ios_base::out` olduğu sıfır olmayan, çıkış arabelleği erişilebilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_stringbuf](#basic_stringbuf)|Türünde bir nesne oluşturur `basic_stringbuf`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Şablon parametresi için bir eş anlamlı türüdür `Alloc`.|
|[char_type](#char_type)|Bir tür adıyla ilişkilendirir `Elem` şablon parametresi.|
|[int_type](#int_type)|İçinde bu tür yapar `basic_filebuf`'s kapsam aynı adı türü eşdeğer `Tr` kapsam.|
|[off_type](#off_type)|İçinde bu tür yapar `basic_filebuf`'s kapsam aynı adı türü eşdeğer `Tr` kapsam.|
|[pos_type](#pos_type)|İçinde bu tür yapar `basic_filebuf`'s kapsam aynı adı türü eşdeğer `Tr` kapsam.|
|[traits_type](#traits_type)|Bir tür adıyla ilişkilendirir `Tr` şablon parametresi.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Taşma](#overflow)|Yeni bir karakter tam arabelleğine takıldığında çağrılabilir korumalı, sanal işlev.|
|[pbackfail](#pbackfail)|Öğenin giriş arabelleğine geri koymak için korumalı sanal üye işlevi denemeden sonra kılar (tarafından sonraki işaretçisi işaret) geçerli öğe.|
|[seekoff](#seekoff)|Korumalı sanal üye fonksiyonu geçerli konumlar denetimli akışlar için alter dener.|
|[seekpos](#seekpos)|Korumalı sanal üye fonksiyonu geçerli konumlar denetimli akışlar için alter dener.|
|[str](#str)|Yazma konumunu değiştirmeden dize arabellekte metni alır veya ayarlar.|
|swap||
|[underflow](#underflow)|Giriş akışından geçerli öğe ayıklamak için korunan sanal üye işlevi.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<sstream >

**Namespace:** std

## <a name="allocator_type"></a>  basic_stringbuf::allocator_type

Şablon parametresi için bir eş anlamlı türüdür `Alloc`.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringbuf"></a>  basic_stringbuf::basic_stringbuf

Türünde bir nesne oluşturur `basic_stringbuf`.

```cpp
basic_stringbuf(
    ios_base::openmode _Mode = ios_base::in | ios_base::out);

basic_stringbuf(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

`_Mode` Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

`str` Türünde bir nesne [basic_string](../standard-library/basic-string-class.md).

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu null işaretçi giriş arabelleği ve çıkış arabelleği denetleme tüm işaretçiler içinde depolar. Daha fazla bilgi için Açıklamalar bölümüne bakın [basic_streambuf sınıfı](../standard-library/basic-streambuf-class.md). Ayrıca depolar `_Mode` stringbuf modu. Daha fazla bilgi için Açıklamalar bölümüne bakın [basic_stringbuf sınıfı](../standard-library/basic-stringbuf-class.md).

İkinci oluşturucu dize nesnesi tarafından denetlenen sırasının bir kopyasını ayırır `str`. Varsa `_Mode & ios_base::in` olduğu sıfır olmayan, onu okuma sırası başlatma sırasında başlatmak için giriş arabelleği ayarlar. Varsa `_Mode & ios_base::out` olduğu sıfır olmayan, onu dizisi başlangıcında yazmaya başlamak için çıkış arabelleği ayarlar. Ayrıca depolar `_Mode` stringbuf modu. Daha fazla bilgi için Açıklamalar bölümüne bakın [basic_stringbuf sınıfı](../standard-library/basic-stringbuf-class.md).

## <a name="char_type"></a>  basic_stringbuf::char_type

Bir tür adıyla ilişkilendirir **Elem** şablon parametresi.

```cpp
typedef Elem char_type;
```

## <a name="int_type"></a>  basic_stringbuf::int_type

Bu tür basic_filebuf'ın kapsamında aynı adı türü eşdeğer yapar **Tr** kapsam.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="off_type"></a>  basic_stringbuf::off_type

Bu tür basic_filebuf'ın kapsamında aynı adı türü eşdeğer yapar **Tr** kapsam.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="overflow"></a>  basic_stringbuf::Overflow

Yeni bir karakter tam arabelleğine takıldığında çağrılabilir korumalı sanal işlev.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

`_Meta` Arabelleğe eklemek için karakter veya **traits_type::eof**.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olması durumunda, döndürür **traits_type::eof**. Aksi takdirde, döndürür **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*).

### <a name="remarks"></a>Açıklamalar

Varsa _ *Meta* eşit karşılaştırmak değil **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), korumalı sanal üye fonksiyonu öğe ekleme girişiminde **traits_type::** [ to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*) çıkış arabelleği içine. Bunu çeşitli yöntemlerle yapabilirsiniz:

- Yazma konumunu varsa, bu öğenin yazma konumunu depolamak ve çıkış arabelleği için sonraki işaretçisi Artır.

- Çıkış arabelleği için yeni veya ek depolama alanı ayırarak, yazma konumunu kullanılabilir hale getirebilirsiniz. Çıkış arabelleği bu şekilde genişletme, ilişkili tüm giriş arabelleği genişletir.

## <a name="pbackfail"></a>  basic_stringbuf::pbackfail

Bir öğe giriş arabelleğe geri alın ve bunu (tarafından sonraki işaretçisi işaret) geçerli öğe yapmak korumalı sanal üye fonksiyonu çalışır.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

`_Meta` Arabelleğe eklemek için karakter veya **traits_type::eof**.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olması durumunda, döndürür **traits_type::eof**. Aksi takdirde, döndürür **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*).

### <a name="remarks"></a>Açıklamalar

Varsa `_Meta` karşılaştırır eşit **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), geri göndermek için etkili bir şekilde akış geçerli öğe zaten bir öğedir. Aksi takdirde, bu öğenin değiştirilmiştir **bayt** = **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(_ *Meta*). İşlev, çeşitli yollarla bir öğe geri koyabilirsiniz:

- Kullanılabilir putback konumdur ve depolanan öğesi bayta eşit karşılaştırır, giriş arabelleği için sonraki işaretçisi azaltma.

- Putback konumu varsa ve stringbuf modu değiştirilmesi sıralı veriyorsa ( **modu & ios_base::out** sıfır olmayan olan), bayt putback konumda depolamak ve giriş arabelleği için sonraki işaretçisi azaltma.

## <a name="pos_type"></a>  basic_stringbuf::pos_type

Bu tür basic_filebuf'ın kapsamında aynı adı türü eşdeğer yapar **Tr** kapsam.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a>  basic_stringbuf::seekoff

Korumalı sanal üye fonksiyonu geçerli konumlar denetimli akışlar için alter dener.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

`_Off` Göreli olarak için arama konumunu `_Way`. Daha fazla bilgi için bkz: [basic_stringbuf::off_type](#off_type).

`_Way` Uzaklık işlemleri için başlangıç noktası. Bkz: [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) olası değerler için.

`_Mode` İşaretçi konumunun modunu belirtir. Varsayılan konumlar yazma ve okuma değiştirmek izin vermektir. Daha fazla bilgi için bkz: [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

### <a name="return-value"></a>Dönüş Değeri

Yeni bir konuma veya geçersiz akış konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi için `basic_stringbuf<Elem, Tr, Alloc>`, tamamen akış uzaklığını akışı konumu oluşur. Uzaklık sıfır denetimli dizisinin ilk öğesi belirler.

Yeni bir konuma şu şekilde belirlenir:

- Varsa `_Way`  ==  `ios_base::beg`, yeni bir konuma artı akış başlangıcıdır `_Off`.

- Varsa `_Way`  ==  `ios_base::cur`, yeni konumu geçerli akış konumdur artı `_Off`.

- Varsa `_Way`  ==  `ios_base::end`, artı akışın sonuna yeni konumdur `_Off`.

Varsa `_Mode & ios_base::in` olduğu sıfır olmayan, işlevi giriş arabelleğini okumaya sonraki konuma değiştirir. Varsa `_Mode & ios_base::out` olduğu sıfır olmayan, işlevi çıkış arabelleğinin yazmak için bir sonraki konuma değiştirir. Bir akış etkilenecek arabelleğini mevcut olması gerekir. Başarılı olması konumlandırma işlemi için sonuçta elde edilen akışı konumu denetimli sırası içinde yer almalıdır. İşlev hem akış konumlar etkilerse `_Way` olmalıdır `ios_base::beg` veya `ios_base::end` ve her iki akışlar aynı öğede konumlandırılır. Aksi takdirde (veya hiçbiri konumu etkilenen varsa), yerleştirme işlemi başarısız olur.

İşlev veya her ikisini akış konumlarını değiştirmeden başarılı olursa, sonuç akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz akış konumunu döndürür.

## <a name="seekpos"></a>  basic_stringbuf::seekpos

Korumalı sanal üye fonksiyonu geçerli konumlar denetimli akışlar için alter dener.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

`_Sp` Arama konumu.

`_Mode` İşaretçi konumunun modunu belirtir. Varsayılan konumlar yazma ve okuma değiştirmek izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

İşlev veya her ikisini akış konumlarını değiştirmeden başarılı olursa, sonuç akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz akış konumunu döndürür. Akışı konumu geçersiz olup olmadığını belirlemek için dönüş değeri ile karşılaştırın `pos_type(off_type(-1))`.

### <a name="remarks"></a>Açıklamalar

Basic_stringbuf sınıfı bir nesne için < **Elem**, **Tr**, `Alloc`>, tamamen akış uzaklığını akışı konumu oluşur. Uzaklık sıfır denetimli dizisinin ilk öğesi belirler. Yeni bir konuma _ tarafından belirlenir *Sp*.

Varsa **modu & ios_base::in** olan sıfır olmayan, işlevi giriş arabelleğini okumaya sonraki konuma değiştirir. Varsa **modu & ios_base::out** olan sıfır olmayan, işlevi çıkış arabelleğinin yazmak için bir sonraki konuma değiştirir. Bir akış etkilenecek arabelleğini mevcut olması gerekir. Başarılı olması konumlandırma işlemi için sonuçta elde edilen akışı konumu denetimli sırası içinde yer almalıdır. Aksi takdirde (veya hiçbiri konumu etkilenen varsa), yerleştirme işlemi başarısız olur.

## <a name="str"></a>  basic_stringbuf::Str

Yazma konumunu değiştirmeden dize arabellekte metni alır veya ayarlar.

```cpp
basic_string<Elem, Tr, Alloc> str() const;
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametreler

`_Newstr` Yeni bir dize.

### <a name="return-value"></a>Dönüş Değeri

Sınıfın bir nesnesi döndüren [basic_string](../standard-library/basic-string-class.md) \< **Elem**, **Tr**, ayırma **>,** , denetlenen sırasıdır bir kopyasını sıra denetlenen tarafından  **\*bu**.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi sınıfı basic_string bir nesne döndürür < **Elem**, **Tr**, `Alloc`>, yalnızca denetlenen sırasıdır denetlediği sırasının bir kopyasını  **\*bu**. Kopyalanan dizisi saklı stringbuf moduna bağlıdır:

- Varsa **modu & ios_base::out** sıfır dışında olan ve bir çıkış arabelleği varsa, tüm çıkış arabelleği dizidir ( [epptr](../standard-library/basic-streambuf-class.md#epptr) - [pbase](../standard-library/basic-streambuf-class.md#pbase) başlayan öğeleri ile `pbase`).

- Varsa **modu & ios_base::in** sıfır dışında olan ve bir giriş arabelleği varsa, tüm giriş arabelleği dizidir ( [egptr](../standard-library/basic-streambuf-class.md#egptr) - [eback](../standard-library/basic-streambuf-class.md#eback) itibaren öğeleri `eback`).

- Aksi takdirde, kopyalanan sırası boş olur.

İkinci üye fonksiyonu tarafından şu anda denetlenen dizisi kaldırır  **\*bu**. Ardından denetlediği sırasının bir kopyasını ayırır `_Newstr`. Varsa **modu & ios_base::in** olan sıfır olmayan, onu okuma sırası başındaki başlatmak için giriş arabelleği ayarlar. Varsa **modu & ios_base::out** olan sıfır olmayan, onu yazma sırası başındaki başlatmak için çıkış arabelleği ayarlar.

### <a name="example"></a>Örnek

```cpp
// basic_stringbuf_str.cpp
// compile with: /EHsc
#include <iostream>
#include <sstream>

using namespace std;

int main( )
{
   basic_string<char> i( "test" );
   stringstream ss;

   ss.rdbuf( )->str( i );
   cout << ss.str( ) << endl;

   ss << "z";
   cout << ss.str( ) << endl;

   ss.rdbuf( )->str( "be" );
   cout << ss.str( ) << endl;
}
```

```Output
test
zest
be
```

## <a name="traits_type"></a>  basic_stringbuf::traits_type

Bir tür adıyla ilişkilendirir **Tr** şablon parametresi.

```cpp
typedef Tr traits_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **Tr**.

## <a name="underflow"></a>  basic_stringbuf::underflow

Korumalı, geçerli öğe giriş akışından ayıklamak için sanal işlev.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olması durumunda, döndürür **traits_type::**[eof](../standard-library/char-traits-struct.md#eof). Aksi takdirde, geçerli öğe Giriş akışı, hangi dönüştürülür döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli öğe ayıklamak korumalı sanal üye fonksiyonu çalışır **bayt** geçerli akışı konumu giriş arabelleğinden ilerleyin ve öğesi olarak dönmek **traits_type::**[için _int_type](../standard-library/char-traits-struct.md#to_int_type)( **bayt**). Bir yolla bunu yapabilirsiniz: Okuma konumu varsa, sürdüğünü **bayt** öğe okuma konumunda depolanan ve giriş arabelleği için sonraki işaretçisi ilerler.

## <a name="swap"></a>  basic_streambuf::Swap

Bu dize arabellek başka bir dize arabelleği ile içeriğini değiştirir.

```cpp
void basic_stringbuf<T>::swap(basic_stringbuf& other)
```

### <a name="parameters"></a>Parametreler

`other` İçeriği takas basic_stringbuf bu basic_stringbuf ile.

### <a name="remarks"></a>Açıklamalar

## <a name="op_eq"></a>  basic_stringbuf::operator =

Sol tarafta basic_stringbuf işlecinin sağ tarafında basic_stringbuf içeriğini atar.

```cpp
basic_stringbuf& basic_stringbuf:: operator=(const basic_stringbuf& other)
```

### <a name="parameters"></a>Parametreler

`other` Yerel ayar nitelikler dahil olmak üzere içerikleri işlecinin sol tarafındaki stringbuf atanacak basic_stringbuf.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
