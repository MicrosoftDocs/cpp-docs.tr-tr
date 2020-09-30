---
title: '&lt;bit &gt; işlevleri'
description: Tek tek bitleri ve bit dizilerini erişmek, işlemek ve işlemek için işlevler
ms.date: 08/28/2020
f1_keywords:
- bit/std::bit_cast
- bit/std::has_single_bit
- bit/std::bit_ceil
- bit/std::bit_floor
- bit/std::bit_width
- bit/std::rotl
- bit/std::rotr
- bit/std::countl_zero
- bit/std::countl_one
- bit/std::countr_zero
- bit/std::countr_one
- bit/std::popcount
helpviewer_keywords:
- std::bit [C++], bit_cast
- std::bit [C++], has_single_bit
- std::bit [C++], bit_ceil
- std::bit [C++], bit_floor
- std::bit [C++], bit_width
- std::bit [C++], rotl
- std::bit [C++], rotr
- std::bit [C++], countl_zero
- std::bit [C++], countl_one
- std::bit [C++], countr_zero
- std::bit [C++], countr_one
- std::bit [C++], popcount
ms.openlocfilehash: 94e44493b9356b3a0717c42aa1bed510ebe460dd
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509988"
---
# <a name="ltbitgt-functions"></a>&lt;bit &gt; işlevleri

\<bit>Üst bilgi, aşağıdaki üye olmayan şablon işlevlerini içerir:

| **Üye olmayan işlevler** | **Açıklama** |
|--------|---------|
|[bit_cast](#bit_cast) | Nesne temsilini bir türden diğerine yeniden yorumlayın. |
|[bit_ceil](#bit_ceil) | İki değerden büyük veya eşit bir değere eşit olan en küçük kuvveti bulun. |
|[bit_floor](#bit_floor) | Sıfırdan büyük olan en büyük kuvveti bir değerden daha fazla bulun. |
|[bit_width](#bit_width) | Bir değeri temsil etmek için gereken en az bit sayısını bulun. |
|[countl_zero](#countl_zero) | Ardışık bitlerin sayısını, en önemli bitten başlayarak sıfır olarak ayarlayın. |
|[countl_one](#countl_one) | En önemli bitden başlayarak, birbirini izleyen ardışık bitlerin sayısını bir olarak ayarlayın. |
|[countr_zero](#countr_zero) | En az önemli bitden başlayarak ardışık bitlerin sayısını sıfır olarak ayarlayın. |
|[countr_one](#countl_one) | Ardışık olmayan bitlerin sayısını, en az önemli bir bitten başlayarak bir tane olarak ayarlayın. |
|[has_single_bit](#has_single_bit) | Bir değerin tek bir bit kümesine sahip olup olmadığını denetleyin. Bu, bir değerin ikinin üssü olup olmadığını test etme ile aynıdır. |
|[popcount](#popcount) | Bir olarak ayarlanan bit sayısını say. |
|[rotl](#rotl) | Bit düzeyinde sola döndürme sonucunu hesaplama. |
|[rotr](#rotr) | Bit düzeyinde sağa döndürme sonucunu hesaplama. |

## <a name="bit_cast"></a>`bit_cast`

Türündeki bir nesneden bir bit modelini `From` türündeki yeni bir nesneye kopyalayın `To` .

```cpp
template <class To, class From>
[[nodiscard]] constexpr To bit_cast(const From& from) noexcept;
```

### <a name="parameters"></a>Parametreler

*Hedef*\
Çıkışın türü.

*Kaynak*\
Dönüştürülecek değerin türü.

*Kaynak*\
Dönüştürülecek değer.

### <a name="return-value"></a>Döndürülen değer

`To` türünün bir nesnesi.

İçindeki her bir bit, içinde doldurma bitleri olmadığı müddetçe içindeki karşılık gelen bit ile eşleşir `from` `To` , bu durumda sonuçta bu bitler belirtilmemiş olur.

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <iostream>

int main()
{
    float f = std::numeric_limits<float>::infinity();
    int i = std::bit_cast<int>(f);
    std::cout << "float f = " << std::hex << f
              << "\nstd::bit_cat<int>(f) = " << std::hex << i << '\n';
    return 0;
}
```

```Output
float f = inf
std::bit_cat<int>(f) = 7f800000
```

### <a name="remarks"></a>Açıklamalar

Alt düzey kodun genellikle bir türdeki bir nesneyi başka bir tür olarak yorumlaması gerekir. Yeniden yorumlanan nesne orijinaliyle aynı bit gösterimine sahiptir, ancak farklı bir tür.

Veya kullanmak yerine, `reinterpret_cast` `memcpy()` `bit_cast()` bu dönüşümleri yapmanın daha iyi bir yoludur. Daha iyidir çünkü:

- `bit_cast()``constexpr`
- `bit_cast()` türlerin kopyalanabilir ve aynı boyutta olmasını gerektirir. Bu, ve kullanarak karşılaşabileceğiniz olası sorunları önler `reinterpret_cast` ve `memcpy` yanlışlıkla ve yanlış bir şekilde kullanılabilmesi için, üç aylık olmayan-kopyalanabilir türlerini dönüştürebilir. Ayrıca, `memcpy()` aynı boyutta olmayan türler arasında yanlışlıkla kopyalamak için de kullanılabilir. Örneğin, bir işaretsiz int (4 bayt) veya başka bir şekilde bir çift (8 bayt).

Bu aşırı yükleme yalnızca şu durumlarda aşırı yükleme çözümüne katılır:

- `sizeof(To) == sizeof(From)`
- `To` ve `From` [is_trivially_copyable](is-trivially-copyable-class.md).

Bu işlev şablonu `constexpr` ve yalnızca `To` ,, `From` ve kendi alt nesnelerin türleri ise:

- birleşim veya işaretçi türü değil
- Üye türüne yönelik bir işaretçi değil
- geçici değil
- bir başvuru türü olan statik olmayan veri üyesi yok

## <a name="bit_ceil"></a>`bit_ceil`

İki değerden büyük veya eşit bir değere eşit olan en küçük kuvveti bulun. Örneğin, verilen `3` , döndürür `4` .

```cpp
template<class T>
[[nodiscard]] constexpr T bit_ceil(T value);
```

### <a name="parameters"></a>Parametreler

*deeri*\
Sınanacak işaretsiz tamsayı değeri.

### <a name="return-value"></a>Döndürülen değer

 İki değerden büyük veya buna eşit en küçük üssü `value` .

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (auto i = 0u; i < 6u; ++i) // bit_ceil() takes an unsigned integer type
    {
        auto nextClosestPowerOf2 = std::bit_ceil(i);
        std::cout << "\nbit_ceil(0b" << std::bitset<4>(i) << ") = "
                  << "0b" << std::bitset<4>(nextClosestPowerOf2);
    }
    return 0;
}
```

```Output
bit_ceil(0b0000) = 0b0001
bit_ceil(0b0001) = 0b0001
bit_ceil(0b0010) = 0b0010
bit_ceil(0b0011) = 0b0100
bit_ceil(0b0100) = 0b0100
bit_ceil(0b0101) = 0b1000
```

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yalnızca `T` , işaretsiz bir tamsayı türü ise aşırı yükleme çözümüne katılır. Örneğin:,,, vb `unsigned int` `unsigned long` `unsigned short` `unsigned char` .

## <a name="bit_floor"></a>`bit_floor`

Sıfırdan büyük olan en büyük kuvveti bir değerden daha fazla bulun. Örneğin, verilen `5` , döndürür `4` .

```cpp
template< class T >
[[nodiscard]] constexpr T bit_floor(T value) noexcept;
```

### <a name="parameters"></a>Parametreler

*deeri*\
Sınanacak işaretsiz tamsayı değeri.

### <a name="return-value"></a>Döndürülen değer

İkiden büyük olmayan en büyük üssü `value` . \
`value`Sıfırsa, sıfır döndürür.

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (auto i = 0u; i < 6u; ++i) // bit_floor() takes an unsigned integer type
    {
        auto previousPowerOf2 = std::bit_floor(i);
        std::cout << "\nbit_floor(0b" << std::bitset<4>(i) << ") = 0b"
                  << std::bitset<4>(previousPowerOf2);
    }
    return 0;
}
```

```Output
bit_floor(0b0000) = 0b0000
bit_floor(0b0001) = 0b0001
bit_floor(0b0010) = 0b0010
bit_floor(0b0011) = 0b0010
bit_floor(0b0100) = 0b0100
bit_floor(0b0101) = 0b0100
```

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yalnızca `T` , işaretsiz bir tamsayı türü ise aşırı yükleme çözümüne katılır. Örneğin:,,, vb `unsigned int` `unsigned long` `unsigned short` `unsigned char` .

## <a name="bit_width"></a>`bit_width`

Bir değeri temsil etmek için gereken en az bit sayısını bulun.

Örneğin, 5 (0b101) verildiğinde, 5 değerini ifade etmek için 3 ikili bit kullandığından 3 değeri döndürür.

```cpp
template<class T>
[[nodiscard]] constexpr T bit_width(T value) noexcept;
```

### <a name="parameters"></a>Parametreler

*deeri*\
Sınanacak işaretsiz tamsayı değeri.

### <a name="return-value"></a>Döndürülen değer

Temsil etmek için gereken bit sayısı `value` . \
`value`Sıfırsa, sıfır döndürür.

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <iostream>

int main()
{
    for (unsigned i=0u; i <= 8u; ++i)
    {
        std::cout << "\nbit_width(" << i << ") = "
                  << std::bit_width(i);
    }
    return 0;
}
```

```Output
bit_width(0) = 0
bit_width(1) = 1
bit_width(2) = 2
bit_width(3) = 2
bit_width(4) = 3
bit_width(5) = 3
bit_width(6) = 3
bit_width(7) = 3
bit_width(8) = 4
```

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yalnızca `T` , işaretsiz bir tamsayı türü ise aşırı yükleme çözümüne katılır. Örneğin:,,, vb `unsigned int` `unsigned long` `unsigned short` `unsigned char` .

## <a name="countl_zero"></a>`countl_zero`

Ardışık bitlerin sayısını, en önemli bitten başlayarak sıfır olarak ayarlayın.

```cpp
template<class T>
[[nodiscard]] constexpr int countl_zero(T value) noexcept;
```

### <a name="parameters"></a>Parametreler

*deeri*\
Sınanacak işaretsiz tamsayı değeri.

### <a name="return-value"></a>Döndürülen değer

En önemli bitden başlayarak ardışık sıfır bitlerin sayısı. \
`value`Sıfırsa, türünün bit sayısı `value` .

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (unsigned char result = 0, i = 0; i < 9; i++)
    {
        std::cout << "\ncountl_zero(0b" << std::bitset<8>(result) << ") = " << std::countl_zero(result);
        result = result == 0 ? 1 : result * 2;
    }
    return 0;
}
```

```Output
countl_zero(0b00000000) = 8
countl_zero(0b00000001) = 7
countl_zero(0b00000010) = 6
countl_zero(0b00000100) = 5
countl_zero(0b00001000) = 4
countl_zero(0b00010000) = 3
countl_zero(0b00100000) = 2
countl_zero(0b01000000) = 1
countl_zero(0b10000000) = 0
```

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yalnızca `T` , işaretsiz bir tamsayı türü ise aşırı yükleme çözümüne katılır. Örneğin:,,, vb `unsigned int` `unsigned long` `unsigned short` `unsigned char` .

## <a name="countl_one"></a>`countl_one`

En önemli bitden başlayarak, birbirini izleyen ardışık bitlerin sayısını bir olarak ayarlayın.

```cpp
template<class T>
[[nodiscard]] constexpr int countl_one(T value) noexcept;
```

### <a name="parameters"></a>Parametreler

*deeri*\
Sınanacak işaretsiz tamsayı değeri.

### <a name="return-value"></a>Döndürülen değer

En önemli bitden başlayarak, tek bir olarak ayarlanan ardışık bitlerin sayısı.

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char value = 0;
    for (unsigned char bit = 128; bit > 0; bit /= 2)
    {
        value |= bit;
        std::cout << "\ncountl_one(0b" << std::bitset<8>(value) << ") = "
                  << std::countl_one(value);
    }
    return 0;
}
```

```Output
countl_one(0b10000000) = 1
countl_one(0b11000000) = 2
countl_one(0b11100000) = 3
countl_one(0b11110000) = 4
countl_one(0b11111000) = 5
countl_one(0b11111100) = 6
countl_one(0b11111110) = 7
countl_one(0b11111111) = 8
```

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yalnızca `T` , işaretsiz bir tamsayı türü ise aşırı yükleme çözümüne katılır. Örneğin:,,, vb `unsigned int` `unsigned long` `unsigned short` `unsigned char` .

## <a name="countr_zero"></a>`countr_zero`

En az önemli bitden başlayarak ardışık bitlerin sayısını sıfır olarak ayarlayın.

```cpp
template<class T>
[[nodiscard]] constexpr int countr_zero(T value) noexcept;
```

### <a name="parameters"></a>Parametreler

*deeri*\
Sınanacak işaretsiz tamsayı değeri.

### <a name="return-value"></a>Döndürülen değer

En az önemli bitden başlayarak ardışık sıfır bit sayısı. \
`value`Sıfırsa, türünün bit sayısı `value` .

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (unsigned char result = 0, i = 0; i < 9; i++)
    {
        std::cout << "\ncountr_zero(0b" << std::bitset<8>(result) << ") = "
                  << std::countr_zero(result);
        result = result == 0 ? 1 : result * 2;
    }
    return 0;
}
```

```Output
countr_zero(0b00000000) = 8
countr_zero(0b00000001) = 0
countr_zero(0b00000010) = 1
countr_zero(0b00000100) = 2
countr_zero(0b00001000) = 3
countr_zero(0b00010000) = 4
countr_zero(0b00100000) = 5
countr_zero(0b01000000) = 6
countr_zero(0b10000000) = 7
```

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yalnızca `T` , işaretsiz bir tamsayı türü ise aşırı yükleme çözümüne katılır. Örneğin:,,, vb `unsigned int` `unsigned long` `unsigned short` `unsigned char` .

## <a name="countr_one"></a>`countr_one`

Ardışık olmayan bitlerin sayısını, en az önemli bir bitten başlayarak bir tane olarak ayarlayın.

```cpp
template<class T>
[[nodiscard]] constexpr int countr_one(T value) noexcept;
```

### <a name="parameters"></a>Parametreler

*deeri*\
Sınanacak işaretsiz tamsayı değeri.

### <a name="return-value"></a>Döndürülen değer

En az önemli bitden başlayarak, tek bir olarak ayarlanan ardışık bitlerin sayısı.

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char value = 0;
    for (int bit = 1; bit <= 128; bit *= 2)
    {
        value |= bit;
        std::cout << "\ncountr_one(0b" << std::bitset<8>(value) << ") = "
                  << std::countr_one(value);
    }
    return 0;
}
```

```Output
countr_one(0b00000001) = 1
countr_one(0b00000011) = 2
countr_one(0b00000111) = 3
countr_one(0b00001111) = 4
countr_one(0b00011111) = 5
countr_one(0b00111111) = 6
countr_one(0b01111111) = 7
countr_one(0b11111111) = 8
```

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yalnızca `T` , işaretsiz bir tamsayı türü ise aşırı yükleme çözümüne katılır. Örneğin:,,, vb `unsigned int` `unsigned long` `unsigned short` `unsigned char` .

## <a name="has_single_bit"></a>`has_single_bit`

Değerin yalnızca bir bit kümesine sahip olup olmadığını denetleyin. Bu, bir değerin ikinin üssü olup olmadığını test etme ile aynıdır.

```cpp
template <class T>
[[nodiscard]] constexpr bool has_single_bit(T value) noexcept;
```

### <a name="parameters"></a>Parametreler

*deeri*\
Sınanacak işaretsiz tamsayı değeri.

### <a name="return-value"></a>Döndürülen değer

`true``value`yalnızca bir bit kümesine sahipse, bu da iki üssü de anlamına gelir `value` . Tersi durumda `false`.

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <bitset>
#include <iostream>
#include <iomanip>

int main()
{
    for (auto i = 0u; i < 10u; ++i)
    {
        std::cout << "has_single_bit(0b" << std::bitset<4>(i) << ") = "
                  << std::boolalpha << std::has_single_bit(i) << '\n';
    }
    return 0;
}
```

```Output
has_single_bit(0b0000) = false
has_single_bit(0b0001) = true
has_single_bit(0b0010) = true
has_single_bit(0b0011) = false
has_single_bit(0b0100) = true
has_single_bit(0b0101) = false
has_single_bit(0b0110) = false
has_single_bit(0b0111) = false
has_single_bit(0b1000) = true
has_single_bit(0b1001) = false
```

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yalnızca `T` , işaretsiz bir tamsayı türü ise aşırı yükleme çözümüne katılır. Örneğin:,,, vb `unsigned int` `unsigned long` `unsigned short` `unsigned char` .

## <a name="popcount"></a>`popcount`

İşaretsiz bir tamsayı değerinde bir tane olarak ayarlanan bit sayısını say.

```cpp
template<class T>
[[nodiscard]] constexpr int popcount(T value) noexcept;
```

### <a name="parameters"></a>Parametreler

*deeri*\
Sınanacak işaretsiz tamsayı değeri.

### <a name="return-value"></a>Döndürülen değer

Sayı bitleri içinde bir olarak ayarlanır `value` .

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
   for (unsigned char value = 0; value < 16; value++)
    {
        std::cout << "\npopcount(0b" << std::bitset<4>(value) << ") = "
                  << std::popcount(value);
    }
    return 0;
}
```

```Output
popcount(0b0000) = 0
popcount(0b0001) = 1
popcount(0b0010) = 1
popcount(0b0011) = 2
popcount(0b0100) = 1
popcount(0b0101) = 2
popcount(0b0110) = 2
popcount(0b0111) = 3
popcount(0b1000) = 1
popcount(0b1001) = 2
popcount(0b1010) = 2
popcount(0b1011) = 3
popcount(0b1100) = 2
popcount(0b1101) = 3
popcount(0b1110) = 3
popcount(0b1111) = 4
```

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yalnızca `T` , işaretsiz bir tamsayı türü ise aşırı yükleme çözümüne katılır. Örneğin:,,, vb `unsigned int` `unsigned long` `unsigned short` `unsigned char` .

## <a name="rotl"></a>`rotl`

İşaretsiz bir tamsayı değerinin bitlerini belirtilen sayıda sola döndürür. En soldaki bit "çıkış" ın en sağdaki bite döndürüldüğü bitleri.

```cpp
template<class T>
[[nodiscard]] constexpr T rotl(T value, int s) noexcept;
```

### <a name="parameters"></a>Parametreler

*deeri*\
Döndürülecek işaretsiz tamsayı değeri.

*malar*\
Gerçekleştirilecek sol döndürmeler sayısı.

### <a name="return-value"></a>Döndürülen değer

`value`Left, Times döndürme sonucu `s` . \
`s`Sıfırsa, döndürür `value` . \
`s`Negatifse, olur `rotr(value, -s)` . En sağdaki bitin ' Fall ' olan bitler en soldaki bite döndürülür.

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char bits = 1;
    for (int i = 0; i < 8; ++i)
    {
        std::cout << "rotl(0b" << std::bitset<8>(bits) << ", 1) = ";
        bits = std::rotl(bits, 1);
        std::cout << "0b" << std::bitset<8>(bits) << '\n';
    }
    std::cout << "rotl(0b" << std::bitset<8>(bits) << ",-1) = ";
    bits = std::rotl(bits, -1);
    std::cout << "0b" << std::bitset<8>(bits);
    return 0;
}
```

```Output
rotl(0b00000001, 1) = 0b00000010
rotl(0b00000010, 1) = 0b00000100
rotl(0b00000100, 1) = 0b00001000
rotl(0b00001000, 1) = 0b00010000
rotl(0b00010000, 1) = 0b00100000
rotl(0b00100000, 1) = 0b01000000
rotl(0b01000000, 1) = 0b10000000
rotl(0b10000000, 1) = 0b00000001
rotl(0b00000001,-1) = 0b10000000
```

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yalnızca `T` , işaretsiz bir tamsayı türü ise aşırı yükleme çözümüne katılır. Örneğin:,,, vb `unsigned int` `unsigned long` `unsigned short` `unsigned char` .

## <a name="rotr"></a>`rotr`

Belirtilen sayıda doğru olan bit sayısını döndürür `value` . En sağdaki bitin ' Fall ' olan bitleri en soldaki bite geri döndürülür.

```cpp
template<class T>
[[nodiscard]] constexpr T rotr(T value, int s) noexcept;
```

### <a name="parameters"></a>Parametreler

*deeri*\
Döndürülecek işaretsiz tamsayı değeri.

*malar*\
Gerçekleştirilecek sağ döndürmeler sayısı.

### <a name="return-value"></a>Döndürülen değer

Doğru döndürme sonucu `value` `s` . \
`s`Sıfırsa, döndürür `value` . \
`s`Negatifse, olur `rotl(value, -s)` . En soldaki bitin ' Fall ' olan bitleri en sağdaki bite geri döndürülür.

### <a name="example"></a>Örnek

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char bits = 128;
    for (int i = 0; i < 8; ++i)
    {
        std::cout << "rotr(0b" << std::bitset<8>(bits) << ", 1) = ";
        bits = std::rotr(bits, 1);
        std::cout << "0b" << std::bitset<8>(bits) << '\n';
    }
    std::cout << "rotr(0b" << std::bitset<8>(bits) << ",-1) = ";
    bits = std::rotr(bits, -1);
    std::cout << "0b" << std::bitset<8>(bits);
    return 0;
}
```

```Output
rotr(0b10000000, 1) = 0b01000000
rotr(0b01000000, 1) = 0b00100000
rotr(0b00100000, 1) = 0b00010000
rotr(0b00010000, 1) = 0b00001000
rotr(0b00001000, 1) = 0b00000100
rotr(0b00000100, 1) = 0b00000010
rotr(0b00000010, 1) = 0b00000001
rotr(0b00000001, 1) = 0b10000000
rotr(0b10000000,-1) = 0b00000001
```

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yalnızca `T` , işaretsiz bir tamsayı türü ise aşırı yükleme çözümüne katılır. Örneğin:,,, vb `unsigned int` `unsigned long` `unsigned short` `unsigned char` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<bit>

**Ad alanı:** std

[/std: c + + en son](../build/reference/std-specify-language-standard-version.md) gereklidir.

## <a name="see-also"></a>Ayrıca bkz.

[\<bit>](bit.md)
