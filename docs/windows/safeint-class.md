---
title: SafeInt sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce7715553e17e49ef3c169145abfb49816f6d6dd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891343"
---
# <a name="safeint-class"></a>SafeInt Sınıfı
Tamsayı taşma önlemeye yardımcı olmak için tamsayı temelleri genişletir ve tamsayılar farklı türlerde karşılaştırmanıza olanak tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>  
class SafeInt;  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Şablon|Açıklama|  
|--------------|-----------------|  
|T|Tür tamsayı veya Boole parametresi, `SafeInt` yerini alır.|  
|E|İlke işleme hatası tanımlayan numaralandırılmış veri türü.|  
|U|Tamsayı veya Boole parametresi ikincil işleneni için türü.|  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[içindeki]|Birden fazla tek başına işlevlerinde işlecinin sağ tarafında değerini temsil eden giriş parametresi.|  
|[,] ediyorum|Birden fazla tek başına işlevlerinde işlecinin sağ tarafında değerini temsil eden giriş parametresi.|  
|BITS]|Birden fazla tek başına işlevlerinde işlecinin sağ tarafında değerini temsil eden giriş parametresi.|  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SafeInt::SafeInt](../windows/safeint-safeint.md)|Varsayılan Oluşturucu.|  
  
### <a name="assignment-operators"></a>Atama İşleçleri  
  
|Ad|Sözdizimi|  
|----------|------------|  
|=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const U& rhs)`|  
|=|`SafeInt<T,E>& operator= (const T& rhs) throw()`|  
|=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)`|  
|=|`SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()`|  
  
### <a name="casting-operators"></a>Atama İşleçleri  
  
|Ad|Sözdizimi|  
|----------|------------|  
|bool|`operator bool() throw()`|  
|char|`operator char() const`|  
|İmzalı char|`operator signed char() const`|  
|unsigned char|`operator unsigned char() const`|  
|__int16|`operator __int16() const`|  
|İmzasız __int16|`operator unsigned __int16() const`|  
|__int32|`operator __int32() const`|  
|İmzasız __int32|`operator unsigned __int32() const`|  
|long|`operator long() const`|  
|imzasız long|`operator unsigned long() const`|  
|__int64|`operator __int64() const`|  
|İmzasız __int64|`operator unsigned __int64() const`|  
|wchar_t|`operator wchar_t() const`|  
  
### <a name="comparison-operators"></a>Karşılaştırma İşleçleri  
  
|Ad|Sözdizimi|  
|----------|------------|  
|<|`template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()`|  
|<|`bool operator< (SafeInt<T,E> rhs) const throw()`|  
|>=|`template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()`|  
|>=|`Bool operator>= (SafeInt<T,E> rhs) const throw()`|  
|>|`template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()`|  
|>|`Bool operator> (SafeInt<T,E> rhs) const throw()`|  
|<=|`template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()`|  
|<=|`bool operator<= (SafeInt<T,E> rhs) const throw()`|  
|==|`template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()`|  
|==|`bool operator== (bool rhs) const throw()`|  
|==|`bool operator== (SafeInt<T,E> rhs) const throw()`|  
|!=|`template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()`|  
|!=|`bool operator!= (bool b) const throw()`|  
|!=|`bool operator!= (SafeInt<T,E> rhs) const throw()`|  
  
### <a name="arithmetic-operators"></a>Aritmetik İşleçler  
  
|Ad|Sözdizimi|  
|----------|------------|  
|+|`const SafeInt<T,E>& operator+ () const throw()`|  
|-|`SafeInt<T,E> operator- () const`|  
|++|`SafeInt<T,E>& operator++ ()`|  
|--|`SafeInt<T,E>& operator-- ()`|  
|%|`template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const`|  
|%|`SafeInt<T,E> operator% (SafeInt<T,E> rhs) const`|  
|%=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)`|  
|%=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)`|  
|*|`template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const`|  
|*|`SafeInt<T,E> operator* (SafeInt<T,E> rhs) const`|  
|*=|`SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)`|  
|*=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)`|  
|*=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)`|  
|/|`template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const`|  
|/|`SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const`|  
|/=|`SafeInt<T,E>& operator/= (SafeInt<T,E> i)`|  
|/=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)`|  
|/=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)`|  
|+|`SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const`|  
|+|`template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const`|  
|+=|`SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)`|  
|+=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)`|  
|+=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)`|  
|-|`template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const`|  
|-|`SafeInt<T,E> operator- (SafeInt<T,E> rhs) const`|  
|-=|`SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)`|  
|-=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)`|  
|-=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)`|  
  
### <a name="logical-operators"></a>Mantıksal İşleçler  
  
|Ad|Sözdizimi|  
|----------|------------|  
|!|`bool operator !() const throw()`|  
|~|`SafeInt<T,E> operator~ () const throw()`|  
|<<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()`|  
|<<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()`|  
|<<=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()`|  
|<<=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()`|  
|>>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()`|  
|>>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()`|  
|>>=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()`|  
|>>=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()`|  
|&|`SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()`|  
|&|`template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()`|  
|&=|`SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()`|  
|&=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()`|  
|&=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()`|  
|^|`SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()`|  
|^|`template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()`|  
|^=|`SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()`|  
|^=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()`|  
|^=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()`|  
|&#124;|`SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()`|  
|&#124;|`template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()`|  
|&#124;=|`SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()`|  
|&#124;=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()`|  
|&#124;=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()`|  
  
## <a name="remarks"></a>Açıklamalar  
 `SafeInt` Sınıfı tamsayı taşma matematik işlemlerinde karşı korur. Örneğin, iki 8 bit tamsayı eklemeyi düşünün: bir 200 değeri ve ikinci değer olarak 100 sahiptir. Doğru matematiksel işlemi 200 + 100 = 300 olacaktır. Ancak, 8 bit tam sayı sınırı nedeniyle üst bit kaybolur ve derleyici 44 döndürür (300-2<sup>8</sup>) sonucu olarak. Üzerinde matematiksel Bu denklemi bağımlı herhangi bir işlem beklenmeyen davranışlara neden olur.  
  
 `SafeInt` Sınıfı denetler olup aritmetik taşma oluşur veya kod olup olmadığını sıfıra bölünme dener. Her iki durumda da sınıfı olası sorunu program uyarmak için hata işleyici çağırır.  
  
 Bu sınıf ayrıca, iki farklı türde tamsayılar oldukları sürece karşılaştırmanızı sağlar `SafeInt` nesneleri. Genellikle, bir karşılaştırma gerçekleştirdiğinizde, aynı türden olması sayıları önce dönüştürmeniz gerekir. Başka bir tür için bir sayı genellikle atama hiçbir veri kaybı olduğundan emin olmak için kontroller gerektirir.  
  
 Bu konudaki işleçleri tablo tarafından desteklenen matematiksel ve Karşılaştırma işleçleri listeler `SafeInt` sınıfı. En matematik işleçleri dönüş bir `SafeInt` nesne türü `T`.  
  
 Karşılaştırma işlemleri arasında bir `SafeInt` ve tamsayı türü herhangi bir yönde gerçekleştirilebilir. Örneğin, her ikisi de `SafeInt<int>(x) < y` ve `y> SafeInt<int>(x)` geçerli olduğundan ve aynı sonucu döndürür.  
  
 Birçok ikili işleçler iki farklı kullanarak desteklemeyen `SafeInt` türleri. Bunun bir örneği `&` işleci. `SafeInt<T, E> & int` desteklenir, ancak `SafeInt<T, E> & SafeInt<U, E>` değil. İkinci örnekte derleyici döndürmek için parametre türünü bilmez. Bu sorun için bir çözüm için ikinci parametre temel türü geri dönüştürmek için ' dir. Aynı parametreleri kullanarak, bu, yapılabilir `SafeInt<T, E> & (U)SafeInt<U, E>`.  
  
> [!NOTE]
>  Bit düzeyinde herhangi bir işlem için iki farklı parametreler aynı boyutta olmalıdır. Boyutlar farklıysa, derleyici özel durum oluşturacak bir [ASSERT](../mfc/reference/diagnostic-services.md#assert) özel durum. Bu işlemin sonuçları doğru olmasını garanti edilemez. Bu sorunu çözmek için daha büyük parametre ile aynı boyutta oluncaya kadar küçük parametre dönüştürün.  
  
 Kaydırma işleçleri için şablon türü var olandan daha fazla BITS kaydırma ASSERT özel durum oluşturur. Bu yayın modunda hiçbir etkisi olmaz. Dönüş türü özgün türü ile aynı olduğundan SafeInt parametreleri iki tür karıştırma kaydırma işleçleri için mümkün değildir. Sayısını sağ tarafında işleci yalnızca kaydırılacak bit sayısını gösterir.  
  
 SafeInt nesnesi ile mantıksal bir karşılaştırma gerçekleştirdiğinizde, karşılaştırması kesinlikle aritmetik bulunur. Örneğin, bu ifadeler göz önünde bulundurun:  
  
-   `SafeInt<uint>((uint)~0) > -1`  
  
-   `((uint)~0) > -1`  
  
 İlk ifade çözümler `true`, ancak ikinci ifade çözümler `false`. Bit tabanlı değil işlecini 0 0xFFFFFFFF kullanılır. İkinci ifade varsayılan karşılaştırma işleci 0xFFFFFFFF için 0xFFFFFFFF karşılaştırır ve bunları eşit olarak göz önünde bulundurur. Karşılaştırma işleci için `SafeInt` sınıfı gerçekleştirir ilk parametre imzasız iken ikinci parametre negatiftir. Bu nedenle, bit gösteriminde aynı olmasına rağmen `SafeInt` mantıksal işleç gerçekleştirir işaretsiz tamsayı -1'den daha büyük.  
  
 Kullanırken dikkatli olun `SafeInt` ile birlikte sınıf `?:` Üçlü işleci. Aşağıdaki kod satırını göz önünde bulundurun.  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : -1;  
```  
  
 Derleyici, bu dönüştürür:  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);  
```  
  
 Varsa `flag` olan `false`, derleyici için -1 değeri atamak yerine bir özel durum oluşturur `x`. Bu nedenle, bu davranışı önlemek için kullanılacak doğru aşağıdaki satırı kodudur.  
  
```  
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;  
```  
  
 `T` ve `U` bir Boolean türü, karakter türü veya tamsayı türü atanabilir. Tamsayı türleri imzalı veya imzasız ve herhangi bir boyuta 8 bitten 64 bit.  
  
> [!NOTE]
>  Ancak `SafeInt` sınıfı kabul eden herhangi bir tür tamsayı, imzasız türleriyle daha verimli bir şekilde gerçekleştirir.  
  
 `E` hata işleme mekanizması, `SafeInt` kullanır. Hata işleme için iki mekanizma SafeInt Kitaplığı ile sağlanır. Varsayılan ilke `SafeIntErrorPolicy_SafeIntException`, hangi atar bir [Safeıntexception sınıfı](../windows/safeintexception-class.md) bir hata oluştuğunda özel durum. Diğer ilke `SafeIntErrorPolicy_InvalidParameter`, bir hata oluşursa programı durdurur.  
  
 Hata ilkesi özelleştirmek için iki seçenek vardır. İlk parametre kümesini seçenektir `E` oluştururken bir `SafeInt`. Hata ilkesi için yalnızca bir tane işleme değiştirmek istediğinizde bu seçeneği kullanın `SafeInt`. Diğer seçenek tanımlamaktır `_SAFEINT_DEFAULT_ERROR_POLICY` dahil önce özelleştirilmiş hata işleme sınıfınız olacak `SafeInt` kitaplığı. Varsayılan hata tüm örnekleri için ilke işleme değiştirmek istediğinizde bu seçeneği kullanın `SafeInt` kodunuzda sınıfı.  
  
> [!NOTE]
>  SafeInt Kitaplığı hataları işleme özelleştirilmiş bir sınıf denetimi hata işleyicisine adlı kodu vermemelidir. Hata işleyicisi çağrılır sonra sonucu `SafeInt` işlemi güvenilen olamaz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SafeInt Kitaplığı](../windows/safeint-library.md)   
 [SafeIntException Sınıfı](../windows/safeintexception-class.md)