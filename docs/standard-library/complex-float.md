---
title: karmaşık&lt;float&gt;
ms.date: 11/04/2016
f1_keywords:
- complex/std::complex<float>
helpviewer_keywords:
- complex<float> function
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
ms.openlocfilehash: bfe0e9dcb0bf8f8b74487404998e06d233097a39
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453108"
---
# <a name="complexltfloatgt"></a>karmaşık&lt;float&gt;

İlk olarak, karmaşık bir sayının gerçek bölümünü ve sanal parçayı temsil eden ikincisini temsil eden **float**türünde nesnelerin sıralı bir çiftini depolayan bir nesneyi tanımlar.

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

*_RealVal*\
Oluşturulan karmaşık sayının gerçek parçası için **float** türünün değeri.

*_ImagVal*\
Oluşturulan karmaşık sayının sanal bölümü için **float** türünün değeri.

*Karmaşıksayı*\
Gerçek ve sanal parçaları, oluşturulmakta olan karmaşık sayıda **kayan** türü başlatmak için kullanılan **Double** veya **Long Double** türünde karmaşık bir sayıdır.

## <a name="return-value"></a>Dönüş Değeri

**Kayan**türünde karmaşık bir sayı.

## <a name="remarks"></a>Açıklamalar

**Float** türündeki karmaşık bir sınıf için karmaşık olan şablon sınıfının açık özelleştirmesi, şablon sınıfından yalnızca tanımladığı oluşturuculardan farklıdır. **Float** 'ten **Double** 'a dönüştürmenin örtük olmasına izin verilir, ancak **float** 'ten **Long Double** 'a daha az güvenli dönüştürmenin **Açık**olması gerekir. Atama söz dizimini kullanarak tür dönüşümle başlatma, **Açık** kuralların kullanımı.

Şablon sınıfı `complex`hakkında daha fazla bilgi için bkz. [Complex Class](../standard-library/complex-class.md). Şablon sınıfının `complex`üyelerinin bir listesi için bkz.

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
        << endl << "gives c2float = " << c2float << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 3.0 , 4.0 );
   complex <float> c3float ( c3longdouble );
   cout << "Explicit conversion from type long double to type float,"
        << endl << "gives c3float = " << c3float << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3float);
   double argc3 = arg ( c3float);
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:"
        << endl << "arg ( c3 ) = "
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

**Üstbilgi**: \<karmaşık >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[karmaşık sınıf](../standard-library/complex-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
