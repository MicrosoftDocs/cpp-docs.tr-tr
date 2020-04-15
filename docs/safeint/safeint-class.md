---
title: SafeInt Sınıfı
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeInt
- SafeInt::SafeInt
- SafeInt.SafeInt
helpviewer_keywords:
- SafeInt class
- SafeInt class, constructor
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
ms.openlocfilehash: c365b5cab5814d3992e6570949a69fc5d39c1dd3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373450"
---
# <a name="safeint-class"></a>SafeInt Sınıfı

Tümsek taşmasını önlemeye yardımcı olmak için tümsesayı ilkellerini genişletir ve farklı tümsatürleri karşılaştırmanızı sağlar.

> [!NOTE]
> Bu kitaplığın en son sürümü [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt).

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>
class SafeInt;
```

### <a name="parameters"></a>Parametreler

| Şablon  |  Açıklama |
|--------|------------|
| T         |  `SafeInt` Yerine gelen bir insa veya Boolean parametresi türü. |
| E         |  Hata işleme ilkesini tanımlayan numaralandırılmış bir veri türü. |
| U         |  Sekonder operand için birsoner veya Boolean parametresi türü. |

| Parametre  |  Açıklama |
|---------|-----------------|
| *Rhs*      |  [içinde] Birkaç tek başına işlevde işlecinin sağ tarafındaki değeri temsil eden bir giriş parametresi. |
| *Ⅰ*        |  [içinde] Birkaç tek başına işlevde işlecinin sağ tarafındaki değeri temsil eden bir giriş parametresi. |
| *Bit*     |  [içinde] Birkaç tek başına işlevde işlecinin sağ tarafındaki değeri temsil eden bir giriş parametresi. |

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

| Adı                          |  Açıklama |
|---------------------------|--------------------|
| [SafeInt::SafeInt](#safeint)  |  Varsayılan oluşturucu. |

### <a name="assignment-operators"></a>Atama İşleçleri

| Adı  |  Sözdizimi |
|----|---------|
| =     |  `template<typename U>`<br />`SafeInt<T,E>& operator= (const U& rhs)` |
| =     |  `SafeInt<T,E>& operator= (const T& rhs) throw()` |
| =     |  `template<typename U>`<br />`SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)` |
| =     |  `SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()` |

### <a name="casting-operators"></a>Atama İşleçleri

| Adı              |  Sözdizimi |
|------|---------------------------------|
| bool              |  `operator bool() throw()` |
| char              |  `operator char() const` |
| imzalı char       |  `operator signed char() const` |
| unsigned char     |  `operator unsigned char() const` |
| __int16           |  `operator __int16() const` |
| imzasız __int16  |  `operator unsigned __int16() const` |
| __int32           |  `operator __int32() const` |
| imzasız __int32  |  `operator unsigned __int32() const` |
| long              |  `operator long() const` |
| imzasız long     |  `operator unsigned long() const` |
| __int64           |  `operator __int64() const` |
| imzasız __int64  |  `operator unsigned __int64() const` |
| wchar_t           |  `operator wchar_t() const` |

### <a name="comparison-operators"></a>Karşılaştırma İşleçleri

| Adı  |  Sözdizimi |
|----|----------------|
| \<     |  `template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()` |
| \<     |  `bool operator< (SafeInt<T,E> rhs) const throw()` |
| \>=    |  `template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()` |
| \>=    |  `Bool operator>= (SafeInt<T,E> rhs) const throw()` |
| \>     |  `template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()` |
| \>     |  `Bool operator> (SafeInt<T,E> rhs) const throw()` |
| \<=    |  `template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()` |
| \<=    |  `bool operator<= (SafeInt<T,E> rhs) const throw()` |
| ==    |  `template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()` |
| ==    |  `bool operator== (bool rhs) const throw()` |
| ==    |  `bool operator== (SafeInt<T,E> rhs) const throw()` |
| !=    |  `template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()` |
| !=    |  `bool operator!= (bool b) const throw()` |
| !=    |  `bool operator!= (SafeInt<T,E> rhs) const throw()` |

### <a name="arithmetic-operators"></a>Aritmetik İşleçler

| Adı  |  Sözdizimi |
|----|--------------|
| +     |  `const SafeInt<T,E>& operator+ () const throw()` |
| -     |  `SafeInt<T,E> operator- () const` |
| ++    |  `SafeInt<T,E>& operator++ ()` |
| --    |  `SafeInt<T,E>& operator-- ()` |
| %     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const` |
| %     |  `SafeInt<T,E> operator% (SafeInt<T,E> rhs) const` |
| %=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)` |
| %=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)` |
| \*     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const` |
| \*     |  `SafeInt<T,E> operator* (SafeInt<T,E> rhs) const` |
| \*=    |  `SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)` |
| \*=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)` |
| \*=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)` |
| /     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const` |
| /     |  `SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const` |
| /=    |  `SafeInt<T,E>& operator/= (SafeInt<T,E> i)` |
| /=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)` |
| /=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)` |
| +     |  `SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const` |
| +     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const` |
| +=    |  `SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)` |
| +=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)` |
| +=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)` |
| -     |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const` |
| -     |  `SafeInt<T,E> operator- (SafeInt<T,E> rhs) const` |
| -=    |  `SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)` |
| -=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)` |
| -=    |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)` |

### <a name="logical-operators"></a>Mantıksal İşleçler

| Adı     |  Sözdizimi |
|------|--------------|
| !        |  `bool operator !() const throw()` |
| ~        |  `SafeInt<T,E> operator~ () const throw()` |
| \<\<       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()` |
| \<\<       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()` |
| \<\<=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()` |
| \<\<=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()` |
| \>\>       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()` |
| \>\>       |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()` |
| \>\>=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()` |
| \>\>=      |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()` |
| &        |  `SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()` |
| &        |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()` |
| &=       |  `SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()` |
| &=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()` |
| &=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()` |
| ^        |  `SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()` |
| ^        |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()` |
| ^=       |  `SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()` |
| ^=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()` |
| ^=       |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()` |
| &#124;   |  `SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()` |
| &#124;   |  `template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()` |
| &#124;=  |  `SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()` |
| &#124;=  |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()` |
| &#124;=  |  `template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()` |

## <a name="remarks"></a>Açıklamalar

Sınıf `SafeInt` matematiksel işlemlerde birandak taşmakarşı korur. Örneğin, iki adet 8 bit tamsayı eklemeyi düşünün: birinin değeri 200, ikincisinin değeri 100'tür. Doğru matematiksel işlem 200 + 100 = 300 olacaktır. Ancak, 8-bit tümsekli sınır nedeniyle, üst bit kaybolur ve derleyici sonuç olarak 44 (300 - 2<sup>8)</sup>döndürecektir. Bu matematiksel denkleme bağlı herhangi bir işlem beklenmeyen davranışlar oluşturur.

Sınıf, `SafeInt` aritmetik bir taşmanın oluşup oluşmadığını veya kodun sıfıra bölmeye çalışıp çalışmayacağını denetler. Her iki durumda da, sınıf olası sorun programı uyarmak için hata işleyicisi çağırır.

Bu sınıf, nesne oldukları `SafeInt` sürece iki farklı tamsayı türünü karşılaştırmanızı da sağlar. Genellikle, bir karşılaştırma yaptığınızda, önce sayıları aynı türde dönüştürmeniz gerekir. Bir numarayı başka bir türe dökmek genellikle veri kaybı olmadığından emin olmak için denetimler gerektirir.

Bu konudaki Operatörler tablosunda `SafeInt` sınıf tarafından desteklenen matematiksel ve karşılaştırma işleçleri listelenir. Çoğu matematiksel işleç türünde `SafeInt` `T`bir nesne döndürer.

A `SafeInt` ve integral türü arasındaki karşılaştırma işlemleri her iki yönde de gerçekleştirilebilir. Örneğin, her `SafeInt<int>(x) < y` `y> SafeInt<int>(x)` ikisi de geçerli dir ve aynı sonucu döndürecektir.

Birçok ikili işleç iki `SafeInt` farklı türde kullanmayı desteklemez. Bunun bir örneği `&` işleçtir. `SafeInt<T, E> & int`desteklenir, ancak `SafeInt<T, E> & SafeInt<U, E>` desteklenmez. İkinci örnekte, derleyici ne tür bir parametrenin döndürülacağını bilmez. Bu sorunun bir çözümü, ikinci parametreyi taban türüne geri atmaktır. Aynı parametreler kullanılarak, bu yapılabilir. `SafeInt<T, E> & (U)SafeInt<U, E>`

> [!NOTE]
> Bitakıllıca işlemler için iki farklı parametre aynı boyutta olmalıdır. Boyutlar farklıysa, derleyici bir [ASSERT](../mfc/reference/diagnostic-services.md#assert) özel durum oluşturur. Bu işlemin sonuçlarının doğru olduğu garanti edilemez. Bu sorunu gidermek için, daha büyük parametreyle aynı boyutta olana kadar daha küçük parametreyi atın.

Shift işleçleri için, şablon türü için var olandan daha fazla bit kaydırma bir Assert özel durum atacaktır. Bu sürüm modunda hiçbir etkisi olmayacaktır. İade türü orijinal türle aynı olduğundan, shift işleçleri için iki tür SafeInt parametresini karıştırmak mümkündür. İşleticinin sağ tarafındaki sayı yalnızca kaydırılabilen bit sayısını gösterir.

Bir SafeInt nesnesi ile mantıksal bir karşılaştırma yaptığınızda, karşılaştırma kesinlikle aritmetiktir. Örneğin, şu ifadeleri göz önünde bulundurun:

- `SafeInt<uint>((uint)~0) > -1`

- `((uint)~0) > -1`

İlk deyim **doğru**giderir, ancak ikinci deyim `false`. 0 bitwise olumsuzlama 0xFFFFFFFFFFF olduğunu. İkinci ifadede, varsayılan karşılaştırma işleci 0xFFFFFFFF ile 0xFFFFFFFFile karşılaştırır ve bunları eşit olarak kabul eder. `SafeInt` Sınıfın karşılaştırma işleci ikinci parametrenin negatif, ilk parametrenin ise imzasız olduğunu fark eder. Bu nedenle, bit gösterimi `SafeInt` aynı olsa da, mantıksal işleç imzasız tamsayı -1'den büyük olduğunu fark eder.

`SafeInt` Sınıfı `?:` üçüncül işleçle birlikte kullanırken dikkatli olun. Aşağıdaki kod satırını düşünün.

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : -1;
```

Derleyici bunu şuna dönüştürür:

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);
```

Ise, `flag` derleyici -1 değerini atamak yerine bir özel durum `x` `false` Bu nedenle, bu davranışı önlemek için, kullanılacak doğru kod aşağıdaki satırdır.

```cpp
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;
```

`T`ve `U` boolean türü, karakter türü veya tamsayı türü atanabilir. Tümsek türleri imzalanabilir veya imzalanmamış olabilir ve 8 bitten 64 bit'e kadar herhangi bir boyut.

> [!NOTE]
> `SafeInt` Sınıf her türlü tamsayı kabul etse de, imzasız türlerle daha verimli bir şekilde gerçekleştirir.

`E``SafeInt` kullanan hata işleme mekanizmasıdır. SafeInt kitaplığı ile iki hata işleme mekanizması sağlanır. Varsayılan `SafeIntErrorPolicy_SafeIntException`ilke, bir hata oluştuğunda [SafeIntException Class](../safeint/safeintexception-class.md) özel durum atar. Diğer ilke, `SafeIntErrorPolicy_InvalidParameter`bir hata oluşursa programı durdurur.

Hata ilkesini özelleştirmek için iki seçenek vardır. İlk seçenek, bir `E` `SafeInt`. oluştururken parametreyi ayarlamaktır. Hata işleme ilkesini yalnızca bir `SafeInt`kişi için değiştirmek istediğinizde bu seçeneği kullanın. Diğer seçenek, `SafeInt` kitaplığı eklemeden önce _SAFEINT_DEFAULT_ERROR_POLICY özelleştirilmiş hata işleme sınıfınız olarak tanımlamaktır. Kodunuzdaki sınıfın tüm örnekleri için varsayılan hata işleme ilkesini `SafeInt` değiştirmek istediğinizde bu seçeneği kullanın.

> [!NOTE]
> SafeInt kitaplığından gelen hataları işleyen özelleştirilmiş bir sınıf denetimi hata işleyicisi olarak adlandırılan koda döndürmemelidir. Hata işleyicisi çağrıldıktan `SafeInt` sonra, işlemin sonucu güvenilemez.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SafeInt`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** safeint.h

**Ad alanı:** msl::yardımcı programlar

## <a name="safeintsafeint"></a><a name="safeint"></a>SafeInt::SafeInt

Bir `SafeInt` nesne inşa eder.

```cpp
SafeInt() throw

SafeInt (
   const T& i
) throw ()

SafeInt (
   bool b
) throw ()

template <typename U>
SafeInt (
   const SafeInt <U, E>& u
)

I template <typename U>
SafeInt (
   const U& i
)
```

### <a name="parameters"></a>Parametreler

*Ⅰ*<br/>
[içinde] Yeni `SafeInt` nesnenin değeri. Bu, oluşturucuya bağlı olarak T veya U tipi bir parametre olmalıdır.

*B*<br/>
[içinde] Yeni `SafeInt` nesne için Boolean değeri.

*U*<br/>
[içinde] A `SafeInt` tipi U. Yeni `SafeInt` nesne *u*ile aynı değere sahip olacak, ancak T türünde olacaktır.

U' da depolanan veri `SafeInt`türü. Bu bir Boolean, karakter veya tamsayı türü olabilir. Bir sonda türüyse, imzalanabilir veya imzalanmamış olabilir ve 8 ile 64 bit arasında olabilir.

### <a name="remarks"></a>Açıklamalar

Oluşturucu, *i* veya *u*için giriş parametresi, boolean, karakter veya tamsayı türü olmalıdır. Başka bir parametre türüyse, `SafeInt` sınıf geçersiz bir giriş parametresini belirtmek için [static_assert](../cpp/static-assert.md) çağırır.

Şablon türünü `U` kullanan oluşturucular giriş parametresini otomatik olarak . `T` Sınıf, `SafeInt` veri kaybı olmadan verileri dönüştürür. Verileri veri kaybı olmadan `E` türe `T` dönüştüremiyorsa hata işleyicisine rapor ver.

Boolean parametresinden bir a `SafeInt` oluşturursanız, değeri hemen başlatmanız gerekir. Kodu `SafeInt<bool> sb;`kullanarak `SafeInt` bir oluşturamazsınız. Bu bir derleme hatası oluşturur.
