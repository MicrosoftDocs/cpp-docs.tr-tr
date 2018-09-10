---
title: karmaşık&lt;float&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- complex/std::complex<float>
dev_langs:
- C++
helpviewer_keywords:
- complex<float> function
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb2a78219cd5474f879407e75c5a89f14f87b647
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315970"
---
# <a name="complexltfloatgt"></a>karmaşık&lt;float&gt;

Her iki türdeki nesneleri sıralı bir çift depolayan bir nesneyi tanımlayan **float**, ilk karmaşık sayıyı ve ikinci gerçek bölümünü temsil eden sanal bölümü temsil eden.

## <a name="syntax"></a>Sözdizimi

```cpp
template <>
class complex<float> {
public:
    constexpr complex(
    float _RealVal = 0,
    float _ImagVal = 0);

constexpr complex(
    const complex<float>& complexNum);

constexpr complex(
    const complex<double>& complexNum);

constexpr complex(
    const complex<long double>& complexNum);
// rest same as template class complex
};
```

### <a name="parameters"></a>Parametreler

*_RealVal*<br/>
Türü değeri **float** için yapılandırılan karmaşık sayıyı gerçek bir parçası.

*_ImagVal*<br/>
Türü değeri **float** yapılandırılmakta karmaşık sayıyı sanal bölümü için.

*complexNum*<br/>
Tür karmaşık sayısı **çift** veya türü **uzun çift** olan reel ve sanal parça türü karmaşık bir sayıyı başlatmak için kullanılan **float** oluşturuluyor.

## <a name="return-value"></a>Dönüş Değeri

Türü karmaşık bir sayıyı **float**.

## <a name="remarks"></a>Açıklamalar

Karmaşık türü karmaşık bir sınıfa şablon sınıfının açık uzmanlığı **float** Şablon sınıfı yalnızca tanımladığı Yapıcılardaki farklıdır. Dönüştürme **float** için **çift** örtük, izin verilen ancak daha az güvenli dönüştürme **float** için **uzun çift** olduğu olması gereken **açık**. Kullanımını **açık** başlatma ile atama sözdizimi kullanılarak tür dönüştürme kuralları.

Şablon sınıfı hakkında daha fazla bilgi için `complex`, bkz: [complex sınıfı](../standard-library/complex-class.md). Şablon sınıfının üye listesini `complex`, bkz.

## <a name="example"></a>Örnek

```cpp
// complex_comp_flt.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <float> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type double
   complex <double> c2double ( 1.0 , 3.0 );
   complex <float> c2float ( c2double );
   cout << "Implicit conversion from type double to type float,"
        << "\n gives c2float = " << c2float << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 3.0 , 4.0 );
   complex <float> c3float ( c3longdouble );
   cout << "Explicit conversion from type long double to type float,"
        << "\n gives c3float = " << c3float << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3float);
   double argc3 = arg ( c3float);
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
/* Output:
Specifying initial real & imaginary parts,
 as type float gives c1 = (4,5)
Implicit conversion from type double to type float,
 gives c2float = (1,3)
Explicit conversion from type long double to type float,
 gives c3float = (3,4)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5
Argument of c3 is recovered from c3 using:
 arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.
*/
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<karmaşık >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[complex Sınıfı](../standard-library/complex-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
