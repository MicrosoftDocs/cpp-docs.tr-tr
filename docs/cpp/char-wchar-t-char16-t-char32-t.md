---
description: 'Hakkında daha fazla bilgi edinin: char, wchar_t, char16_t, char32_t'
title: char, wchar_t, char16_t, char32_t
ms.date: 02/14/2018
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
ms.openlocfilehash: f8bab56bf8a2cebe8409c9dc4ceecf931ec83260
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278798"
---
# <a name="char-wchar_t-char16_t-char32_t"></a>char, wchar_t, char16_t, char32_t

, Ve türleri, alfasayısal **`char`** **`wchar_t`** olmayan karakterler **`char16_t`** **`char32_t`** ve yazdırılamayan karakterler içeren yerleşik türlerdir.

## <a name="syntax"></a>Syntax

```cpp
char     ch1{ 'a' };  // or { u8'a' }
wchar_t  ch2{ L'a' };
char16_t ch3{ u'a' };
char32_t ch4{ U'a' };
```

## <a name="remarks"></a>Açıklamalar

**`char`** Tür, C ve C++ içindeki özgün karakter türüdür. Tür **`unsigned char`** genellikle C++ ' da yerleşik bir tür olmayan bir *baytı* temsil etmek için kullanılır. **`char`** Tür, ASCII karakter kümesinden veya ISO-8859 karakter kümelerinden karakterleri depolamak için veya SHIFT-JIS ya da Unicode karakter KÜMESININ UTF-8 kodlaması gibi çok baytlık karakterlerin tek tek baytlarından saklamak için kullanılabilir. Türündeki dizeler **`char`** , çok baytlı karakterleri kodlamak için kullanıldığında bile *dar* dizeler olarak adlandırılır. Microsoft derleyicisinde **`char`** 8 bitlik bir türdür.

**`wchar_t`** Tür, uygulama tanımlı geniş karakter türüdür. Microsoft derleyicisinde, Windows işletim sistemlerindeki yerel karakter türü olan UTF-16LE olarak kodlanmış Unicode 'U depolamak için kullanılan 16 bit geniş bir karakteri temsil eder. Evrensel C çalışma zamanı (UCRT) kitaplığı işlevlerinin geniş karakter sürümleri, **`wchar_t`** Yerel WINDOWS API 'sinin geniş karakter sürümleri gibi, parametre ve dönüş değerleri olarak ve işaretçi ve dizi türlerini kullanır.

**`char16_t`** Ve **`char32_t`** türleri sırasıyla 16 bit ve 32 bitlik geniş karakterleri temsil eder. UTF-16 olarak kodlanmış Unicode, **`char16_t`** türde depolanabilir ve UTF-32 olarak kodlanmış Unicode, tür içinde depolanabilir **`char32_t`** . Bu türlerin dizeleri ve **`wchar_t`** hepsi *geniş* dizeler olarak adlandırılır, ancak terim genellikle türündeki dizelere başvurur **`wchar_t`** .

C++ standart kitaplığında, `basic_string` türü hem dar hem de geniş dizeler için özelleştirilmiştir. Karakterler tür olduğunda, karakterler tür olduğunda, karakterler tür olduğunda `std::string` **`char`** `std::u16string` **`char16_t`** `std::u32string` **`char32_t`** ve `std::wstring` karakterler tür **`wchar_t`** olduğunda kullanın. Metin temsil eden `std::stringstream` ve `std::cout` dar ve geniş dizeler için Uzmanlıklar içeren diğer türler.
