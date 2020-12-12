---
description: 'Daha fazla bilgi: tamsayı limitleri'
title: Tamsayı Sınırları
ms.date: 01/29/2018
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
ms.openlocfilehash: 78081f8af1c3d1e1f9f71e5d61dea4ee2bd7085c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345530"
---
# <a name="integer-limits"></a>Tamsayı Sınırları

**Microsoft'a özgü**

Tamsayı türleri için sınırlar aşağıdaki tabloda listelenmiştir. Bu sınırlara yönelik Önişlemci makroları, standart üstbilgi dosyasını eklediğinizde de tanımlanır \<climits> .

## <a name="limits-on-integer-constants"></a>Tamsayı sabitleri için sınırlar

| Sabit | Anlamı | Değer |
|--|--|--|
| `CHAR_BIT` | En küçük değişkende bit alanı olmayan bit sayısı. | 8 |
| `SCHAR_MIN` | Türünde bir değişken için minimum değer **`signed char`** . | -128 |
| `SCHAR_MAX` | Türünde bir değişken için maksimum değer **`signed char`** . | 127 |
| `UCHAR_MAX` | Türünde bir değişken için maksimum değer **`unsigned char`** . | 255 (0xFF) |
| `CHAR_MIN` | Türünde bir değişken için minimum değer **`char`** . | -128; **`/J`** seçenek kullanılırsa 0 |
| `CHAR_MAX` | Türünde bir değişken için maksimum değer **`char`** . | 127; **`/J`** seçenek kullanılırsa 255 |
| `MB_LEN_MAX` | Çok karakterli bir sabitteki en fazla bayt sayısı. | 5 |
| `SHRT_MIN` | Türünde bir değişken için minimum değer **`short`** . | -32768 |
| `SHRT_MAX` | Türünde bir değişken için maksimum değer **`short`** . | 32767 |
| `USHRT_MAX` | Türünde bir değişken için maksimum değer **`unsigned short`** . | 65535 (0xFFFF) |
| `INT_MIN` | Türünde bir değişken için minimum değer **`int`** . | -2147483648 |
| `INT_MAX` | Türünde bir değişken için maksimum değer **`int`** . | 2147483647 |
| `UINT_MAX` | Türünde bir değişken için maksimum değer **`unsigned int`** . | 4294967295 (0xffffffff) |
| `LONG_MIN` | Türünde bir değişken için minimum değer **`long`** . | -2147483648 |
| `LONG_MAX` | Türünde bir değişken için maksimum değer **`long`** . | 2147483647 |
| `ULONG_MAX` | Türünde bir değişken için maksimum değer **`unsigned long`** . | 4294967295 (0xffffffff) |
| `LLONG_MIN` | Türünde bir değişken için minimum değer **`long long`** | -9223372036854775808 |
| `LLONG_MAX` | Türünde bir değişken için en büyük değer **`long long`** | 9223372036854775807 |
| `ULLONG_MAX` | Türünde bir değişken için en büyük değer **`unsigned long long`** | 18446744073709551615 (0xffffffffffffffff) |

Bir değer en büyük tamsayı gösterimini aşarsa, Microsoft derleyicisi bir hata oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan sınırlar](../cpp/floating-limits.md)
