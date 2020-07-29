---
title: chrono değişmez değerleri
ms.date: 11/04/2016
ms.assetid: 1a9e23b1-256f-4570-8226-5fa7364fb032
ms.openlocfilehash: d8416580df09a8a466678702cb20ba4ddf37eb28
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230162"
---
# <a name="chrono-literals"></a>chrono değişmez değerleri

(C++ 14) \<chrono>Üst bilgi, saat, dakika, saniye, milisaniye, mikrosaniye ve nanosaniye değerlerini temsil eden sabit değerleri kullanmayı kolaylaştırmak için 12 [Kullanıcı tanımlı sabit değerleri](../cpp/user-defined-literals-cpp.md) tanımlar. Kullanıcı tanımlı her değişmez değer bir integral ve kayan nokta aşırı yüklemesi içerir. Sabit değerler, std:: hatası, kapsam içinde olduğunda otomatik olarak kapsama getirilen sabit değerler:: chrono_literals satır içi ad alanında tanımlanmıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
inline namespace literals {
  inline namespace chrono_literals {
    // return integral hours
    constexpr chrono::hours operator"" h(unsigned long long Val);

    // return floating-point hours
    constexpr chrono::duration<double, ratio<3600>> operator"" h(long double Val);

    // return integral minutes
    constexpr chrono::minutes(operator"" min)(unsigned long long Val);

    // return floating-point minutes
    constexpr chrono::duration<double, ratio<60>>(operator"" min)(long double Val);

    // return integral seconds
    constexpr chrono::seconds operator"" s(unsigned long long Val);

    // return floating-point seconds
    constexpr chrono::duration<double> operator"" s(long double Val);

    // return integral milliseconds
    constexpr chrono::milliseconds operator"" ms(unsigned long long Val);

    // return floating-point milliseconds
    constexpr chrono::duration<double, milli> operator"" ms(long double Val);

    // return integral microseconds
    constexpr chrono::microseconds operator"" us(unsigned long long Val);

    // return floating-point microseconds
    inline constexpr chrono::duration<double, micro> operator"" us(long double Val);

    // return integral nanoseconds
    inline constexpr chrono::nanoseconds operator"" ns(unsigned long long Val);

    // return floating-point nanoseconds
    constexpr chrono::duration<double, nano> operator"" ns(long double Val);

  } // inline namespace chrono_literals
} // inline namespace literals
```

## <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken alan sabit değerler, **`long long`** bir değeri veya ilgili türü döndürür. Kayan nokta bağımsız değişkeni alan sabit değerler bir [süre](../standard-library/duration-class.md)döndürür.

## <a name="example"></a>Örnek

Aşağıdaki örneklerde, EO değişmez değerlerinin nasıl kullanılacağı gösterilmiştir.

```cpp
constexpr auto day = 24h;
constexpr auto week = 24h* 7;
constexpr auto my_duration_unit = 108ms;
```
