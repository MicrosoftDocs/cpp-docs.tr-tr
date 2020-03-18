---
title: '&lt;dize&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- string/std::getline
- string/std::stod
- string/std::stof
- string/std::stoi
- string/std::stol
- string/std::stold
- string/std::stoll
- string/std::stoul
- string/std::stoull
- string/std::swap
- string/std::to_string
- string/std::to_wstring
ms.assetid: 1a4ffd11-dce5-4cc6-a043-b95de034c7c4
helpviewer_keywords:
- std::getline [C++]
- std::stod [C++]
- std::stof [C++]
- std::stoi [C++]
- std::stol [C++]
- std::stold [C++]
- std::stoll [C++]
- std::stoul [C++]
- std::stoull [C++]
- std::swap [C++]
- std::to_string [C++]
- std::to_wstring [C++]
ms.openlocfilehash: 828aeb975178850f5c0a7ea3b7e982bbadd6e7c4
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419492"
---
# <a name="ltstringgt-functions"></a>&lt;dize&gt; işlevleri

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[Stoi](#stoi)|[STOL](#stol)|[stold](#stold)|
|[Stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[Kur](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a>getline

Giriş akışı satır satırından dizeleri ayıkla.

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delim);

template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& is,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delim);

// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str);

template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& is,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parametreler

*\*
Bir dizenin ayıklanabileceği giriş akışı.

*str*\
Giriş akışındaki karakterleri okuyan dize.

*delib*\
Satır sınırlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Giriş *akışı.*

### <a name="remarks"></a>Açıklamalar

' Den karakter Ayıkla `(1)` işaretlenen işlev imzası çifti, bir değer *bulunana kadar,* *Str*içinde depolanana kadar *olur* .

`(2)` işaretlenen işlev imzası çifti, varsayılan satır sınırlayıcısı olarak yeni satırı kullanır ve **getline**(`is`, `str`, `is`gibi davranır. `widen`(' `\n`')).

Her bir çiftin ikinci işlevi, [Rvalue başvurularını](../cpp/lvalues-and-rvalues-visual-cpp.md)desteklemeye yönelik bir analog ' dur.

Aşağıdakilerden biri gerçekleştiğinde ayıklama işlemi duraklar:

- Dosyanın *sonunda, iç* durum bayrağı `ios_base::eofbit`olarak ayarlanır.

- İşlev, `delim`eşit olarak karşılaştırdığı bir öğeyi ayıkladıktan sonra, bu durumda öğe hiçbir şekilde geri yerleştirmez veya denetimli diziye eklenmez.

- İşlev `str.`[max_size](../standard-library/basic-string-class.md#max_size) öğelerini ayıkladıktan *sonra, bu* durumda iç durum bayrağı `ios_base::failbit`olarak ayarlanır.

- Daha önce listelenenlerden *başka bir hata* , bu durumda iç durum bayrağı `ios_base::badbit` olarak ayarlanır.

İç durum bayrakları hakkında daha fazla bilgi için bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate).

İşlev hiçbir öğe ayıkladıysanız *, iç* durum bayrağı `ios_base::failbit`olarak ayarlanır. Herhangi bir *durumda, `getline` döndürür.*

Bir özel *durum oluşturulursa, ve* *Str* geçerli bir durumda bırakılır.

### <a name="example"></a>Örnek

Aşağıdaki kod iki modda `getline()` gösterir: ilk olarak varsayılan sınırlayıcıyla (yeni satır) ve ikincisi sınırlayıcı olarak boşluk ile. While döngülerinin sonlandırılmasını denetlemek için dosya sonu karakteri (klavyede CTRL-Z) kullanılır. Bu, `cin` iç durum bayrağını `eofbit`olarak ayarlar ve bu, ikinci while döngüsünün düzgün çalışması için önce [basic_ios:: Clear ()](../standard-library/basic-ios-class.md#clear) ile temizlenmelidir.

```cpp
// compile with: /EHsc /W4
#include <string>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    string str;
    vector<string> v1;
    cout << "Enter a sentence, press ENTER between sentences. (Ctrl-Z to stop): " << endl;
    // Loop until end-of-file (Ctrl-Z) is input, store each sentence in a vector.
    // Default delimiter is the newline character.
    while (getline(cin, str)) {
        v1.push_back(str);
    }

    cout << "The following input was stored with newline delimiter:" << endl;
    for (const auto& p : v1) {
        cout << p << endl;
    }

    cin.clear();

    vector<string> v2;
    // Now try it with a whitespace delimiter
    while (getline(cin, str, ' ')) {
        v2.push_back(str);
    }

    cout << "The following input was stored with whitespace as delimiter:" << endl;
    for (const auto& p : v2) {
        cout << p << endl;
    }
}
```

## <a name="stod"></a>stod

Bir karakter dizisini **Double**'a dönüştürür.

```cpp
double stod(
    const string& str,
    size_t* idx = 0);

double stod(
    const wstring& str,
    size_t* idx = 0
;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

**Double** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini, `strtod( str.c_str(), _Eptr)`çağırarak, `_Eptr` bir işlevin dahili bir nesne olduğu, **Bu türdeki bir** değer `val` bir değere dönüştürür. ` str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve `val`döndürür.

## <a name="stof"></a>stof

Bir karakter dizisini float öğesine dönüştürür.

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

Float değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe sırasını, `strtof( str.c_str(), _Eptr)`çağırarak, `_Eptr` işlevin dahili bir nesnesi olduğu gibi **float** türünde bir değer `val` dönüştürür. ` str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve `val`döndürür.

## <a name="stoi"></a>Stoi

Bir karakter dizisini tamsayıya dönüştürür.

```cpp
int stoi(
    const string& str,
    size_t* idx = 0,
    int base = 10);

int stoi(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="return-value"></a>Dönüş Değeri

Tamsayı değeri.

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|Dönüşte dönüştürülmemiş ilk karakterin dizinini içerir.|
|*base*|Kullanılacak sayı temeli.|

### <a name="remarks"></a>Açıklamalar

İşlevi `stoi` *Str* içindeki karakter dizisini **int** türünde bir değere dönüştürür ve değeri döndürür. Örneğin, "10" karakter dizisini geçtiğinde, `stoi` tarafından döndürülen değer 10 ' dur.

`stoi` `_Eptr`, işlevin iç bir nesne olduğu `strtol( str.c_str(), _Eptr, idx)`şekilde çağrıldığında tek baytlı karakterler için `strtol` işlev gibi davranır. ya da `wcstol` benzer şekilde çağrıldığında çok sayıda karakter için `wcstol(Str.c_str(), _Eptr, idx)`. Daha fazla bilgi için bkz. [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

`str.c_str() == *_Eptr`, `stoi` `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa veya döndürülen değer **int**türünde bir nesne olarak temsil edimiyorsa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx``*_Eptr - str.c_str()` depolar.

## <a name="stol"></a>STOL

Bir karakter dizisini **Long**değerine dönüştürür.

```cpp
long stol(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long stol(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|
|*base*|Kullanılacak sayı temeli.|

### <a name="return-value"></a>Dönüş Değeri

Uzun tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini, `strtol( str.c_str(), _Eptr, idx)`çağırarak `_Eptr` bir nesne olan bir nesne olduğu **gibi,** `val` bir değere dönüştürür. ` str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve `val`döndürür.

## <a name="stold"></a>stold

Bir karakter dizisini **Long Double**'a dönüştürür.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|

### <a name="return-value"></a>Dönüş Değeri

**Long Double** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini, `strtold( str.c_str(), _Eptr)`çağırarak, `_Eptr` bir nesne olan bir nesne olduğu gibi **Long Double** türünde bir değer `val` dönüştürür. ` str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve `val`döndürür.

## <a name="stoll"></a>Stoll

Bir karakter dizisini **uzun bir uzunluğa**dönüştürür.

```cpp
long long stoll(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long long stoll(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|
|*base*|Kullanılacak sayı temeli.|

### <a name="return-value"></a>Dönüş Değeri

**Uzun uzun** değer.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini, `strtoll( str.c_str(), _Eptr, idx)`çağırarak, `_Eptr` bir nesne olan bir nesne olduğu gibi **uzun uzun** `val` bir değere dönüştürür. ` str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve `val`döndürür.

## <a name="stoul"></a>stoul

Bir karakter dizisini işaretsiz bir Long değerine dönüştürür.

```cpp
unsigned long stoul(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long stoul(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|
|*base*|Kullanılacak sayı temeli.|

### <a name="return-value"></a>Dönüş Değeri

İşaretsiz uzun tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini `strtoul( str.c_str(), _Eptr, idx)`çağırarak **işaretsiz Long** türünde bir değer `val` bir değere dönüştürür; burada `_Eptr`, işlevin dahili bir nesnesidir. ` str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve `val`döndürür.

## <a name="stoull"></a>stoull

Bir karakter dizisini **işaretsiz Long**Long değerine dönüştürür.

```cpp
unsigned long long stoull(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long long stoull(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*üstbilgisine*|Dönüştürülecek karakter sırası.|
|*idx*|İlk dönüştürülmemiş karakterin dizin değeri.|
|*base*|Kullanılacak sayı temeli.|

### <a name="return-value"></a>Dönüş Değeri

**İmzasız Long Long** değeri.

### <a name="remarks"></a>Açıklamalar

İşlevi *Str* içindeki öğe dizisini, `strtoull( str.c_str(), _Eptr, idx)`çağırarak, `_Eptr` bir nesne iç olarak bir nesne olduğu gibi **işaretsiz Long** Long türünde bir `val` değere dönüştürür. ` str.c_str() == *_Eptr`, `invalid_argument`türünde bir nesne oluşturur. Böyle bir çağrı `errno`ayarlandıysa, `out_of_range`türünde bir nesne oluşturur. Aksi halde, *idx* null bir işaretçi değilse, işlev `*idx` `*_Eptr -  str.c_str()` depolar ve `val`döndürür.

## <a name="swap"></a>Kur

İki dizenin karakter dizilerini değiş tokuş eder.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
Öğeleri başka bir dizeden değiştirilebilen bir dize.

*sağ*\
Öğeleri ilk dizeyle takas edilecek diğer dize.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, *sol taraftaki*özelleştirilmiş üye işlevini yürütür. Sabit karmaşıklığı garanti eden dizeler için [takas](../standard-library/basic-string-class.md#swap)(*sağ*).

### <a name="example"></a>Örnek

```cpp
// string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   swap ( s1 , s2 );
   cout << "\nAfter swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.

After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="to_string"></a>to_string

Bir değeri `string`dönüştürür.

```cpp
string to_string(int Val);
string to_string(unsigned int Val);
string to_string(long Val);
string to_string(unsigned long Val);
string to_string(long long Val);
string to_string(unsigned long long Val);
string to_string(float Val);
string to_string(double Val);
string to_string(long double Val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Acil*|Dönüştürülecek değer.|

### <a name="return-value"></a>Dönüş Değeri

Değeri temsil eden `string`.

### <a name="remarks"></a>Açıklamalar

İşlev, `Buf` bir dizi nesnesinde depolanan bir öğe *dizisine dönüştürür;* burada `Fmt` olduğu gibi `sprintf(Buf, Fmt, Val)`çağırarak

- `Val` **int** türünde `"%d"`

- `Val` **işaretsiz int** türünde `"%u"`

- `Val` tür **uzunsa** `"%ld"`

- `Val` tür **işaretsiz** ise `"%lu"`

- `Val` tür **uzun uzunsa** `"%lld"`

- `Val` tür **imzasız uzun uzunsa** `"%llu"`

- `Val` **float** veya **Double** türünde `"%f"`

- `Val` tür **Long Double** ise `"%Lf"`

İşlev `string(Buf)`döndürür.

## <a name="to_wstring"></a>to_wstring

Bir değeri geniş dizeye dönüştürür.

```cpp
wstring to_wstring(int Val);
wstring to_wstring(unsigned int Val);
wstring to_wstring(long Val);
wstring to_wstring(unsigned long Val);
wstring to_wstring(long long Val);
wstring to_wstring(unsigned long long Val);
wstring to_wstring(float Val);
wstring to_wstring(double Val);
wstring to_wstring(long double Val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Val`|Dönüştürülecek değer.|

### <a name="return-value"></a>Dönüş Değeri

Değeri temsil eden geniş dize.

### <a name="remarks"></a>Açıklamalar

İşlevi `Val` bir dizi nesnesinde depolanan öğelerin dizisine dönüştürür; burada `Fmt`, `swprintf(Buf, Len, Fmt, Val)`çağırarak `Buf`

- `Val` **int** türünde `L"%d"`

- `Val` **işaretsiz int** türünde `L"%u"`

- `Val` tür **uzunsa** `L"%ld"`

- `Val` tür **işaretsiz** ise `L"%lu"`

- `Val` tür **uzun uzunsa** `L"%lld"`

- `Val` tür **imzasız uzun uzunsa** `L"%llu"`

- `Val` **float** veya **Double** türünde `L"%f"`

- `Val` tür **Long Double** ise `L"%Lf"`

İşlev `wstring(Buf)`döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[\<dize >](../standard-library/string.md)
