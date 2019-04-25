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
ms.openlocfilehash: 1fc7ec438d83be1a92d8fa9d699f4172aba842e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179393"
---
# <a name="safeint-class"></a>SafeInt Sınıfı

Tamsayı taşması önlemek için tamsayı temelleri genişletir ve farklı tamsayı türleri karşılaştırmanıza olanak tanır.

> [!NOTE] 
> Bu kitaplık en son sürümünü şu konumdadır [ https://github.com/dcleblanc/SafeInt ](https://github.com/dcleblanc/SafeInt).

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>
class SafeInt;
```

### <a name="parameters"></a>Parametreler

| Şablon  |  Açıklama |
|--------|------------|
| T         |  Tamsayı veya Boole parametresi türü, `SafeInt` değiştirir. |
| E         |  İlke işleme hatası tanımlayan numaralandırılmış veri türü. |
| U         |  Tamsayı veya Boole parametresi için ikinci işlenenin türü. |

| Parametre  |  Açıklama |
|---------|-----------------|
| *Sol*      |  [in] Birden fazla tek başına işlevlerde işlecinin sağ tarafında değerini temsil eden giriş parametresi. |
| *i*        |  [in] Birden fazla tek başına işlevlerde işlecinin sağ tarafında değerini temsil eden giriş parametresi. |
| *BITS*     |  [in] Birden fazla tek başına işlevlerde işlecinin sağ tarafında değerini temsil eden giriş parametresi. |

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
| İmzalı char       |  `operator signed char() const` |
| unsigned char     |  `operator unsigned char() const` |
| __int16           |  `operator __int16() const` |
| İmzasız __int16  |  `operator unsigned __int16() const` |
| __int32           |  `operator __int32() const` |
| İmzasız __int32 türünün int  |  `operator unsigned __int32() const` |
| long              |  `operator long() const` |
| imzasız long     |  `operator unsigned long() const` |
| __int64           |  `operator __int64() const` |
| imzalanmamış __int64  |  `operator unsigned __int64() const` |
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

`SafeInt` Matematiksel işlemler tamsayı taşması karşı sınıfı korur. Örneğin, iki 8 bit tam sayı eklemeyi göz önünde bulundurun: 200 değeri varsa ve ikinci değeri 100. Doğru matematiksel işlem 200 + 100 = 300 olacaktır. Ancak, 8 bit tam sayı sınırı nedeniyle üst bit kaybolur ve derleyici 44 döndürür (300-2<sup>8</sup>) sonucu. Bu matematiksel denklemi temel bağlı herhangi bir işlemi beklenmeyen davranışlara neden olur.

`SafeInt` Sınıfı olup bir aritmetik taşma oluşur veya kod olup olmadığını sıfıra bölünme dener denetler. Her iki durumda da sınıfı olası bir sorundan program uyarmak için hata işleyicisini çağırır.

Bu sınıf ayrıca, iki farklı tamsayı türleri oldukları sürece karşılaştırmanızı sağlar `SafeInt` nesneleri. Genellikle, bir karşılaştırma gerçekleştirirken aynı türde olacak şekilde sayıları önce dönüştürmeniz gerekir. Başka bir tür için bir sayı genellikle atama, veri kaybı olmadan olduğundan emin olmak için kontroller gerektirir.

Bu konudaki işleçleri tabloda tarafından desteklenen matematiksel ve Karşılaştırma işleçleri listelenir `SafeInt` sınıfı. En çok matematik işleçleri dönüş bir `SafeInt` türündeki nesne `T`.

Karşılaştırma işlemleri arasında bir `SafeInt` ve integral türünde herhangi bir yönde gerçekleştirilebilir. Örneğin, her ikisi de `SafeInt<int>(x) < y` ve `y> SafeInt<int>(x)` geçerli ve aynı sonucu döndürür.

Çoğu ikili işleç iki farklı kullanarak desteklemeyen `SafeInt` türleri. Bunun bir örneği `&` işleci. `SafeInt<T, E> & int` desteklenir, ancak `SafeInt<T, E> & SafeInt<U, E>` değil. İkinci örnekte, derleyici dönüş parametresinin türü bilmez. Bu soruna bir çözüm için ikinci parametre geri temel tür cast sağlamaktır. Aynı parametreleri kullanarak, bu ile yapılabilir `SafeInt<T, E> & (U)SafeInt<U, E>`.

> [!NOTE]
> Bit düzeyinde işlemler için iki farklı parametreler aynı boyutta olmalıdır. Boyutları farklı ise, derleyici verir bir [ASSERT](../mfc/reference/diagnostic-services.md#assert) özel durum. Bu işlemin sonuçlarının doğru olmasını garanti edilemez. Bu sorunu çözmek için daha büyük bir parametre olarak aynı boyutta olan kadar küçük parametresi dönüştürün.

Kaydırma işleçleri için şablon türü var olandan daha fazla bit kaydırma bir onay özel durum oluşturur. Bu yayın modunda hiçbir etkisi olmayacaktır. SafeInt parametrelerinin iki türlerini karıştırmak dönüş türü, özgün türü ile aynı olduğundan kaydırma işleçleri için mümkündür. İşlecin sağ tarafındaki sayısı yalnızca kaydırılacak bit sayısını gösterir.

SafeInt nesnesiyle mantıksal bir karşılaştırma gerçekleştirirken, tamamen aritmetik bir karşılaştırmadır. Örneğin, bu deyimler göz önünde bulundurun:

- `SafeInt<uint>((uint)~0) > -1`

- `((uint)~0) > -1`

İlk deyim çözümler **true**, ancak ikinci deyim çözümler `false`. Bitwise olumsuzlama 0 0xFFFFFFFF kullanılır. İkinci deyim, varsayılan karşılaştırma işleci için 0xFFFFFFFF 0xFFFFFFFF karşılaştırır ve bunları eşit olarak değerlendirir. Karşılaştırma işleci için `SafeInt` sınıfı, ikinci parametre ise ilk parametre imzalanmamış negatif olduğunu fark etti. Bu nedenle, bit gösterimi aynıdır ancak `SafeInt` mantıksal işleç, işaretsiz tamsayı -1'den daha büyük olduğunu fark etti.

Kullanırken dikkatli olun `SafeInt` ile birlikte sınıfı `?:` Üçlü işleci. Aşağıdaki kod satırını göz önünde bulundurun.

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : -1;
```

Derleyici için dönüştürür:

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);
```

Varsa `flag` olduğu `false`, derleyici için -1 değerini atamak yerine bir özel durum oluşturduğunda `x`. Bu nedenle bu davranışı önlemek için aşağıdaki satırı kullanmak için doğru kodu gereklidir.

```cpp
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;
```

`T` ve `U` Boole türü, karakter türü veya tamsayı türüne atanabilir. Türleri imzalı veya imzasız tamsayı ve herhangi bir boyuta 8 bitten 64 bit.

> [!NOTE]
> Ancak `SafeInt` sınıf kabul eden herhangi bir tamsayı türünü, daha verimli bir şekilde imzasız türler ile gerçekleştirir.

`E` hata işleme mekanizması, `SafeInt` kullanır. SafeInt Kitaplığı ile iki hata işleme düzenekleri sağlanır. Olan varsayılan ilkedir `SafeIntErrorPolicy_SafeIntException`, hangi oluşturur bir [Safeıntexception sınıfı](../safeint/safeintexception-class.md) bir hata oluştuğunda özel durum. Diğer ilke `SafeIntErrorPolicy_InvalidParameter`, bir hata oluşursa programı durdurur.

Hata ilkesi özelleştirmek için iki seçenek vardır. İlk seçenek parametresi ayarlamaktır `E` oluşturduğunuzda bir `SafeInt`. Hata ilkesi için yalnızca bir tane işleme değiştirmek istediğinizde bu seçeneği kullanın. `SafeInt`. Diğer seçenek, dahil etmeden önce özelleştirilmiş hata işleme sınıfınıza olmasını _SAFEINT_DEFAULT_ERROR_POLICY tanımlamaktır `SafeInt` kitaplığı. İlke tüm örnekleri için varsayılan hata değiştirmek istediğinizde bu seçeneği kullanın. `SafeInt` kodunuzda sınıfı.

> [!NOTE]
> SafeInt Kitaplığı'ndan hataları işleyecek bir özel sınıf denetimi hata işleyicisine çağıran koda döndürmemelidir. Hata işleyicisi çağrılır sonra sonucunu `SafeInt` işlemi güvenilen olamaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SafeInt`

## <a name="requirements"></a>Gereksinimler

**Başlık:** safeint.h

**Namespace:** msl::utilities

## <a name="safeint"></a>SafeInt::SafeInt

Oluşturur bir `SafeInt` nesne.

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

*i*<br/>
[in] Yeni değeri `SafeInt` nesne. Bu oluşturucuya bağlı olarak U, ya da T türünde bir parametresi olmalıdır.

*b*<br/>
[in] Yeni bir Boole değeri `SafeInt` nesne.

*u*<br/>
[in] A `SafeInt` türüne Yeni `SafeInt` nesnesi aynı değere sahip *u*, ancak türü t

U depolanan verilerin türünü `SafeInt`. Bu, bir Boole değeri, karakter veya tamsayı türü olabilir. Bir tamsayı türü ise, yeniden imzalanmış imzalanmamış veya bırakılabilir ve 8 ile 64 bit arasında olmalıdır.

### <a name="remarks"></a>Açıklamalar

Oluşturucu giriş parametresi *miyim* veya *u*, Boolean, karakter veya tamsayı türü olmalıdır. Parametresi, başka bir tür ise `SafeInt` sınıf çağrıları [static_assert](../cpp/static-assert.md) geçersiz giriş parametresi belirtmek için.

Şablon türü kullanmak oluşturucular `U` otomatik olarak giriş parametresi tarafından belirtilen türe dönüştürmek `T`. `SafeInt` Sınıfı, veri kaybı olmadan verileri dönüştürür. Hata işleyicisine raporları `E` veri türüne dönüştüremezse `T` veri kaybı olmadan.

Oluşturursanız, bir `SafeInt` değeri hemen başlatmak gereken bir Boole parametresi. Yapısı kopyalanamıyor bir `SafeInt` kodu kullanarak `SafeInt<bool> sb;`. Bu, bir derleme hatasına neden olur.
