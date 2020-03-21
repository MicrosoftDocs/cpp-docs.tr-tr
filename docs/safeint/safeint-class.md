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
ms.openlocfilehash: c69dc7ed5e34d98d5acff8f2bc28c34761bd31c6
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076815"
---
# <a name="safeint-class"></a>SafeInt Sınıfı

Tamsayı taşmasını önlemeye yardımcı olmak için tamsayı temel öğelerini genişletir ve farklı tamsayılar türlerini karşılaştırmanızı sağlar.

> [!NOTE]
> Bu kitaplığın en son sürümü [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt)konumunda bulunur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>
class SafeInt;
```

### <a name="parameters"></a>Parametreler

| Şablon  |  Açıklama |
|--------|------------|
| T         |  `SafeInt` değiştiren tamsayı veya Boolean parametresinin türü. |
| E         |  Hata işleme ilkesini tanımlayan bir numaralandırılmış veri türü. |
| U         |  İkincil işlenenin tamsayı veya Boole parametresinin türü. |

| Parametre  |  Açıklama |
|---------|-----------------|
| *sağ taraftan*      |  'ndaki Birkaç bağımsız işlevlerde işlecin sağ tarafındaki değeri temsil eden bir giriş parametresi. |
| *kaydedemiyorum*        |  'ndaki Birkaç bağımsız işlevlerde işlecin sağ tarafındaki değeri temsil eden bir giriş parametresi. |
| *bitlik*     |  'ndaki Birkaç bağımsız işlevlerde işlecin sağ tarafındaki değeri temsil eden bir giriş parametresi. |

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

| Adı                          |  Açıklama |
|---------------------------|--------------------|
| [SafeInt::SafeInt](#safeint)  |  Varsayılan Oluşturucu. |

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

`SafeInt` sınıfı, matematik işlemlerinde tamsayı taşmasına karşı koruma sağlar. Örneğin, iki 8 bitlik tamsayılar eklemeyi düşünün: biri 200 değerine sahiptir ve ikincisi 100 değerine sahiptir. Doğru matematiksel işlem 200 + 100 = 300 olur. Ancak, 8 bit tamsayı sınırı nedeniyle, üst bit kaybedilir ve derleyici sonuç olarak 44 (300-2<sup>8</sup>) döndürür. Bu Matematik denklemine bağlı olan tüm işlemler beklenmeyen davranışlar oluşturur.

`SafeInt` sınıfı, aritmetik bir taşın mi oluştuğunu yoksa kodun sıfıra bölmeye mi çalışacağını denetler. Her iki durumda da, sınıf olası sorunun programını uyarmak için hata işleyicisini çağırır.

Bu sınıf, `SafeInt` nesne oldukları sürece iki farklı tür tamsayıları karşılaştırmanıza de olanak tanır. Genellikle, bir karşılaştırma gerçekleştirdiğinizde, önce sayıları aynı tür olacak şekilde dönüştürmeniz gerekir. Bir sayıyı başka bir türe atama genellikle veri kaybı olmadığından emin olmak için denetimler gerektirir.

Bu konudaki Işleçler tablosunda, `SafeInt` sınıfı tarafından desteklenen matematik ve karşılaştırma işleçleri listelenmiştir. Çoğu matematik işleci `T`türünde bir `SafeInt` nesnesi döndürür.

Bir `SafeInt` ve integral türü arasındaki karşılaştırma işlemleri her iki yönde de gerçekleştirilebilir. Örneğin, `SafeInt<int>(x) < y` ve `y> SafeInt<int>(x)` her ikisi de geçerli olur ve aynı sonucu döndürür.

Birçok ikili işleç iki farklı `SafeInt` türünü kullanmayı desteklemez. Bu bir örnek `&` işleçtir. `SafeInt<T, E> & int` desteklenir, ancak `SafeInt<T, E> & SafeInt<U, E>` değildir. İkinci örnekte, derleyici döndürülecek parametre türünü bilmez. Bu soruna yönelik bir çözüm ikinci parametreyi temel türe dönüştürmek olur. Aynı parametreleri kullanarak bu `SafeInt<T, E> & (U)SafeInt<U, E>`gerçekleştirilebilir.

> [!NOTE]
> Bit düzeyinde işlemler için, iki farklı parametre aynı boyutta olmalıdır. Boyutlar farklıysa, derleyici bir [onaylama](../mfc/reference/diagnostic-services.md#assert) özel durumu oluşturur. Bu işlemin sonuçlarının doğru olması garanti edilemez. Bu sorunu çözmek için, daha küçük parametreyi, daha büyük parametreyle aynı boyuta gelene kadar dönüştürün.

Kaydırma işleçleri için, şablon türü için varolandan daha fazla bit kaydırma bir onaylama özel durumu oluşturur. Bu, yayın modunda hiçbir etkiye sahip olmayacaktır. İki tür SafeInt parametresi, dönüş türü özgün türle aynı olduğundan, kaydırma işleçleri için mümkündür. İşlecin sağ tarafındaki sayı yalnızca kaydırılacak bit sayısını gösterir.

SafeInt nesnesiyle mantıksal bir karşılaştırma gerçekleştirdiğinizde, karşılaştırma kesin olarak aritmetik olur. Örneğin, şu ifadeleri göz önünde bulundurun:

- `SafeInt<uint>((uint)~0) > -1`

- `((uint)~0) > -1`

İlk ifade **true**olarak çözümlenir, ancak ikinci ifade `false`olarak çözümlenir. 0 bit düzeyinde Olumsuzlaştırma değeri 0xFFFFFFFF ' dir. İkinci ifadede, varsayılan karşılaştırma işleci 0xFFFFFFFF ile 0xFFFFFFFF arasında karşılaştırır ve bunların eşit olduğunu varsayar. `SafeInt` sınıfı için karşılaştırma işleci ikinci parametrenin negatiftir, ancak ilk parametre işaretsiz olur. Bu nedenle, bit temsili özdeş olsa da, `SafeInt` mantıksal işleci işaretsiz tamsayının-1 ' den büyük olduğunu farkettir.

`SafeInt` sınıfını `?:` Üçlü işleçle birlikte kullanırken dikkatli olun. Aşağıdaki kod satırını göz önünde bulundurun.

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : -1;
```

Derleyici bunu buna dönüştürür:

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);
```

`flag` `false`ise, derleyici-1 değerini `x`atamak yerine bir özel durum atar. Bu nedenle, bu davranışı önlemek için, kullanılacak doğru kod aşağıdaki satırdır.

```cpp
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;
```

`T` ve `U` bir Boole türü, karakter türü veya tamsayı türü atanabilir. Tamsayı türleri imzalanabilir veya imzasız ve 8 bitten 64 bite kadar herhangi bir boyutta olabilir.

> [!NOTE]
> `SafeInt` sınıfı herhangi bir tür tamsayıyı kabul etse de, imzasız türler ile daha verimli bir şekilde çalışır.

`E`, `SafeInt` tarafından kullanılan hata işleme mekanizmasıdır. SafeInt Kitaplığı ile iki hata işleme mekanizması sağlanır. Varsayılan ilke, bir hata oluştuğunda [Safeintexception sınıfı](../safeint/safeintexception-class.md) özel durumu oluşturan `SafeIntErrorPolicy_SafeIntException`. Diğer ilke, bir hata oluşursa programı durduran `SafeIntErrorPolicy_InvalidParameter`.

Hata ilkesini özelleştirmek için iki seçenek vardır. İlk seçenek, bir `SafeInt`oluşturduğunuzda parametre `E` ayarlandır. Yalnızca bir `SafeInt`için hata işleme ilkesini değiştirmek istediğinizde bu seçeneği kullanın. Diğer seçenek, `SafeInt` kitaplığı eklemeden önce özelleştirilmiş hata işleme sınıfınız olarak _SAFEINT_DEFAULT_ERROR_POLICY tanımlamaktır. Kodunuzda `SafeInt` sınıfının tüm örnekleri için varsayılan hata işleme ilkesini değiştirmek istediğinizde bu seçeneği kullanın.

> [!NOTE]
> SafeInt kitaplığından hataları işleyen özelleştirilmiş bir sınıf, denetimi hata işleyicisini çağıran koda döndürmemelidir. Hata işleyicisi çağrıldıktan sonra `SafeInt` işleminin sonucu güvenilir olamaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SafeInt`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** SafeInt. h

**Ad alanı:** MSL:: Utilities

## <a name="safeintsafeint"></a><a name="safeint"></a>SafeInt:: SafeInt

`SafeInt` nesnesi oluşturur.

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

*kaydedemiyorum*<br/>
'ndaki Yeni `SafeInt` nesnesinin değeri. Oluşturucuya bağlı olarak bu, T veya U türünde bir parametre olmalıdır.

*kenarı*<br/>
'ndaki Yeni `SafeInt` nesnesinin Boolean değeri.

*larınız*<br/>
'ndaki U türünde bir `SafeInt`. Yeni `SafeInt` nesnesi *u*ile aynı değere sahip olacaktır, ancak t türünde olacaktır.

U `SafeInt`depolanan veri türü. Bu bir Boolean, karakter ya da tamsayı türü olabilir. Bir tamsayı türü ise, imzalanmış veya imzasız olabilir ve 8 ile 64 bit arasında olabilir.

### <a name="remarks"></a>Açıklamalar

*I* veya *u*oluşturucusunun giriş parametresi bir Boolean, karakter veya tamsayı türü olmalıdır. Başka bir parametre türü ise `SafeInt` sınıfı, geçersiz bir giriş parametresini göstermek için [static_assert](../cpp/static-assert.md) çağırır.

`U` şablon türünü kullanan oluşturucular, giriş parametresini `T`tarafından belirtilen türe otomatik olarak dönüştürür. `SafeInt` sınıfı verileri hiçbir kayıp olmadan dönüştürür. Verileri veri kaybı olmadan `T` türüne dönüştüremediğinden hata işleyicisine rapor `E`.

Boolean parametresinden bir `SafeInt` oluşturursanız, değeri hemen başlatmalısınız. Kod `SafeInt<bool> sb;`kullanarak `SafeInt` oluşturamazsınız. Bu, bir derleme hatası oluşturur.
