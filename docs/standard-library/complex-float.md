---
title: karmaşık &lt; float&gt;
ms.date: 11/04/2016
f1_keywords:
- complex/std::complex<float>
helpviewer_keywords:
- complex<float> function
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
ms.openlocfilehash: 441006c977b4a4249270d0f4809da0fba0163395
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230071"
---
# <a name="complexltfloatgt"></a>karmaşık &lt; float&gt;

**`float`** İlki, karmaşık bir sayının gerçek bölümünü ve sanal parçayı temsil eden ikincisini temsil eden, her ikisi de türünde sıralı bir nesne çifti depolayan bir nesne tanımlar.

## <a name="syntax"></a>Söz dizimi

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
// rest same as class template complex
};
```

### <a name="parameters"></a>Parametreler

*_RealVal*\
**`float`** Oluşturulan karmaşık sayının gerçek parçası için tür değeri.

*_ImagVal*\
**`float`** Oluşturulmakta olan karmaşık sayının sanal parçasının tür değeri.

*Karmaşıksayı*\
**`double`** **`long double`** Oluşturulan karmaşık bir tür türü başlatmak için gerçek ve sanal parçaları kullanılan tür veya türün karmaşık sayısı **`float`** .

## <a name="return-value"></a>Dönüş Değeri

Karmaşık türden bir sayıdır **`float`** .

## <a name="remarks"></a>Açıklamalar

Sınıf şablonunun karmaşık bir tür karmaşık özelleştirmesi, **`float`** sınıf şablonundan yalnızca tanımladığı oluşturucularda farklılık gösterir. Öğesinden öğesine dönüştürmenin **`float`** **`double`** örtük olmasına izin verilir, ancak ' den daha az güvenli dönüşüm **`float`** **`long double`** olması gerekir **`explicit`** . **`explicit`** Atama söz dizimini kullanarak tür dönüşümle başlatma kurallarını kullanma.

Sınıf şablonu hakkında daha fazla bilgi için `complex` bkz. [Complex Class](../standard-library/complex-class.md). Sınıf şablonu üyelerinin listesi için `complex` bkz..

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

**Üst bilgi**:\<complex>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[karmaşık sınıf](../standard-library/complex-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
