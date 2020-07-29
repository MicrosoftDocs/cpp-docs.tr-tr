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
ms.openlocfilehash: 97d81401cfd01d6d39457a9d63c39bc25901128e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219358"
---
# <a name="safeint-class"></a>SafeInt Sınıfı

Tamsayı taşmasını önlemeye yardımcı olmak için tamsayı temel öğelerini genişletir ve farklı tamsayılar türlerini karşılaştırmanızı sağlar.

> [!NOTE]
> SafeInt Kitaplığı 'nın en son sürümü konumunda bulunur [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) . SafeInt kitaplığını kullanmak için depoyu kopyalayın ve`#include "SafeInt.hpp"`

## <a name="syntax"></a>Söz dizimi

```cpp
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>
class SafeInt;
```

### <a name="parameters"></a>Parametreler

| Şablon  |  Açıklama |
|--------|------------|
| T         |  Değiştiren tamsayı veya Boole parametresinin türü `SafeInt` . |
| E         |  Hata işleme ilkesini tanımlayan bir numaralandırılmış veri türü. |
| U         |  İkincil işlenenin tamsayı veya Boole parametresinin türü. |

| Parametre  |  Açıklama |
|---------|-----------------|
| *sağ taraftan*      |  'ndaki Birkaç bağımsız işlevlerde işlecin sağ tarafındaki değeri temsil eden bir giriş parametresi. |
| *i*        |  'ndaki Birkaç bağımsız işlevlerde işlecin sağ tarafındaki değeri temsil eden bir giriş parametresi. |
| *bitlik*     |  'ndaki Birkaç bağımsız işlevlerde işlecin sağ tarafındaki değeri temsil eden bir giriş parametresi. |

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

| Ad                          |  Açıklama |
|---------------------------|--------------------|
| [SafeInt::SafeInt](#safeint)  |  Varsayılan Oluşturucu. |

### <a name="assignment-operators"></a>Atama İşleçleri

| Ad  |  Sözdizimi |
|----|---------|
| =     |  `template<typename U>`<br />`SafeInt<T,E>& operator= (const U& rhs)` |
| =     |  `SafeInt<T,E>& operator= (const T& rhs) throw()` |
| =     |  `template<typename U>`<br />`SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)` |
| =     |  `SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()` |

### <a name="casting-operators"></a>Atama İşleçleri

| Ad              |  Sözdizimi |
|------|---------------------------------|
| bool              |  `operator bool() throw()` |
| char              |  `operator char() const` |
| işaretli karakter       |  `operator signed char() const` |
| unsigned char     |  `operator unsigned char() const` |
| __int16           |  `operator __int16() const` |
| İmzasız __int16  |  `operator unsigned __int16() const` |
| __int32           |  `operator __int32() const` |
| imzasız __int32  |  `operator unsigned __int32() const` |
| long              |  `operator long() const` |
| imzasız long     |  `operator unsigned long() const` |
| __int64           |  `operator __int64() const` |
| imzasız __int64  |  `operator unsigned __int64() const` |
| wchar_t           |  `operator wchar_t() const` |

### <a name="comparison-operators"></a>Karşılaştırma İşleçleri

| Ad  |  Sözdizimi |
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

| Ad  |  Sözdizimi |
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

| Ad     |  Sözdizimi |
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

`SafeInt`Sınıfı matematik işlemlerinde tamsayı taşmasına karşı koruma sağlar. Örneğin, iki 8 bitlik tamsayılar eklemeyi düşünün: biri 200 değerine sahiptir ve ikincisi 100 değerine sahiptir. Doğru matematiksel işlem 200 + 100 = 300 olur. Ancak, 8 bit tamsayı sınırı nedeniyle, üst bit kaybedilir ve derleyici sonuç olarak 44 (300-2<sup>8</sup>) döndürür. Bu Matematik denklemine bağlı olan tüm işlemler beklenmeyen davranışlar oluşturur.

`SafeInt`Sınıfı, aritmetik bir taşın mi oluştuğunu yoksa kodun sıfıra bölmeye mi çalışacağını denetler. Her iki durumda da, sınıf olası sorunun programını uyarmak için hata işleyicisini çağırır.

Bu sınıf aynı zamanda, nesneler oldukları sürece iki farklı türden tamsayıları karşılaştırmanıza imkan tanır `SafeInt` . Genellikle, bir karşılaştırma yaptığınızda, önce sayıları aynı tür olacak şekilde dönüştürmeniz gerekir. Bir sayıyı başka bir türe atama genellikle veri kaybı olmadığından emin olmak için denetimler gerektirir.

Bu konudaki operatörler tablosunda, sınıfının desteklediği matematik ve karşılaştırma işleçleri listelenmiştir `SafeInt` . Çoğu matematik işleci türünde bir `SafeInt` nesne döndürür `T` .

`SafeInt`Ve integral türü arasındaki karşılaştırma işlemleri her iki yönde de gerçekleştirilebilir. Örneğin, `SafeInt<int>(x) < y` ve `y> SafeInt<int>(x)` geçerli olur ve aynı sonucu döndürür.

Birçok ikili işleç iki farklı tür kullanmayı desteklemez `SafeInt` . Bu bir örneği `&` işleçtir. `SafeInt<T, E> & int`desteklenir, ancak `SafeInt<T, E> & SafeInt<U, E>` değil. İkinci örnekte, derleyici döndürülecek parametre türünü bilmez. Bu soruna yönelik bir çözüm ikinci parametreyi temel türe dönüştürmek olur. Aynı parametreleri kullanarak bu, ile yapılabilir `SafeInt<T, E> & (U)SafeInt<U, E>` .

> [!NOTE]
> Bit düzeyinde işlemler için, iki farklı parametre aynı boyutta olmalıdır. Boyutlar farklıysa, derleyici bir [onaylama](../mfc/reference/diagnostic-services.md#assert) özel durumu oluşturur. Bu işlemin sonuçlarının doğru olması garanti edilemez. Bu sorunu çözmek için, daha küçük parametreyi, daha büyük parametreyle aynı boyuta gelene kadar dönüştürün.

Kaydırma işleçleri için, şablon türü için varolandan daha fazla bit kaydırma bir onaylama özel durumu oluşturur. Bu, yayın modunda hiçbir etkiye sahip olmayacaktır. İki tür SafeInt parametresi, dönüş türü özgün türle aynı olduğundan, kaydırma işleçleri için mümkündür. İşlecin sağ tarafındaki sayı yalnızca kaydırılacak bit sayısını gösterir.

SafeInt nesnesiyle mantıksal bir karşılaştırma yaptığınızda karşılaştırma kesin olarak aritmetik olur. Örneğin, şu ifadeleri göz önünde bulundurun:

- `SafeInt<uint>((uint)~0) > -1`

- `((uint)~0) > -1`

İlk ifade olarak çözümlenir **`true`** , ancak ikinci ifade olarak çözümlenir **`false`** . 0 bit düzeyinde Olumsuzlaştırma değeri 0xFFFFFFFF ' dir. İkinci ifadede, varsayılan karşılaştırma işleci 0xFFFFFFFF ile 0xFFFFFFFF arasında karşılaştırır ve bunların eşit olduğunu varsayar. Sınıf için karşılaştırma işleci `SafeInt` ikinci parametrenin negatif olduğunu, ancak ilk parametre imzasız olduğunu gösterir. Bu nedenle, bit temsili özdeş olsa da, `SafeInt` mantıksal işleç işaretsiz tamsayının-1 ' den büyük olduğunu farkettir.

`SafeInt`Sınıfını Üçlü işleçle birlikte kullanırken dikkatli olun `?:` . Aşağıdaki kod satırını göz önünde bulundurun.

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : -1;
```

Derleyici bunu buna dönüştürür:

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);
```

`flag`İse **`false`** , derleyici-1 değerini olarak atamak yerine bir özel durum atar `x` . Bu nedenle, bu davranışı önlemek için, kullanılacak doğru kod aşağıdaki satırdır.

```cpp
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;
```

`T`ve `U` bir Boole türü, karakter türü veya tamsayı türü atanabilir. Tamsayı türleri imzalanabilir veya imzasız ve 8 bitten 64 bite kadar herhangi bir boyutta olabilir.

> [!NOTE]
> `SafeInt`Sınıfı herhangi bir tür tamsayıyı kabul etse de, imzasız türler ile daha verimli bir şekilde çalışır.

`E`, kullanan hata işleme mekanizmasıdır `SafeInt` . SafeInt Kitaplığı ile iki hata işleme mekanizması sağlanır. Varsayılan ilke `SafeIntErrorPolicy_SafeIntException` , bir hata oluştuğunda [Safeintexception sınıfı](safeintexception-class.md) özel durumu oluşturur. Diğer ilke, `SafeIntErrorPolicy_InvalidParameter` bir hata oluşursa programı durduran olur.

Hata ilkesini özelleştirmek için iki seçenek vardır. İlk seçenek, oluştururken parametresini ayarlamak olur `E` `SafeInt` . Yalnızca bir hata işleme ilkesini değiştirmek istediğinizde bu seçeneği kullanın `SafeInt` . Diğer seçenek, kitaplığı eklemeden önce özelleştirilmiş hata işleme sınıfınız olarak _SAFEINT_DEFAULT_ERROR_POLICY tanımlamaktır `SafeInt` . Kodunuzda sınıfın tüm örnekleri için varsayılan hata işleme ilkesini değiştirmek istediğinizde bu seçeneği kullanın `SafeInt` .

> [!NOTE]
> SafeInt kitaplığından hataları işleyen özelleştirilmiş bir sınıf, denetimi hata işleyicisini çağıran koda döndürmemelidir. Hata işleyicisi çağrıldıktan sonra `SafeInt` işlemin sonucuna güvenilemez.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SafeInt`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** SafeInt. hpp
> [!NOTE]
> Bu kitaplığın en son sürümü konumunda bulunur [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) . Kitaplığı kopyalayın ve SafeInt. hpp ' i kullanarak SafeInt kitaplığını kullanın.
> Bu GitHub deposunun SafeInt. h> <için tercih edin. Bu, az sayıda hata düzeltmesi içeren <SafeInt. h> modern bir sürümüdür, C++ ' ın modern özelliklerini kullanarak daha verimli bir koda neden olur ve GCC, Clang ya da Intel derleyicileri kullanan herhangi bir platforma taşınabilir.

### <a name="example"></a>Örnek

```c
#include "SafeInt.hpp" // set path to your clone of the SafeInt GitHub repo (https://github.com/dcleblanc/SafeInt)

int main()
{
    int divisor = 3;
    int dividend = 6;
    int result;

    bool success = SafeDivide(dividend, divisor, result); // result = 2
    success = SafeDivide(dividend, 0, result); // expect fail. result isn't modified.
}
```

**Ad alanı:** yok

## <a name="safeintsafeint"></a><a name="safeint"></a>SafeInt:: SafeInt

Bir `SafeInt` nesnesi oluşturur.

```cpp
SafeInt() throw

SafeInt (const T& i) throw ()

SafeInt (bool b) throw ()

template <typename U>
SafeInt (const SafeInt <U, E>& u)

I template <typename U>
SafeInt (const U& i)
```

### <a name="parameters"></a>Parametreler

`i`<br/>
'ndaki Yeni `SafeInt` nesnenin değeri. Oluşturucuya bağlı olarak bu, T veya U türünde bir parametre olmalıdır.

`b`<br/>
'ndaki Yeni nesnenin Boole değeri `SafeInt` .

`u`<br/>
'ndaki `SafeInt`U türünde bir. Yeni `SafeInt` nesne *u*ile aynı değere sahip olacaktır, ancak T türünde olacaktır.

`U`İçinde depolanan verilerin türü `SafeInt` . Bu bir Boolean, karakter ya da tamsayı türü olabilir. Bir tamsayı türü ise, imzalanmış veya imzasız olabilir ve 8 ile 64 bit arasında olabilir.

### <a name="remarks"></a>Açıklamalar

*I* veya *u*oluşturucusunun giriş parametresi bir Boolean, karakter veya tamsayı türü olmalıdır. Başka bir parametre türü ise, `SafeInt` sınıfı geçersiz bir giriş parametresini göstermek için [static_assert](../cpp/static-assert.md) çağırır.

Şablon türünü kullanan oluşturucular, `U` giriş parametresini otomatik olarak belirtilen türe dönüştürür `T` . `SafeInt`Sınıfı veri kaybı olmadan verileri dönüştürür. Verileri `E` veri kaybı olmadan türüne dönüştüremediğinden hata işleyicisine rapor bildirir `T` .

Bir `SafeInt` Boolean parametresinden bir oluşturursanız, değeri hemen başlatmalısınız. Kodu kullanarak bir oluşturamazsınız `SafeInt` `SafeInt<bool> sb;` . Bu, bir derleme hatası oluşturur.
