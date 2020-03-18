---
title: char, wchar_t, char16_t, char32_t
ms.date: 02/14/2018
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
ms.openlocfilehash: a518f24973aaddff59b97f104d9d912e4a2bedce
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447161"
---
# <a name="char-wchar_t-char16_t-char32_t"></a>char, wchar_t, char16_t, char32_t

**Char**, **wchar_t**, **char16_t** ve **char32_t** türleri, alfasayısal karakterleri ve yazdırılamayan karakterleri temsil eden yerleşik türlerdir.

## <a name="syntax"></a>Sözdizimi

```cpp
char     ch1{ 'a' };  // or { u8'a' }
wchar_t  ch2{ L'a' };
char16_t ch3{ u'a' };
char32_t ch4{ U'a' };
```

## <a name="remarks"></a>Açıklamalar

**Karakter** türü, C ve C++içindeki özgün karakter türüdür. **İmzasız karakter** türü genellikle içinde C++yerleşik bir tür olmayan bir *bayt*temsil etmek için kullanılır. **Char** türü, ASCII karakter KÜMESINDEN veya ıso-8859 karakter kümelerinden karakterleri depolamak Için veya SHIFT-JIS ya da Unicode karakter kümesinin UTF-8 kodlaması gibi çok baytlık karakterlerin tek tek baytlarından saklamak için kullanılabilir. **Karakter** türündeki dizeler, çok baytlı karakterleri kodlamak için kullanıldığında bile *dar* dizeler olarak adlandırılır. Microsoft derleyicisinde, **char** 8 bitlik bir türdür.

**Wchar_t** türü, uygulama tanımlı bir geniş karakter türüdür. Microsoft derleyicisinde, Windows işletim sistemlerindeki yerel karakter türü olan UTF-16LE olarak kodlanmış Unicode 'U depolamak için kullanılan 16 bit geniş bir karakteri temsil eder. Evrensel C çalışma zamanı (UCRT) kitaplığı işlevlerinin geniş karakter sürümleri, yerel Windows API 'sinin geniş karakter sürümleri gibi **wchar_t** ve işaretçi ve dizi türlerini parametre olarak ve dönüş değerlerini kullanır.

**Char16_t** ve **char32_t** türleri sırasıyla 16 bit ve 32 bitlik geniş karakterleri temsil eder. UTF-16 olarak kodlanan Unicode, **char16_t** türünde DEPOLANABILIR ve utf-32 olarak kodlanmış unicode, **char32_t** türünde depolanabilir. Bu türlerin ve **wchar_t** dizelerinin hepsi *geniş* dizeler olarak adlandırılır, ancak terim genellikle **wchar_t** türündeki dizelere başvurur.

C++ Standart kitaplıkta `basic_string` türü hem dar hem de geniş dizeler için özelleştirilmiştir. Karakterler **char**türünde olduğunda `std::string`, **karakterler tür** **char16_t**olduğunda `std::u32string` ve karakterler **char32_t türünde olduğunda**, `std::wstring` `std::u16string` kullanın. `std::stringstream` ve `std::cout` dahil olmak üzere metni temsil eden diğer türler, dar ve geniş dizeler için Uzmanlıklar vardır.