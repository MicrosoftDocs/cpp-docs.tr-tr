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
ms.openlocfilehash: 0b8bb688a0a79c82d4a8baa13ef2841956b5e331
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101722"
---
# <a name="basicstringbuf-class"></a>basic_stringbuf Sınıfı

Türünde öğeler aktarımını denetleyen bir akış arabelleğinin açıklar `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`, için ve bir dizi nesnesinde saklanan öğe dizisi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>,
    class Alloc = allocator<Elem>>
class basic_stringbuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Ayırma*<br/>
Ayırıcı sınıf.

*Elem*<br/>
Dizenin temel öğe türü.

*tr*<br/>
Karakter nitelikleri temel dize öğesinde anlayışıyla çalışır.

## <a name="remarks"></a>Açıklamalar

Nesne ayrılmış, genişletilmiş ve değişiklikler sıralamadaki sığdırmak için gerektiği şekilde serbest.

Basic_stringbuf sınıfı bir nesnenin < `Elem`, `Tr`, `Alloc`> kopyasını depoladığından `ios_base::` [AçmaModu](../standard-library/ios-base-class.md#openmode) bağımsız kendi bir oluşturucudan kendi `stringbuf` modu **modu** :

- Varsa `mode & ios_base::in` olan sıfır olmayan, giriş arabelleği erişilebilir. Daha fazla bilgi için [basic_streambuf sınıfı](../standard-library/basic-streambuf-class.md).

- Varsa `mode & ios_base::out` olan sıfır olmayan, çıkış arabelleği erişilebilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_stringbuf](#basic_stringbuf)|Türünde bir nesne oluşturur `basic_stringbuf`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Şablon parametresi için bir eşanlamlı türüdür *ayırma*.|
|[char_type](#char_type)|Bir tür adıyla ilişkilendirir *Elem* şablon parametresi.|
|[int_type](#int_type)|İçinde bu tür yapar `basic_filebuf`'s kapsamı aynı ada türüne eşdeğer *Tr* kapsam.|
|[off_type](#off_type)|İçinde bu tür yapar `basic_filebuf`'s kapsamı aynı ada türüne eşdeğer *Tr* kapsam.|
|[pos_type](#pos_type)|İçinde bu tür yapar `basic_filebuf`'s kapsamı aynı ada türüne eşdeğer *Tr* kapsam.|
|[traits_type](#traits_type)|Bir tür adıyla ilişkilendirir *Tr* şablon parametresi.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[taşma](#overflow)|Yeni bir karakteri tam bir arabelleğe eklendiğinde çağrılabilir korumalı, sanal işlev.|
|[pbackfail](#pbackfail)|Bir öğe giriş arabelleğine geri yerleştirmek için korumalı sanal üye işlev çalıştığında ardından sağlar (sonraki işaretçisi tarafından işaret edilen) geçerli öğe.|
|[seekoff](#seekoff)|Korumalı sanal üye işlevi, geçerli konumlar denetimli akışları için alter dener.|
|[seekpos](#seekpos)|Korumalı sanal üye işlevi, geçerli konumlar denetimli akışları için alter dener.|
|[str](#str)|Yazma konumunu değiştirmeden dize arabellekteki metni alır veya ayarlar.|
|swap||
|[yetersiz kalması](#underflow)|Geçerli öğe girdi akışından ayıklanacak korumalı sanal üye işlevi.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<sstream >

**Namespace:** std

## <a name="allocator_type"></a>  basic_stringbuf::allocator_type

Şablon parametresi için bir eşanlamlı türüdür *ayırma*.

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

*_Modu*<br/>
Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*str*<br/>
Bir nesne türü [basic_string](../standard-library/basic-string-class.md).

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu giriş arabelleği ve çıkış arabelleği denetleme tüm işaretçilerin null bir işaretçi depolar. Daha fazla bilgi için Açıklamalar bölümüne bakın. [basic_streambuf sınıfı](../standard-library/basic-streambuf-class.md). Ayrıca depolar *_modu* stringbuf modu. Daha fazla bilgi için Açıklamalar bölümüne bakın. [basic_stringbuf sınıfı](../standard-library/basic-stringbuf-class.md).

İkinci oluşturucu dize nesnesi tarafından denetlenen dizinin bir kopyasını ayırır *str*. Varsa `_Mode & ios_base::in` olan sıfır değilse, bunu okunurken dizi başlangıcı'nı başlatmak için giriş arabelleği ayarlar. Varsa `_Mode & ios_base::out` olan sıfır değilse, onu çıkış arabelleği sırasının başlangıcında yazmaya başlamak için ayarlar. Ayrıca depolar *_modu* stringbuf modu. Daha fazla bilgi için Açıklamalar bölümüne bakın. [basic_stringbuf sınıfı](../standard-library/basic-stringbuf-class.md).

## <a name="char_type"></a>  basic_stringbuf::char_type

Bir tür adıyla ilişkilendirir *Elem* şablon parametresi.

```cpp
typedef Elem char_type;
```

## <a name="int_type"></a>  basic_stringbuf::int_type

Bu tür basic_filebuf'ın kapsamında aynı adı türü için eşdeğer yapar `Tr` kapsam.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="off_type"></a>  basic_stringbuf::off_type

Bu tür basic_filebuf'ın kapsamında aynı adı türü için eşdeğer yapar `Tr` kapsam.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="overflow"></a>  basic_stringbuf::Overflow

Yeni bir karakteri tam bir arabelleğe eklendiğinde çağrılabilir korumalı sanal işlev.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*<br/>
Karakter arabelleğine ekleme veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürür `traits_type::eof`. Aksi halde **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*).

### <a name="remarks"></a>Açıklamalar

_ *Meta* eşit karşılaştırmaz **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), korumalı sanal üye işlevi öğe ekleme girişiminde **traits_type::** [ to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*) çıktı arabelleğine. Bunu çeşitli yöntemlerle yapabilirsiniz:

- Yazma konumunu varsa, bu öğe yazma konumuna depolayabilir ve çıkış arabelleği için sonraki işaretçisine artırılacak.

- Çıkış arabelleği için yeni veya ek depolama alanı ayırarak bunu yazma konumunu kullanılabilir duruma getirebilirsiniz. Çıkış arabelleği bu şekilde genişleterek, ilişkili tüm giriş arabelleği genişletir.

## <a name="pbackfail"></a>  basic_stringbuf::pbackfail

Korumalı sanal üye işlevi, bir öğe giriş arabelleğe geri yerleştirin ve ardından (sonraki işaretçisi tarafından işaret edilen) geçerli öğe kolaylaştırmak çalışır.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*<br/>
Karakter arabelleğine ekleme veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürür `traits_type::eof`. Aksi halde **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*).

### <a name="remarks"></a>Açıklamalar

Varsa *_Meta* karşılaştırır eşit **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), geri göndermek için etkili bir şekilde akış önce geçerli öğe zaten bir öğedir. Aksi takdirde, bu öğe tarafından değiştirilir **bayt** = **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(_ *Meta*). İşlevi, öğenin çeşitli yollarla geri koyabilirsiniz:

- Putback konum kullanılabilir ve burada depolanan öğenin bayta eşit karşılaştırır, sonraki işaretçisi giriş arabelleği için azaltma.

- Putback konumu varsa ve stringbuf modu sırası değiştirilecek veriyorsa ( **modu & ios_base::out** sıfır dışında), bayt putback konumda depolamak ve sonraki işaretçisi giriş arabelleği için azaltma.

## <a name="pos_type"></a>  basic_stringbuf::pos_type

Bu tür basic_filebuf'ın kapsamında aynı adı türü için eşdeğer yapar `Tr` kapsam.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a>  basic_stringbuf::seekoff

Korumalı sanal üye işlevi, geçerli konumlar denetimli akışları için alter dener.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Off*<br/>
Arama için göreli konumunu *_Way*. Daha fazla bilgi için [basic_stringbuf::off_type](#off_type).

*_Way*<br/>
İşlemleri için başlangıç noktası. Bkz: [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) için olası değerler.

*_Modu*<br/>
İşaretçisi konumunu modunu belirtir. Değiştirme okuma ve yazma konumları olanak tanımak için varsayılandır. Daha fazla bilgi için [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

### <a name="return-value"></a>Dönüş Değeri

Yeni bir konuma veya geçersiz akış konumu döndürür.

### <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi için `basic_stringbuf<Elem, Tr, Alloc>`, yalnızca bir akış uzaklığı akış konumu oluşur. Uzaklık sıfır değerinin denetlenen dizideki ilk öğeyi belirtir.

Yeni konumu şu şekilde belirlenir:

- Varsa `_Way`  ==  `ios_base::beg`, artı akış başlangıcına yeni konumudur *_Off*.

- Varsa `_Way`  ==  `ios_base::cur`, yeni konumu geçerli stream konumudur yanı sıra *_Off*.

- Varsa `_Way`  ==  `ios_base::end`, artı akışın sonuna yeni konumudur *_Off*.

Varsa `_Mode & ios_base::in` olan sıfır değilse, işlev giriş arabelleğinde okumak için bir sonraki konuma değiştirir. Varsa `_Mode & ios_base::out` olan sıfır değilse, işlev çıkış arabelleğinin yazmak için bir sonraki konuma değiştirir. Bir akış etkilenecek kendi arabellek mevcut olması gerekir. Başarılı olması yerleştirme işlemi için akış konumu, denetlenen bir dizi içinde yer almalıdır. İşlev hem de stream konumları etkilerse *_Way* olmalıdır `ios_base::beg` veya `ios_base::end` ve her iki akışları aynı öğe konumlandırılır. Aksi takdirde (veya hiçbiri konumu etkilenir), yerleştirme işlemi başarısız olur.

Ya da akış konumlarını değiştirme işlev başarılı olursa, sonuç akış konumu döndürür. Aksi takdirde başarısız olur ve geçersiz akış konumunu döndürür.

## <a name="seekpos"></a>  basic_stringbuf::seekpos

Korumalı sanal üye işlevi, geçerli konumlar denetimli akışları için alter dener.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*<br/>
Arama konumu.

*_Modu*<br/>
İşaretçisi konumunu modunu belirtir. Değiştirme okuma ve yazma konumları olanak tanımak için varsayılandır.

### <a name="return-value"></a>Dönüş Değeri

Ya da akış konumlarını değiştirme işlev başarılı olursa, sonuç akış konumu döndürür. Aksi takdirde başarısız olur ve geçersiz akış konumunu döndürür. Akış konumu geçersiz olup olmadığını belirlemek için dönüş değeri ile karşılaştırmak `pos_type(off_type(-1))`.

### <a name="remarks"></a>Açıklamalar

Basic_stringbuf sınıfı bir nesne için < **Elem**, **Tr**, `Alloc`>, bir akış konumu bir akış uzaklığı tamamen oluşur. Uzaklık sıfır değerinin denetlenen dizideki ilk öğeyi belirtir. Yeni konumunu _ tarafından belirlenir *Sp*.

Varsa **modu & ios_base::in** olan sıfır değilse, işlev giriş arabelleğinde okumak için bir sonraki konuma değiştirir. Varsa **modu & ios_base::out** olan sıfır değilse, işlev çıkış arabelleğinin yazmak için bir sonraki konuma değiştirir. Bir akış etkilenecek kendi arabellek mevcut olması gerekir. Başarılı olması yerleştirme işlemi için akış konumu, denetlenen bir dizi içinde yer almalıdır. Aksi takdirde (veya hiçbiri konumu etkilenir), yerleştirme işlemi başarısız olur.

## <a name="str"></a>  basic_stringbuf::Str

Yazma konumunu değiştirmeden dize arabellekteki metni alır veya ayarlar.

```cpp
basic_string<Elem, Tr, Alloc> str() const;
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametreler

*_Newstr*<br/>
Yeni bir dize.

### <a name="return-value"></a>Dönüş Değeri

Sınıfın bir nesnesi döndürür [basic_string](../standard-library/basic-string-class.md) \< **Elem**, **Tr**, ayırma **>,** , denetlenen bir dizi olan bir kopyasını dizisi denetlenmektedir  **\*bu**.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi bir nesne sınıfı basic_string döndürür < **Elem**, **Tr**, `Alloc`>, denetlenen sırasıdır tarafından denetlenen dizinin bir kopyasını  **\*bu**. Kopyalanan dizisi saklı stringbuf moduna bağlıdır:

- Varsa **modu & ios_base::out** sıfır dışında olan ve bir çıkış arabelleği var, tüm çıkış arabelleği dizisidir ( [epptr](../standard-library/basic-streambuf-class.md#epptr) - [pbase](../standard-library/basic-streambuf-class.md#pbase) başlayan öğeleri ile `pbase`).

- Varsa **modu & ios_base::in** sıfır dışında olan ve bir giriş arabellek var, tüm giriş arabelleği dizisidir ( [egptr](../standard-library/basic-streambuf-class.md#egptr) - [eback](../standard-library/basic-streambuf-class.md#eback) başlayarak öğeleri `eback`).

- Aksi takdirde, kopyalanan dizisi boştur.

İkinci üye işlevi herhangi bir dizisi tarafından şu anda denetlenen kaldırır  **\*bu**. Ardından tarafından denetlenen dizinin bir kopyasını ayırır *_Newstr*. Varsa **modu & ios_base::in** olan sıfır değilse, bunu dizisi başına okuma başlatmak için giriş arabelleği ayarlar. Varsa **modu & ios_base::out** olan sıfır değilse, bunu yazma dizisi başına başlatmak için çıkış arabelleği ayarlar.

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

Bir tür adıyla ilişkilendirir *Tr* şablon parametresi.

```cpp
typedef Tr traits_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *Tr*.

## <a name="underflow"></a>  basic_stringbuf::underflow

Korumalı, geçerli öğe girdi akışından ayıklanacak sanal işlev.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürür **traits_type::**[eof](../standard-library/char-traits-struct.md#eof). Aksi takdirde, dönüştürüldüğü giriş akışında geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, geçerli öğe ayıklamak dener `byte` giriş arabellekteki geçerli stream konumuna ilerleyin ve öğenin iade **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **bayt**). Bir yolla bunu yapabilirsiniz: Okuma konumuna kullanılabilir haldeyse, sürdüğünü `byte` öğesi salt okunur bir konumda depolanan ve giriş arabelleği için sonraki işaretçisi ilerler.

## <a name="swap"></a>  basic_streambuf::Swap

Bu dize arabellek ile başka bir dize arabelleğine içeriğini değiştirir.

```cpp
void basic_stringbuf<T>::swap(basic_stringbuf& other)
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
İçerikleri takas basic_stringbuf bu basic_stringbuf ile.

### <a name="remarks"></a>Açıklamalar

## <a name="op_eq"></a>  basic_stringbuf::operator =

Basic_stringbuf işlecin sağ tarafındaki içeriğini sol tarafındaki basic_stringbuf atar.

```cpp
basic_stringbuf& basic_stringbuf:: operator=(const basic_stringbuf& other)
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Bir basic_stringbuf yerel özellikleri dahil olmak üzere içerikleri işlecinin sol tarafındaki stringbuf atanır.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
