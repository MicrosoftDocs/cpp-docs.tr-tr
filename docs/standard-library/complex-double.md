---
title: karmaşık&lt;çift&gt;
ms.date: 11/04/2016
f1_keywords:
- complex/std::complex<double>
helpviewer_keywords:
- complex<double> function
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
ms.openlocfilehash: 565a2e6b5ee4eb495cb4cc3241bb8ce72de538a2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453144"
---
# <a name="complexltdoublegt"></a>karmaşık&lt;çift&gt;

İlki, karmaşık bir sayının gerçek bölümünü ve sanal parçayı temsil eden ikincisini temsil eden **Double**türü her ikisi de içeren sıralı bir nesne çifti depolayan bir nesneyi tanımlar.

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
// rest same as template class complex
};
```

### <a name="parameters"></a>Parametreler

*RealVal*\
Oluşturulan karmaşık sayının gerçek parçası için **Double** türü değeri.

*Imagval*\
Oluşturulan karmaşık sayının sanal bölümü için **Double** türü değeri.

*Karmaşıksayı*\
Gerçek ve sanal parçaları, bir karmaşık sayıda **Double** oluşturulması için kullanılan **float** veya **Long Double** türündeki karmaşık sayı.

## <a name="return-value"></a>Dönüş Değeri

**Double**türünde karmaşık bir sayı.

## <a name="remarks"></a>Açıklamalar

Template sınıfının **Double** türündeki karmaşık bir sınıf için karmaşık özelleştirmesi, şablon sınıfından yalnızca tanımladığı oluşturuculardan farklıdır. **Float** türünden **Double** 'a dönüştürmenin örtük olmasına izin verilir, ancak **Long Double** 'dan **Double** 'a dönüştürmenin **Açık**olması gerekir. Atama söz dizimini kullanarak tür dönüşümle başlatma, **Açık** kuralların kullanımı.

Şablon sınıfı `complex`hakkında daha fazla bilgi için bkz. [Complex Class](../standard-library/complex-class.md). Şablon sınıfının `complex`üyelerinin bir listesi için bkz.

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

**Üstbilgi**: \<karmaşık >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[karmaşık sınıf](../standard-library/complex-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
