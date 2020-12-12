---
description: 'Daha fazla bilgi edinin: karmaşık &lt; Çift&gt;'
title: karmaşık &lt; Çift&gt;
ms.date: 11/04/2016
f1_keywords:
- complex/std::complex<double>
helpviewer_keywords:
- complex<double> function
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
ms.openlocfilehash: 9238e71fcdd70576276eb1ba429a48eeec954601
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325042"
---
# <a name="complexltdoublegt"></a>karmaşık &lt; Çift&gt;

**`double`** İlki, karmaşık bir sayının gerçek bölümünü ve sanal parçayı temsil eden ikincisini temsil eden, her ikisi de türünde sıralı bir nesne çifti depolayan bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <>
class complex<double> {
public:
    constexpr complex(
    double RealVal = 0,
    double ImagVal = 0);

constexpr complex(const complex<double>& complexNum);

constexpr explicit complex(const complex<long double>& complexNum);
// rest same as class template complex
};
```

### <a name="parameters"></a>Parametreler

*RealVal*\
**`double`** Oluşturulan karmaşık sayının gerçek parçası için tür değeri.

*Imagval*\
**`double`** Oluşturulmakta olan karmaşık sayının sanal parçasının tür değeri.

*Karmaşıksayı*\
**`float`** **`long double`** Oluşturulan karmaşık bir tür türü başlatmak için gerçek ve sanal parçaları kullanılan tür veya türün karmaşık sayısı **`double`** .

## <a name="return-value"></a>Dönüş Değeri

Karmaşık türden bir sayıdır **`double`** .

## <a name="remarks"></a>Açıklamalar

Sınıf şablonunun karmaşık bir tür karmaşık özelleştirmesi, **`double`** sınıf şablonundan yalnızca tanımladığı oluşturucularda farklılık gösterir. Öğesinden öğesine dönüştürmenin **`float`** **`double`** örtük olmasına izin verilir, ancak öğesinden **`long double`** öğesine dönüştürmenin **`double`** olması gerekir **`explicit`** . **`explicit`** Atama söz dizimini kullanarak tür dönüşümle başlatma kurallarını kullanma.

Sınıf şablonu hakkında daha fazla bilgi için `complex` bkz. [Complex Class](../standard-library/complex-class.md). Sınıf şablonu üyelerinin listesi için `complex` bkz..

## <a name="example"></a>Örnek

```cpp
// complex_comp_dbl.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <double> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << "as type double gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type float
   complex <float> c2float ( 4.0 , 5.0 );
   complex <double> c2double ( c2float );
   cout << "Implicit conversion from type float to type double,"
        << endl << "gives c2double = " << c2double << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 4.0 , 5.0 );
   complex <double> c3double ( c3longdouble );
   cout << "Explicit conversion from type float to type double,"
        << endl << "gives c3longdouble = " << c3longdouble << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3longdouble );
   double argc3 = arg ( c3longdouble );
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:" << endl
        << "arg ( c3 ) = " << argc3 << " radians, which is "
        << argc3 * 180 / pi << " degrees." << endl;
}
/* Output:
Specifying initial real & imaginary parts,
as type double gives c1 = (4,5)
Implicit conversion from type float to type double,
gives c2double = (4,5)
Explicit conversion from type float to type double,
gives c3longdouble = (4,5)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 6.40312
Argument of c3 is recovered from c3 using:
arg ( c3 ) = 0.896055 radians, which is 51.3402 degrees.
*/
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<complex>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[karmaşık sınıf](../standard-library/complex-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
